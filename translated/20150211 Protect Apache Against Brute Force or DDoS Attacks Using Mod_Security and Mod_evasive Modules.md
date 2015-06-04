在Apache中使用Mod_Security和Mod_evasive来抵御暴力破解和DDos攻击
================================================================================
对于那些托管主机或者将您的主机暴露在因特网中的人来说，保证您的系统在面对攻击者时安全是一个重要的事情。

mod_security（一个可以无缝接入Web服务器的开源的用于Web应用入侵检测和防护的引擎）和mod_evasive是两个在服务器端对抗暴力破解和(D)Dos攻击的非常重要的工具。

mod_evasive，如它的名字一样，在受攻击时提供避实就虚的功能，它像一个雨伞一样保护Web服务器免受那些威胁。

![](http://www.tecmint.com/wp-content/uploads/2012/06/Install-Mod_Security-Mod_evasive-in-CentOS.jpg)

安装Mod_Security和Mod_Evasive来保护Apache

在这篇文章中我们将讨论如何安装、配置以及在RHEL/CentOS6、7和Fedora 21-15上将它们结合到Apache。另外，我们会模拟攻击以便验证服务器进行了正确的反应。

这以您的系统中安装有LAMP服务器为基础，所以，如果您没有安装，请先阅读下面链接的文章再开始阅读本文。

- [在RHEL/CentOS 7中安装LAMP堆栈][1]

如果您在运行RHEL/CentOS 7或Fedora 21，您还需要安装iptables作为默认[防火墙][2]前端以取代firewalld。这样做时为了在RHEL/CentOS 7或Fedora 21中使用同样的工具。

### 步骤 1: 在RHEL/CentOS 7和Fedora 21上安装Iptables防火墙 ###

用下面的命令停止和禁用firewalld：

    # systemctl stop firewalld
    # systemctl disable firewalld

![](http://www.tecmint.com/wp-content/uploads/2012/06/Disable-Firewalld-Service.png)
禁用firewalld服务

接下来在使能iptables之前安装iptables-services包：

    # yum update && yum install iptables-services
    # systemctl enable iptables
    # systemctl start iptables
    # systemctl status iptables

![](http://www.tecmint.com/wp-content/uploads/2012/06/Install-Iptables-Firewall.png)
安装Iptables防火墙

### 步骤 2: 安装Mod_Security和Mod_evasive ###

另外，在安装LAMP后，您还需要在RHEL/CentOS 7/6中[开启EPEL仓库][3]来安装这两个包。Fedora用户不需要开启这个仓库，因为epel已经是Fedora项目的一部分了。

    # yum update && yum install mod_security mod_evasive

当安装结束后，您会在/etc/httpd/conf.d下找到两个工具的配置文件。

    # ls -l /etc/httpd/conf.d

![](http://www.tecmint.com/wp-content/uploads/2012/06/mod_security-mod_evasive-Configurations.png)
mod_security + mod_evasive 配置文件

现在，为了整合这两个模块到Apache，并在启动时将它们加载。请确保下面几行出现在mod_evasive.conf和mod_security.conf的顶层部分，它们分别为：

    LoadModule evasive20_module modules/mod_evasive24.so
    LoadModule security2_module modules/mod_security2.so

请注意modules/mod_security2.so和modules/mod_evasive24.so都是从/etc/httpd到模块源文件的相对路径。您可以通过列出/etc/httpd/modules的内容来验证（如果需要的话，修改它）：

    # cd /etc/httpd/modules
    # pwd
    # ls -l | grep -Ei '(evasive|security)'

![](http://www.tecmint.com/wp-content/uploads/2012/06/Verify-mod_security-mod_evasive-Modules.png)
验证mod_security + mod_evasive模块

接下来重启Apache并且核实它已加载了mod_evasive和mod_security：

    # service httpd restart 		[在RHEL/CentOS 6和Fedora 20-18上]
    # systemctl restart httpd 		[在RHEL/CentOS 7和Fedora 21上]

----------

    [输出已加载的静态模块和动态模块列表]

    # httpd -M | grep -Ei '(evasive|security)'	
    
![](http://www.tecmint.com/wp-content/uploads/2012/06/Check-mod_security-mod_evasive-Loaded.png)
检查mod_security + mod_evasive模块已加载

### 步骤 3: 安装一个核心规则集并且配置Mod_Security ###

简单来说，一个核心规则集（即CRS）为web服务器提供特定状况下如何反应的指令。mod_security的开发者们提供了一个免费的CRS，叫做OWASP（[开放Web应用安全项目]）ModSecurity CRS，它能在下面的地址被下载和安装。

1. 下载OWASP CRS到为之创建的目录

    # mkdir /etc/httpd/crs-tecmint
    # cd /etc/httpd/crs-tecmint
    # wget https://github.com/SpiderLabs/owasp-modsecurity-crs/tarball/master

![](http://www.tecmint.com/wp-content/uploads/2012/06/Download-mod_security-Core-Rules.png)
下载mod_security核心规则

2. 解压CRS文件并修改文件夹名称

    # tar xzf master
    # mv SpiderLabs-owasp-modsecurity-crs-ebe8790 owasp-modsecurity-crs

![](http://www.tecmint.com/wp-content/uploads/2012/06/Extract-mod_security-Core-Rules.png)
解压mod_security核心规则

3. 现在，是时候配置mod_security了。将同样的规则文件（owasp-modsecurity-crs/modsecurity_crs_10_setup.conf.example）拷贝至另一个没有.example扩展的文件。

    # cp modsecurity_crs_10_setup.conf.example modsecurity_crs_10_setup.conf

并通过将下面的几行插入到web服务器的主配置文件/etc/httpd/conf/httpd.conf来告诉Apache将这个文件和该模块放在一起使用。如果您选择解压打包文件到另一个文件夹，那么您需要修改Include的路径：

    <IfModule security2_module>
        Include crs-tecmint/owasp-modsecurity-crs/modsecurity_crs_10_setup.conf
        Include crs-tecmint/owasp-modsecurity-crs/base_rules/*.conf
    </IfModule>

最后，建议您在/etc/httpd/modsecurity.d目录下创建自己的配置文件，在那里我们可以用我们自定义的文件夹（接下来的示例中，我们会将其命名为tecmint.conf）而无需修改CRS文件的目录。这样做能够在CRSs发布新版本时更加容易的升级。

    <IfModule mod_security2.c>
    	SecRuleEngine On
    	SecRequestBodyAccess On
    	SecResponseBodyAccess On 
    	SecResponseBodyMimeType text/plain text/html text/xml application/octet-stream 
    	SecDataDir /tmp
    </IfModule>

您可以在[SpiderLabs的ModSecurity GitHub][5]仓库中参考关于mod_security目录的更完整的解释。

### 步骤 4: 配置Mod_Evasive ###

mod_evasive被配置为使用/etc/httpd/conf.d/mod_evasive.conf中的指令。与mod_security不同，由于在包升级时没有规则来更新，因此我们不需要独立的文件来添加自定义指令。

默认的mod_evasive.conf开启了下列的目录（注意这个文件被详细的注释了，因此我们剃掉了注释以重点显示配置指令）：

    <IfModule mod_evasive24.c>
        DOSHashTableSize    3097
        DOSPageCount        2
        DOSSiteCount        50
        DOSPageInterval     1
        DOSSiteInterval     1
        DOSBlockingPeriod   10
    </IfModule>

这些指令的解释：

- DOSHashTableSize: 这个指令指明了哈希表的大小，它用来追踪基于IP地址的活动。增加这个数字将使查询站点访问历史变得更快，但如果被设置的太高则会影响整体性能。
- DOSPageCount: Legitimate number of identical requests to a specific URI (for example, any file that is being served by Apache) that can be made by a visitor over the DOSPageInterval interval.
- DOSSiteCount: Similar to DOSPageCount, but refers to how many overall requests can be made to the entire site over the DOSSiteInterval interval.
- DOSBlockingPeriod: If a visitor exceeds the limits set by DOSSPageCount or DOSSiteCount, his source IP address will be blacklisted during the DOSBlockingPeriod amount of time. During DOSBlockingPeriod, any requests coming from that IP address will encounter a 403 Forbidden error.

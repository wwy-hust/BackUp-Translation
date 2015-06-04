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





27个Linux下软件包管理工具‘DNF’（Yum的分支）的命令
================================================================================
DNF即Dandified YUM是基于RPM的发行版的下一代软件包管理工具。它首先在Fedora 18中出现，并且在最近发行的Fedora 22中替代了[YUM工具集][1]。

![](http://www.tecmint.com/wp-content/uploads/2015/05/linux-dnf-command-examples.jpg)

DNF致力于改善YUM的瓶颈，即性能、内存占用、依赖解决、速度和许多其他方面。DNF使用RPM、libsolv和hawkey库进行包管理。尽管它并未预装在CentOS和RHEL 7中，但您可以通过yum安装，并同时使用二者。

您也许想阅读更多关于DNF的信息：

- [使用DNF取代Yum背后的原因][2]

最新的DNF稳定版本是2015年5月11日发布的1.0（在写这篇文章之前）。它（以及所有DNF之前版本）主要由Python编写，并以GPL v2许可证发布。

### 安装DNF ###

尽管Fedora 22官方已经过渡到了DNF，但DNF并不在RHEL/CentOS 7的默认仓库中。

为了在RHEL/CentOS系统中安装DNF，您需要首先安装和开启epel-release仓库。

    # yum install epel-release
    或
    # yum install epel-release -y

尽管并不建议在使用yum时添上'-y'选项，因为最好还是看看什么将安装在您的系统中。但如果您对此并不在意，则您可以使用'-y'选项以自动化的安装而无需用户干预。

接下来，使用yum命令从epel-realease仓库安装DNF包。

    # yum install dnf

在您装完dnf后，我会向您展示27个实用的dnf命令和例子，以便帮您更容易和高效的管理基于RPM包的发行版。

### 1. 检查DNF版本 ###

检查您的系统上安装的DNF版本。

    # dnf --version

![Check DNF Version](http://www.tecmint.com/wp-content/uploads/2015/05/Check-DNF-Version.gif)

### 2. 列出开启的DNF仓库 ###

dnf命令中的'repolist'选项将显示您系统中所有开启的仓库。

    # dnf repolist

![Check All Enabled Repositories](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Enabled-Repositories.gif)

### 3. 列出所有开启和关闭的DNF仓库 ###

'repolist all'选项将显示您系统中所有开启/关闭的仓库。

    # dnf repolist all

![List All Enabled/Disabled Repositories](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Repositories.gif)

### 4. 用DNF列出所有可用的且已安装的软件包 ###

'dnf list'命令将列出所有仓库中所有可用的软件包和您Linux系统中已安装的软件包。

    # dnf list

![List All Packages using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/List-All-Packages.png)

### 5. 用DNF列出所有已安装的软件包 ###

尽管'dnf list'命令将列出所有仓库中所有可用的软件包和已安装的软件包。然而像下面一样使用'list installed'选项将只列出已安装的软件包。

    # dnf list installed

![List All Installed Packages](http://www.tecmint.com/wp-content/uploads/2015/05/List-Installed-Packages.png)

### 6. 用DNF列出所有可用的软件包 ###

类似的，可以用'list available'选项列出所有开启的仓库中所有可用的软件包。

    # dnf list available

![List Available Packages using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/List-Available-Packages.png)

### 7. 使用DNF查找软件包 ###

如果您不太清楚您想安装的软件包的名字，这种情况下，您可以使用'search'选项来搜索匹配该字符（例如，nano）和字符串的软件包。

    # dnf search nano

![Search Package by Word](http://www.tecmint.com/wp-content/uploads/2015/05/Search-Package.gif)

### 8. 查看哪个软件包提供了某个文件/子软件软件包？ ###

dnf的选项'provides'能查找提供了某个文件/子软件包的软件包名。例如，如果您想找找那个软件包提供了您系统中的'/bin/bash'文件，可以使用下面的命令

    # dnf provides /bin/bash

![Find File Sub Package](http://www.tecmint.com/wp-content/uploads/2015/05/Find-Package-Sub-Package.gif)

### 9. 使用DNF获得一个软件包的详细信息 ###

如果您想在安装一个软件包前知道它的详细信息，您可以使用'info'来获得一个软件包的详细信息，例如：

    # dnf info nano

![Check Package Information with DNF](http://www.tecmint.com/wp-content/uploads/2015/05/Check-Package-Information.gif)

### 10. 使用DNF安装软件包 ###

想安装一个叫nano的软件包，只需运行下面的命令，它会为nano自动的解决和安装所有的依赖。

    # dnf install nano

![Install Package using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/Install-Package-DNF.gif)

### 11. 使用DNF更新一个软件包 ###

您可能只想更新一个特定的包（例如，systemd）并且保留系统内剩余软件包不变。

    # dnf update systemd

![Update a Specific Package](http://www.tecmint.com/wp-content/uploads/2015/05/Update-a-Package.gif)

### 12. 使用DNF检查系统更新 ###

检查系统中安装的所有软件包的更新可以简单的使用dnf进行：

    # dnf check-update

![Check For System Update](http://www.tecmint.com/wp-content/uploads/2015/05/Check-For-System-Update.gif)

### 13. 使用DNF安装系统中所有的软件包 ###

您可以使用下面的命令来更新整个系统中所有已安装的软件包。

    # dnf update
    或
    # dnf upgrade

![Update System](http://www.tecmint.com/wp-content/uploads/2015/05/Update-System.gif)

### 14. 使用DNF来移除/删除一个软件包 ###

您可以在dnf命令中使用'remove'或'erase'选项来移除任何不想要的软件包。

    # dnf remove nano
    或
    # dnf erase nano

![Remove Package in Linux](http://www.tecmint.com/wp-content/uploads/2015/05/Remove-Package.gif)

### 15. 使用DNF移除于依赖无用的软件包（Orphan Packages） ###

这些为了满足依赖安装的软件包在相应的程序删除后便不再需要了。可以用过下面的命令来将它们删除。

    # dnf autoremove

![Remove Orphan Packages](http://www.tecmint.com/wp-content/uploads/2015/05/Autoremove-Packages.gif)

### 16. 使用DNF移除缓存的软件包 ###

我们在使用dnf时经常会碰到过期的头部和不完整的事务，它们会导致错误。我们可以使用下面的语句清理缓存的软件包和包含远程包信息的头部。

    # dnf clean all

![Remove DNF Cache](http://www.tecmint.com/wp-content/uploads/2015/05/Remove-Cache-Packages.gif)

### 17. Get Help on Specific DNF Command ###

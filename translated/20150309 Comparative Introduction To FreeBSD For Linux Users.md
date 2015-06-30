以比较的方式向Linux用户介绍FreeBSD
================================================================================
![](https://1102047360.rsc.cdn77.org/wp-content/uploads/2015/03/FreeBSD-790x494.jpg)

### 简介 ###

BSD最初从UNIX继承而来，目前有许多的类Unix操作系统是基于BSD的。FreeBSD是使用最广泛的开源伯克利软件发行版（BSD发行版）。就像它隐含的意思一样，它是一个免费的开源类Unix操作系统，并且是公共服务器的平台。FreeBSD源代码通常以宽松的BSD许可证发布。它与Linux有很多相似的地方，但我们得承认它们在很多方面不同。

本文的其余部分组织如下：FreeBSD的描述在第一部分，FreeBSD和Linux的相似点在第二部分，它们的区别将在第三部分讨论，对他们功能的讨论和总结在最后一节。

### FreeBSD描述 ###

#### 历史 ####

- FreeBSD的第一个版本发布于1993年，它的第一张CD-ROM是FreeBSD1.0，也发行于1993年。接下来，FreeBSD 2.1.0在1995年发布并且获得了所有用户的青睐。实际上许多IT公司都很满意地使用FreeBSD，我们可以列出其中的一些：IBM、Nokia、NetApp和Juniper Network。

#### 许可证 ####

- 关于它的许可证，FreeBSD以多种开源许可证进行发布，它最新的名为Kernel代码以两种子BSD许可证进行了发布，提供使用和重新发布FreeBSD的绝对自由。其它的代码以三、四种子BSD许可证进行发布，有些是以GPL和CDDL的许可证发布的。

#### 用户 ####

- FreeBSD的重要特点之一就是它多样的用户。实际上，FreeBSD可以作为邮件服务器、Web Server、FTP服务器以及路由器等，您只需要在它上运行服务相关的软件即可。而且FreeBSD还支持ARM、PowerPC、MIPS、x86、x86-64架构。

### FreeBSD和Linux的相似处 ###

FreeBSD和Linux是两个免费开源的软件。实际上，它们的用户可以很容易的检查并修改源代码，用户拥有绝对的自由。而且，FreeBSD和Linux都是类Unix系统，它们的内核、内部组件、库程序都使用从历史上的AT&T Unix处继承的算法。FreeBSD从根基上更像Unix系统，而Linux是作为免费的类Unix系统发布的。许多工具应用都可以在FreeBSD和Linux中找到，实际上，他们几乎有同样的功能。

此外，FreeBSD能够运行大量的Linux应用。它可以安装一个Linux的兼容层，这个兼容层可以在编译FreeBSD时加入AAC Compact Linux得到或通过下载已编译了Linux兼容层的FreeBSD系统，其中会包括兼容程序：aac_linux.ko。这不同于Linux，Linux无法运行FreeBSD的软件。

最后，我们注意到虽然二者有同样的目标，但二者还是有一些不同之处，我们在下一节中列出。

### FreeBSD和Linux的区别 ###

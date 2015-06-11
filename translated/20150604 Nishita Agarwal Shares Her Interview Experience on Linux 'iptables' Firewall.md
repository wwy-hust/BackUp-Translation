Nishita Agarwal分享它关于Linux防火墙'iptables'的面试经验
================================================================================
Nishita Agarwal是Tecmint的用户，她将分享它关于刚刚经历的一家公司（私人公司Pune，印度）的面试经验。在面试中她被问道了许多不同的问题，但她是iptables方面的专家，因此她想分享这些关于iptables的问题和相应的答案给那些以后可能会进行相关面试的人。

![Linux防火墙Iptables面试问题](http://www.tecmint.com/wp-content/uploads/2015/05/Linux-iptables-Interview-Questions.jpg)

所有的问题和相应的答案都基于Nishita Agarwal的记忆经过了重写。

> “嗨，朋友！我叫**Nishita Agarwal**。我已经取得了理学本科学位，我的专业集中在UNIX和它的变种（BSD，Linux）。它们一直深深的吸引着我。我在存储方面有1年+的经验。我在寻求职业上的变化，并将供职于印度的Pune公司。”

下面是我在面试中被问到的问题的集合。我已经把我记忆中有关iptables的问题和它们的答案记录了下来。希望这会对您未来的面试有所帮助。

### 1. 你听说过Linux下面的iptables和防火墙么？知不知道它们是什么，是用来干什么的？ ###

> **答案** : iptables和防火墙我都知道，并且我已经使用iptables好一段时间了。iptables主要由C语言写成，并且以GNU GPL许可证发布。它是以系统管理员的角度写的，最新的稳定版是iptables 1.4.21。iptables通常被认为是类UNIX系统中的防火墙，更准确的说，可以称为iptables/netfilter。管理员通过终端/GUI工具与iptables打交道，来添加和定义防火墙规则到预定义的表中。Netfilter是内核中的一个模块，它执行过滤的任务。
> 
> Firewalld是RHEL/CentOS 7（也许还有其他发行版，但我不太清楚）中实现的最新的过滤规则。它已经取代了iptables接口，并与netfilter相连接。

### 2. 你用过一些iptables的GUI或命令行工具么？ ###

> **答案** : 虽然我既用过GUI工具，比如与[Webmin][1]结合的Shorewall；以及直接通过终端访问iptables。但我必须承认通过Linux终端直接访问iptables能给予用户更高级的灵活性、对其背后工作更好的理解的能力。GUI适合初级管理员而终端适合有经验的管理员。

### 3. 那么iptables和firewalld的基本区别是什么呢？ ###

> **答案** : iptables和firewalld都有着同样的目的（包过滤），但它们使用不同的方式。iptables与firewalld不同，在每次发生更改时都刷新整个规则集。通常iptables配置文件位于‘/etc/sysconfig/iptables‘，而firewalld的配置文件位于‘/etc/firewalld/‘。firewalld的配置文件是一组XML文件。以XML为基础进行配置的firewalld比iptables的配置更加容易，但是两者都可以完成同样的任务。例如，firewalld可以在自己的命令行界面以及基于XML的配置文件下使用iptables。

### 4. 如果有机会的话，你会在你所有的服务器上用firewalld替换iptables么？ ###

> **答案** : 我对iptables很熟悉，它也工作的很好。如果没有任何需求需要firewalld的动态特性，那么没有理由把所有的配置从iptables移动到firewalld。通常情况下，目前为止，我还没有看到iptables造成什么麻烦。IT技术的通用准则也说道“为什么要修一件没有坏的东西呢？”。上面是我自己的想法，但如果组织愿意用firewalld替换iptables的话，我不介意。

### 5. 你看上去对iptables很有信心，巧的是，我们的服务器也在使用iptables。 ###

iptables使用的表由哪些？请简要的描述iptables使用的表以及它们支持的链。

> **答案** : 谢谢您的赞赏。至于您问得问题，iptables使用的表有四个，它们是：
> 
>     Nat 表
>     Mangle 表
>     Filter 表
>     Raw 表
> 
> Nat表 : Nat表主要用于网络地址转换。根据表中的每一条规则修改网络包的IP地址。流中的包遍历Nat表仅仅一遍。例如，如果一个通过某个接口的包被修饰（修改了IP地址），该流中其余的包将不再遍历这个表。通常不建议在这个表中进行过滤，由NAT表支持的链称为PREROUTING Chain，POSTROUTING Chain和OUTPUT Chain。
> 
> Mangle表 : 





















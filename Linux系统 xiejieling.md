# 第1章 了解并安装Linux系统

## 1.1 Linux系统的发展与特点

### 1.1.1 Linux的发展历史

####（1）Linux系统的简介

Linux是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。它能运行主要的UNIX工具软件、应用程序和网络协议。支持32位和64位硬件。
Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。可安装在各种计算机硬件设备中，如手机、平板电脑、路由器、视频游戏控制台、台式计算机、大型机和超级计算机。

人们习惯用Linux来形容整个基于Linux内核，并且使用GNU 工程各种工具和数据库的操作系统。严格来讲，Linux操作系统指的是“linux内核+各种软件”，Linux这个词只表示Linux内核。

####（2）Linux的由来

##### 1、想法诞生

Linux内核是林纳斯·托瓦兹（LinusTorvalds）最先设计的。
在1988年，托瓦兹进入赫尔辛基大学选读了计算机科学系。因为学业需要与个人兴趣，他接触到了unix这个操作系统。当时整个赫尔辛基只有一部最新的UNIX系统,但是仍然很难满足托瓦兹的需求。为此,他就想到自己写一个类unix操作系统。

##### 2、着手设计

在1991年初，林纳斯·托瓦兹购买了最新的intel386的个人计算机，安装了Minix系统，开始学习minix操作系统。经由Minix系统的源码学习到了很多内核程序设计的设计概念。1991年4月，林纳斯·托瓦兹开始酝酿并着手编制自己的操作系统。

##### 3、分享与修改

当托瓦兹发现自己的写的东西可以在386上面顺利运行，并且可以读取Minix的文件系统后，他将这个内核程序放置在当时芬兰最大的ftp网络上供大家下载，同时在BBS上面贴了一则消息，希望能获得大家的一些修改建议。因此当用户在安装使用时，发生问题，会反馈给托瓦兹。在托瓦兹能够解决的问题范围内，他能很快速的进行linux内核的更新和排错。

同时为了让自己的Linux能够兼容于UNIX系统，并让所有的软件都可以在Linux上执行，托瓦兹开始参考标准的POSIX规范。
> POSIX是可携式操作系统接口(（Portable Operating System Interface)）的缩写，重点在于规范核心内核与应用程序之间的接口，这是由美国电气与电子工程师学会(（IEEE)）所发布的一项标准！

##### 4、广大爱好者的加入

部分硬件需求得不到满足，托瓦兹因此无法编写相关驱动程序。此时，有志愿者愿意帮忙写驱动程序。只要经测试可以运行后，托瓦兹就会将这些程序代码加入到内核中。因为这样的状况，linux的开发逐渐模块化，可维护性也大大增加。

因为Linux内核加入了太多的功能，托瓦兹无法一个人进行内核的实际测试并加入内核源程序，有更多的人加入进来。例如考克斯（AlanCox）、与崔迪（StephenTweedie）等，这些重要的副手会先将志愿者的修补程序或者新功能的程序代码进行测试，并且将结果上传给托瓦兹。托瓦兹负责最后内核加入的源码的选择与整并，这种分层负责的方式让Linux的开发更加容易！

##### 5、linux正式版的发布

这个团队，在1994年正式完成了Linux的内核正式版Version 1.0，代码量达17万行。这一版同时还加入了X Window System的支持，此外，托瓦兹指命企鹅为Linux的吉祥物。
在1996年6月，Linux 2.0内核发布，此内核有大约40万行代码，并可以支持多个处理器。此时的Linux 已经进入了实用阶段，全球大约有350万人使用。

####（3）Linux开枝散叶

##### 1、不同distribution的产生

因为linux加入了gnu计划，所以，任何人均可取得源码和可执行这个内核程序，并且可以修改。并且由于GNU的GPL授权并非不能从事商业行为，因此很多商业公司和团队便专门来开发自己的linux distribution。比较出名的有Red Hat，SuSE,Ubuntu,Fedora,Debian,CentOS等。

##### 2、不同distribution的支持标准

因为这些版本使用的都是同一个内核，而且还有LinuxStandardBase（LSB）以及目录架构的FilesystemHierarchyStandard（FHS）标准规范等一些标准来规范开发者，它们的唯一差别可能就是该开发者自家所开发出来的管理工具以及套件管理的模式。所以基本上，每个Linux distributions除了架构的严谨度与选择的套件内容外，其实差异并不太大，大家可以选择自己喜好的distribution来安装。

### 1.1.2 Linux Kernel

Linux是一种开源电脑操作系统内核。它是一个用C语言写成，符合POSIX标准的类Unix操作系统。

Linux最早是由芬兰LinusTorvalds为尝试在英特尔架构上提供自由的类Unix操作系统而开发的。该计划开始于1991年，在计划的早期有一些Minix黑客提供了协助，而今天全球无数程序员正在为该计划无偿提供帮助。操作系统是一个用来和硬件打交道并为用户程序提供一个有限服务集的低级支撑软件。一个计算机系统是一个硬件和软件的共生体，它们互相依赖，不可分割。计算机的硬件，含有外围设备、处理器、内存、硬盘和其他的电子设备组成计算机的发动机。但是没有软件来操作和控制它，自身是不能工作的。完成这个控制工作的软件就称为操作系统，在Linux的术语中被称为“内核”，也可以称为“核心”。Linux内核的主要模块（或组件）分以下几个部分：存储管理、CPU和进程管理、文件系统、设备管理和驱动、网络通信，以及系统的初始化（引导）、系统调用等。

### 1.1.3 GNU计划

GNU 是“GNU’s Not UNIX”的递归缩写。GNU 计划，又译为“革奴计划”，是由理查德·斯托曼在 1983 年 9 月 27 日公开发起的，它的目标是创建一套完全自由的操作系统。
理查德·斯托曼最早是在 net.unix-wizards 新闻组上公布该消息，并附带一份《GNU 宣言》等解释为何发起该计划的文章，其中一个理由就是要“重现当年软件界合作互助的团结精神”。

UNIX 是一种广泛使用的商业操作系统的名称。由于 GNU 将要实现 UNIX 系统的接口标准，因此 GNU 计划可以分别开发不同的操作系统。GNU 计划采用了部分当时已经可自由使用的软件，例如 TeX 排版系统和 X Window 视窗系统等。不过 GNU 计划也开发了大批其他的自由软件，这些软件也被移植到其他操作系统平台上，例如 Microsoft Windows、BSD 家族、Solaris 及 MacOS。

为保证 GNU 软件可以自由地“使用、复制、修改和发布”，所有 GNU 软件都包含一份在禁止其他人添加任何限制的情况下，授权所有权利给任何人的协议条款，GNU 通用公共许可证（GNU General Public License，GPL）。这个就是被称为‘公共版权’的概念。GNU 也针对不同场合，提供 GNU 宽通用公共许可证（与 GNU 自由文档许可证这两种协议条款。

### 1.1.4 Linux的发行版本

#### Linux 10个主流发行版本

[![img](https://cambrian-images.cdn.bcebos.com/6b035c21a1f586e324acd74c8f479bb2_1537539247585.jpeg?x-bce-process=image/resize,m_lfit,w_200,h_200&autime=20)](https://author.baidu.com/home?from=bjh_article&app_id=1596904315487549)

主机捕手
发布时间: 18-04-1706:47
这10个Linux发行版来源于国外网站(最后给出链接)。它列出了10个Linux发行版（包含一个FreeBSD，Linux的胞兄弟），通常被认为是全球Linux用户最广泛使用的。

**Ubuntu，Linux Mint和PCLinuxOS** 是其中最易用使用的。想快速部署使用，就可以选择这几个。尤其对于新手，已经做到了和Windows类似的易用程度了。另一方面，Slackware Linux，Arch Linux和FreeBSD是更激进的发行版，更新比较频繁，需要有一定的基础。openSUSE，Fedora，DebianGNU/Linux和Mageia则是比较保守的发行版。稳定性是他们的特点，但是软件包都比较旧。很多桌面版本的新功能没法用。CentOS是一个企业级的发行版，适合那些喜欢稳定性，可靠性和软件长期支持的用户。

#####**Linux Mint**
![img](https://t12.baidu.com/it/u=825897314,2765535575&fm=173&app=25&f=JPEG?w=90&h=90&s=6356A472C5307B301C7C164E0300E074)

LinuxMint是一个基于Ubuntu的发行版，最早于2006年由居住在爱尔兰的法国出生的IT专家ClementLefebvre发布。最初维护一个专门为新Linux用户提供帮助，技巧和文档的Linux网站，该发行版致力于解决那些技术性较强的产品的使用问题，让它们更易于使用。他把许多人提到的“改进的Ubuntu”或“Ubuntu完善版”的东西建立起来。注：Ubuntu就是以易用，对新手友好著称的。可想而知Mint的目标更进一步，让Linux更加的贴近了普通用户。

但LinuxMint不仅仅是一个具有新的应用程序和更新的桌面主题的Ubuntu。自开始以来，开发人员一直在增加各种Mint下的图形工具以提高可用性。这包括mintDesktop–用于配置桌面环境的实用程序，mintMenu–一个新的，优雅的菜单结构，以方便导航，mintInstall–一个易于使用的软件安装程序，mintUpdate–一个软件更新程序，提供了一些更突出的几个工具和数百个额外的改进。该项目还开发了很多替代的专有程序以避免一些潜在的法律版权问题，其中包括专利和专利设计的多媒体编解码器，这些编解码器在很多发行版中通常是不存在的。因此，Mint在易用性方面的声誉得到了进一步的加强，也许Linux Mint的最佳特性之一就是开发人员倾听用户的意见，并总是快速地实施好的建议。

LinuxMint可以免费下载，它没有固定的发布时间表或者计划的功能列表，但是在每个Ubuntu长期支持版本发布几周后，可以预期LinuxMint的新版本。除Mint的MATE和Cinnamon桌面两个主要版本之外，该项目还使用包括KDE和Xfce在内的其他桌面版本构建版本。这些版本通常在两个“主要”版本几周后完成，有时可能会缺少一些主要分支中的一些“Mint”工具和其他功能。Mint系列的另一个版本是基于Debian稳定版分支的“Debian版”。LinuxMint的Debian版本提供了非常稳定的基础，而桌面软件包的更新速度比Mint的“主要分支”版本更快。 Linux Mint不适用软件自由原则，也不会发布安全公告。

**优点**：精心整理的内部开发的“Mint”工具，数百个用户友好的增强功能，包含多媒体编解码器
**缺点**：“社区”版本，因此可能并不总是包含最新的功能。另外，项目不会发布安全建议软件包管理  ：mintInstall包管理器,使用DEB包（与Ubuntu兼容）
**可用的版本**：“主”版本（MATE和Cinnamon桌面），“社区”版本（KDE和Xfce桌面），Linux Mint“Debian”版本（MATE或Cinnamon桌面）
**替代选择**：Ubuntu, elementary OS, Zorin OS, Lubuntu, Xubuntu, Peppermint OS 

![img](https://t12.baidu.com/it/u=1689382931,3096975977&fm=173&app=25&f=JPEG?w=480&h=370&s=C992429A1534ED8AC2C408D8030050B2)

#####**Ubuntu**
![img](https://t11.baidu.com/it/u=1081556905,2186049380&fm=173&app=25&f=JPEG?w=90&h=91&s=06E6D8168CF5509278B31AFE0300702B)

Ubuntu的推出是在2004年9月首次宣布的。尽管这个项目在Linux发行版中是一个相对较新的，但是它的邮件列表很快就被热情的用户和开发人员所占领。随后的几年中，Ubuntu发展成为最受欢迎的桌面Linux发行版，并为开发易于使用和免费的桌面操作系统做出了巨大贡献，该操作系统成为市场上专有桌面操作系统强有力的竞争者。

Ubuntu成功的原因是：项目资金来源稳定；创建了一个优秀的基于Web的基础架构，其中包含Wiki风格的文档，创造性的bug报告功能以及专业的管理方法；能够向所有感兴趣的用户免费发送CD，从而有助于分发的快速普及。
在技术方面，Ubuntu基于Debian“Sid”（不稳定分支），但是使用的是GNOME，Firefox和LibreOffice等一些著名软件包的最新版本。它使用称为“Unity”独创的用户界面。它具有可预测的6个月发布时间表，外加一个长期支持（LTS）版本，支持5年的安全更新，具体取决于版本（非LTS版本支持9个月）。 Ubuntu的其他特殊功能包括可安装的LiveDVD，独占应用和桌面主题，Windows用户的迁移助理，支持3D桌面效果等最新技术，为ATI和NVIDIA图形卡以及无线网络轻松安装专有设备驱动程序，并为非免费或专利设计的媒体编解码器提供按需支持。

**优点**：固定发布周期和支持期; 具有5年安全更新的长期支持（LTS）变体;新手友好; 丰富的文档，官方和用户无私贡献
**缺点**：与Debian有一定的兼容性问题; 频繁的重大更新可能流失一些用户，Unity用户界面被批评为更适合移动设备，而不是电脑; 非LTS版本只有9个月的安全支持软件包管理：使用DEB包的高级包工具（APT）
**其他衍生版**：Ubuntu，Kubuntu，Xubuntu，Lubuntu，Ubuntu GNOME，Ubuntu MATE，Ubuntu Budgie，Ubuntu Kylin，适用于64位（x86_64）处理器的Ubuntu Studio;
**基于Ubuntu的发行版**： Linux Mint (桌面版本), elementary OS (桌面版本), Zorin OS (桌面版本), Pinguy OS (桌面版本),Trisquel GNU/Linux (自由软件), Bodhi Linux (Enlightenment桌面)

![img](https://t12.baidu.com/it/u=4019262053,1479570461&fm=173&app=25&f=JPEG?w=480&h=384&s=240A9856CCC3577C0EAB37BF03005008)

#####**Debian GNU/Linux**
![img](https://t11.baidu.com/it/u=2720879257,703246102&fm=173&app=25&f=JPEG?w=93&h=114&s=C0047E328C7548825ED1BADA03008024)

DebianGNU/Linux于1993年首次公布。它的创始人IanMurdock的初始想法是在空闲时间创建一个由数百名志愿者开发的完全非商业项目。Debian不仅在不到十年的时间里成为了最大的Linux发行版，也是有史以来创建的最大的协作软件项目！

DebianGNU/Linux的成功：由1000多名志愿者开发，它的软件库包含近50,000个二进制包（编译为8个处理器架构），有120个基于Debian的发行版和liveCD。这些数字是任何其他基于Linux的操作系统无法比拟的。Debian主要有三个主要分支（或四个，如果包括增加稳定性的“实验”分支）：“unstable”（也称为“sid”），“testing”和“stable ”。软件包和功能的逐步整合和稳定性，以及项目完善的质量控制机制，使得Debian获得了今天可用的最佳测试和无缺陷发行版之一的声誉。
然而，这种冗长而复杂的开发风格也有一些缺点：Debian的稳定版本并不是特别新，特别是因为新的稳定版本每1–3年才会发布一次。那些喜欢最新软件包和技术的用户被迫使用Debiantesting(测试)或unstable(不稳定)分支。Debian高度民主的结构导致了有争议的决定，并引发了开发者之间的分歧，这导致没有能将项目快速推进。

**优点**：非常稳定;卓越的质量控制;包括超过30,000个软件包;支持比任何其他Linux发行版更多的处理器体系结构
**缺点**：保守–由于支持许多处理器架构，并不总是包含更新的技术;缓释周期（每1–3年稳定释放一次）;对开发者邮件列表和博客的讨论有时是不可能的软件包管理：使用DEB包的高级包工具（APT）
**可用的版本**：12个处理器架构的安装CD/DVD和liveCD映像，包括来自Intel，AMD，Power和其他所有32位和64位处理器
**基于Debian的替代方案**：Ubuntu, SparkyLinux(Enlightenment, JWM, LXDE, MATE, Openbox, Razor-qt, Xfce桌面), SolydXK (Xfce或KDE), KNOPPIX (LXDE), Tanglu(GNOME, KDE), siduction (LXQt)

![img](https://t10.baidu.com/it/u=4247544135,4124786714&fm=173&app=25&f=JPEG?w=480&h=384&s=BEC5B144D8C9136C07F8BD190100E0D3)

#####**Mageia**
![img](https://t12.baidu.com/it/u=4015674251,1456310642&fm=173&app=25&f=JPEG?w=90&h=90&s=05926532CFF559805ADD91CC0100E0E3)

Mageia可能是这个列表中的最新发行版，但它的来源可以追溯到1998年7月，当时GalDuval发布了MandrakeLinux。当时它只是一个红帽Linux的分支，KDE作为默认的桌面，更完善的硬件支持和一些用户友好的功能，加上媒体的积极评论，它获得了一定的知名度。MandrakeLinux后来变成了一个商业版本，并在2010年几乎破产之前更名为Mandriva，新管理层在没有工作的情况下，决定组建一个Mageia，这个社区项目是Mandrake和Mandriva的核心延续，或许比Mandriva本身更为合理。

Mageia主要是一个桌面版本。其最受欢迎的功能是最优秀的软件应用，精良的系统管理套件（Mageia控制中心），吸引了大量志愿者贡献者以及广泛的国际化支持。它具有最简单但功能强大的系统安装程序之一，同时还可以使用KDE或GNOME桌面和全面的语言支持。而且可以来直接从桌面安装系统，无需刻录到U盘。该发行版具有良好的软件包管理功能，具有强大的命令行选项和图形化软件管理模块，可以轻松访问数千个软件包。独特的Mageia控制中心随着每个版本的不断改进，为Linux的新手提供了一个强大的工具来配置他们的计算机的任何方面，而无需使用终端命令行。

**优点**：适合初学者;优秀的中央配置工具;支持数十种语言的开箱即用支持;可安装的Live镜像
**缺点**：与Mandriva分开之后，缺乏声誉和资源，有人担心开发者没有能力长期维持开发软件包管理：使用RPM软件包，Rpmdrake（URPMI的图形前端）的URPMI包管理器
**可用版本**：用于32位（i586）和64位（x86_64）处理器的安装DVD;可安装32位（i586）处理器的live CD
**其他选择**：OpenMandriva，ROSA

![img](https://t11.baidu.com/it/u=2542222936,888615284&fm=173&app=25&f=JPEG?w=480&h=300&s=F333EC6E1AE2D76452AE15130200E0C8)

#####**Fedora**
![img](https://t11.baidu.com/it/u=1726267342,3016641628&fm=173&app=25&f=JPEG?w=90&h=90&s=A123F1140ED5A492262AB0880300C0A8)

虽然Fedora仅在2004年9月才正式发布，但它的起源可追溯到1995年，当时它是由BobYoung和MarcEwing以RedHatLinux的名义发布的。1997年，红帽公司推出了革命性的RPM软件包管理系统，具有依赖解决方案和其他先进功能，极大地促进了分发的迅速普及并超越SlackwareLinux成为世界上使用最广泛的Linux发行版。在以后的几年中，红帽将按照正常的6个月发布时间表进行开发。

在2003年刚发布Red Hat Linux 9之后，该公司对其产品系列进行了一些根本性的改变。它保留了红帽商业产品的商标，特别是红帽企业Linux，并引入了Fedora Core（后来改名为Fedora）。Linux社区接受了“新的”发行版作为RedHatLinux的核心延续版本。Fedora重新成为一个高质量的版本，成为市场上最受欢迎的操作系统之一。与此同时，红帽公司迅速成为全球规模最大，盈利能力最强的Linux公司，拥有创新的产品阵容，出色的客户支持以及红帽认证工程师（RHCE）认证计划等其他受欢迎的计划。
尽管Fedora的方向仍然由RedHat，Inc.主要控制，无可否认，Fedora是最具创新性的分发版之一。它对Linux内核，glibc和GCC的贡献是众所周知的，它最近集成了SELinux功能，虚拟化技术，系统服务管理器，先进的日志文件系统以及其他企业级功能。但Fedora仍然缺乏明确的面向桌面的策略，以使产品更容易用于“Linux爱好者”目标以外的用户。

**优点**：高度创新;突出的安全功能;大量支持的软件包;严格遵守自由软件的理念;具有许多流行桌面环境的LiveCD的可用性
**缺点**：Fedora的优先级倾向于倾向于企业功能，而不是桌面可用性;一些出色的边缘功能，比如早期切换到KDE 4和GNOME 3，偶尔会疏远一些桌面用户**软件包管理**：使用RPM软件包的YUM图形和命令行工具
**可用的版本**：用于32位（i386）和64位（x86_64）处理器的Fedora;还有GNOME，KDE，LXDE，MATE和Xfce桌面的CD版本
**基于Fedora的替代方案**：Korora（GNOME，KDE，LXDE桌面或Xfce桌面的LiveDVD）**基于红帽的备选方案**：CentOS，Scientific Linux

![img](https://t12.baidu.com/it/u=1634229197,2209762966&fm=173&app=25&f=JPEG?w=480&h=384&s=BA87A14CCEE5936C40FF25890300F08A)

#####**openSUSE**
![img](https://t12.baidu.com/it/u=4263624323,369161543&fm=173&app=25&f=JPEG?w=90&h=54&s=62C69856CC93F8037AD5C35B03003077)

openSUSE的诞生始于1992年，当时四位德国Linux爱好者Roland Dyroff，Thomas Fehr，Hubert Mantel和Burchard Steinbild以SuSE（Software und System Entwicklung）Linux的名义推出了该项目。在早期，这家年轻的公司出售了一套包含德语版SlackwareLinux的软盘，但是在SuSELinux于1996年5月成为独立发行版4.2之后不久，在随后的几年里，开发人员采用了RPM软件包管理格式，并推出了易于使用的图形系统管理工具YaST。在欧洲和北美地区，SuSELinux的发布频繁，出色的文档和易用性使得发行日益受到欢迎。

**优点**：全面而直观的配置工具;大型软件包库，优秀的网站基础设施和印刷文档
**缺点**：2006年11月，Novell与微软的专利协议似乎使微软对Linux的知识产权声称合法化;其资源沉重的桌面设置和图形工具有时被视为“臃肿和缓慢”
**软件包管理**：使用RPM包的YaST图形和命令行实用程序
**可用的版本**：openSUSE for 32位（i386），64位（x86_64）处理器（也可安装live CD版）;适用于i586，IA64，PowerPC，s390，s390x和x86_64体系结构的SUSE Linux Enterprise Desktop/Server

![img](https://t12.baidu.com/it/u=4089630242,3668160179&fm=173&app=25&f=JPEG?w=480&h=384&s=AB31CB00C1260D1D79C8980E0300E0C0)

#####**Arch Linux**
![img](https://t10.baidu.com/it/u=344907000,1024779575&fm=173&app=25&f=JPEG?w=90&h=84&s=C092C632ADE455014F47B5460300C0E9)

ArchLinux的KISS（保持简单愚蠢）哲学是在2002年由加拿大计算机科学专业毕业生JuddVinet在2002年推出的，几年来，它一直是一个为中级和高级Linux用户设计的边缘项目。但是它“滚动更新”，只需要安装一次，然后保持一直更新，不要从头安装新的系统。这都要感谢其强大的包管理器和一个总是最新的软件库。因此，ArchLinux的“发行版”很少，而且现在只限于一个基本的安装光盘，只有在基本系统发生相当大的变化时，才会发行新的安装介质。

ArchLinux除了拥有备受推崇的“滚动发布”更新机制之外，还以其快速和强大的软件包管理器“Pacman”而闻名，能够从源代码安装软件包，并且由于其AUR基础架构，以及经过充分测试的软件包不断增加的软件库。其高度重视的文档，以及卓越的ArchLinux手册，使得一些高级Linux用户可以自行安装和定制分发。用户可以使用的强大工具意味着发行版可以无限定制到最细微的细节，并且没有两个安装可能是相同的。不利的一面是，任何滚动更新更新机制都有其危险性：人为错误，库或依赖关系丢失，已存在于存储库中的应用程序的新版本有一个尚未报告的严重错误都可能导致系统的不稳定。在Pacman升级之后，最终导致无法启动的系统是经常遇到的。因此，ArchLinux是一种需要用户警觉并具有足够的知识来解决任何这种可能的问题的发行版。此外，偶尔安装的发行版意味着有时由于重要的系统更改或在较早的Linux内核中缺少硬件支持而无法使用旧版本。

**优点**：优秀的软件管理基础设施无与伦比的定制和调整选项;一流的在线文档
**缺点**：偶尔会出现不稳定和风险**软件包管理**：使用TAR.XZ软件包的“Pacman”包管理器
**可用的版本**：64位（x86_64）处理器的最小安装CD和网络安装CD映像
**基于Arch Linux的发行版**：**Manjaro Linux**（与Cinnamon，Enlightenment，KDE，LXDE，MATE，Openbox，Xfce一起使用），Antergos（与GNOME 3一起使用），ArchBang Linux（使用Openbox的轻量级），Chakra GNU / Linux （使用KDE的Live CD），Bridge Linux（使用GNOME，KDE，LXDE和Xfce），Parabola GNU / Linux（免费软件），KaOS（使用KDE）

![img](https://t12.baidu.com/it/u=1689382931,3096975977&fm=173&app=25&f=JPEG?w=480&h=370&s=C992429A1534ED8AC2C408D8030050B2)

#####**CentOS**
![img](https://t12.baidu.com/it/u=3629618216,1909660893&fm=173&app=25&f=JPEG?w=90&h=84&s=C040F01A92F145907C40605E0300F062)

CentOS于2003年底推出，是一个社区项目，目标是将红帽企业Linux（RHEL）的源代码重建为可安装的Linux发行版，并为所有包含的软件包提供及时的安全更新。更直白地说，**CentOS是一个RHEL克隆版**。这两个发行版之间唯一的技术差异就是品牌CentOS用自己的所有代码取代了所有的红帽商标和标识。

CentOS经常被看作是一个可靠的服务器发行版。它配备了经过良好测试和稳定的Linux内核和软件包，构成了其母公司RedHatEnterpriseLinux的基础。尽管是志愿者维护的一个社区项目，但它已经赢得了市场上更高端服务器产品（尤其是经验丰富的Linux系统管理员）的稳定，免费替代品的声誉。CentOS也适合作为企业桌面解决方案，特别是在稳定性，可靠性和长期支持优于最新软件和功能的地方。像RHEL一样，CentOS支持大约7 – 10年的安全更新。

尽管有其优势，CentOS可能不是所有部署方案中的最佳解决方案。主要的CentOS版本是在RHEL版本的基础上发布的，每2–3年才会发布一次，而小版本（例如5.1）则以6到9个月为间隔。小发行通常不包含任何主要功能（虽然有时包括支持更新的硬件），只有少数软件包可能会更新到新版本。Linux内核，基本系统和大多数应用程序版本保持不变，但偶尔也可以在试验的基础上提供重要软件包（例如LibreOffice或Firefox）的新版本。当然也有一个分支项目，CentOS也为其发行版的用户构建了更新的软件包，但是包含它们的软件库默认是不启用的，因为它们可能会破坏上游的兼容性。

**优点**：非常稳定和可靠;免费下载和使用;有7年以上的免费安全更新;
**缺点**：缺乏最新的Linux技术;有时该项目未能履行其及时提供安全更新和新稳定版本的承诺
**软件包管理**：使用RPM软件包的YUM图形和命令行工具**可用版本**：用于i386和x86_64处理器的安装DVD和可安装的Live CD（GNOME）;旧版本（3.x和4.x）也可用于Alpha，IA64和IBM z系列（s390，s390x）处理器。
**其他RHEL克隆和基于CentOS的发行版**：Scientific Linux，Springdale Linux，SME服务器，Rocks Cluster Distribution，Oracle Enterprise Linux

![img](https://t10.baidu.com/it/u=2302503993,2397221342&fm=173&app=25&f=JPEG?w=480&h=384&s=8864D714933F412E5A64EC70030060B3)

#####**PCLinuxOS**
![img](https://t10.baidu.com/it/u=3891374169,2763480819&fm=173&app=25&f=JPEG?w=90&h=81&s=AC03E11496D6A79444D7D09C0300E0AA)

PCLinuxOS于2003年由比尔·雷诺兹（BillReynolds）首先宣布，被称为“Texstar”。在创建自己的发行版之前，Texstar已经是MandrakeLinux社区用户的知名开发人员构建的最新的RPM包，并提供免费下载。2003年，他决定建立一个新的发行版，最初基于MandrakeLinux，但有几个显著的可用性改进。理念是应该**对初学者是友好的，具有专有内核模块，浏览器插件和媒体编解码器的开箱即用的支持，并应作为一个简单直观的图形安装程序的Live CD**。

几年后的发展，PCLinuxOS正在迅速接近其预期的状态。就可用性而言，该项目为大多数Windows到Linux移民希望从他们的新操作系统中获得的许多技术提供了开箱即用的支持。在软件方面，**PCLinuxOS是一个面向KDE的发行版，具有定制且始终最新版本的流行桌面环境**。不断增长的软件存储库包含其他桌面，并为许多常见任务提供各种各样的桌面软件包。对于系统配置，PCLinuxOS保留了很多Mandriva优秀的控制中心，但是用APT和Synaptic（一个图形化的包管理前端）取代了它的包管理系统。

不利的一面是，PCLinuxOS缺乏任何形式的路线图或发布目标。尽管越来越多的社区参与这个项目，大多数的发展和决策仍然掌握在Texstar的手中，他们在判断发布的稳定性时倾向于保守的一面。因此，PCLinuxOS的开发过程往往是艰巨的。例如，尽管频繁要求64位版本，但开发者直到最近才开始生产64位版本。此外，该项目不提供任何安全建议，而是依靠用户通过所包括的管理工具保持系统最新的状态。

**优点**：对图形驱动程序，浏览器插件和媒体编解码器的开箱即用支持;滚动更新机制;最新的软件
**缺点**：对非英语语言没有开箱即用的支持;缺乏发布计划和安全建议
**软件包管理**：使用RPM包的高级包工具（APT）
**可用的版本**：KDE，完整的Monty，KDE Minime，LXDE，LXDE Mini，Openbox，Openbox盆景，用于64位（x86_64）处理器体系结构的KDE

![img](https://t12.baidu.com/it/u=2078823767,850788828&fm=173&app=25&f=JPEG?w=480&h=384&s=0B95C30244BEAB3E18E65BB70300B004)

#####**Slackware Linux**
![img](https://t12.baidu.com/it/u=3895132502,1204949935&fm=173&app=25&f=JPEG?w=89&h=84&s=ED02E41008F5518251A3CA8C0300E0AA)

由Patrick Volkerding于1992年创建的Slackware Linux是**现存最古老的Linux发行版**。从现在停止开发的SLS项目中分离出来，Slackware 1.0拥有24个软盘，并建立在Linux内核版本0.99pl11-alpha之上。它很快成为最受欢迎的Linux发行版，据估计1995年其市场份额占所有Linux安装量的80％。随着Red Hat Linux和其他更友好的发行版的出现，其受欢迎程度急剧下降，但Slackware Linux仍然是面向更技术导向的系统管理员和桌面用户的一个备受赞赏的操作系统。

SlackwareLinux是一个**高度技术性的，干净的发行版**，只有非常有限的自定义实用程序。它使用一个**简单的，基于文本的系统安装程序和一个比较原始的软件包管理系统**，它不能解决软件依赖问题。因此，Slackware被认为是目前可用的最干净和最不稳定的发行版之一–缺乏特定于Slackware的增强功能可以降低新问题引入系统的可能性。所有配置都是通过编辑文本文件完成的。 

在当今世界，SlackwareLinux越来越成为构建新的定制解决方案的“核心系统”，而不是具有各种支持的软件的完整发行版。唯一的例外是服务器市场，Slackware仍然很受欢迎，虽然在这里，发行版的**复杂升级过程和缺乏官方支持**的安全更新自动化工具使得它日益失去竞争力。Slackware对系统基本组件的保守态度意味着它需要大量的手动安装后工作，才能被调整到现代桌面系统。

**优点**：高度稳定，干净，基本上没有错误，坚决遵守UNIX原则
**缺点**：正式支持的应用程序数量有限;在基础包选择方面保守;复杂的升级程序
**软件包管理**：使用TXZ软件包的“pkgtool”**可用版本**：适用于32位（i486）和64位（x86_64）处理器的安装CD和DVD
**基于Slackware的替代品**：Zenwalk Linux（桌面），Salix（桌面，Live CD），Porteus（带有KDE，LXDE，MATE，Razor-qt或Xfce的live CD），VectorLinux
**其他类似发行版本**：Arch Linux，Frugalware Linux

![img](https://t12.baidu.com/it/u=745484576,2341252982&fm=173&app=25&f=JPEG?w=480&h=384&s=603F30D4E316A23E9497C08F0300208B)

#####**FreeBSD**
![img](https://t10.baidu.com/it/u=2776863579,258761220&fm=173&app=25&f=JPEG?w=89&h=85&s=44D6589A88F533806B9AFAAE03007029)

FreeBSD是**AT＆TUNIX通过BerkeleySoftwareDistribution（BSD）的间接后裔**，它的历史可以追溯到1993年。与Linux发行版不同，Linux发行版被定义为由Linux内核和数千个软件应用程序组成的集成软件解决方案，而FreeBSD是一个紧密集成的操作系统，**由BSD内核和所谓的“用户空间”构成**（因此即使没有额外的应用程序也可以使用）。一旦安装在普通的计算机系统上，这种区别就不明显了 – 就像许多Linux发行版一样，大量易于安装的（大部分）开源应用程序也是可支持FreeBSD核心。

FreeBSD已经发展成为一个**快速，高性能和非常稳定的操作系统，尤其适用于Web服务和类似的任务**。许多具有关键任务计算基础设施的大型网络搜索引擎和组织已经在他们的计算机系统上部署和使用FreeBSD多年。与Linux相比，FreeBSD是在一个限制少得多的许可证下分发的，它允许为任何目的而实际上不受限制的重用和修改源代码。即使是苹果公司的Mac OSX也是从FreeBSD派生出来的。除了核心操作系统之外，该项目还提供了超过24,000个二进制和源代码形式的软件应用程序，以方便安装在FreeBSD核心上。

虽然FreeBSD当然可以用作桌面操作系统，但是它与这个部门中流行的Linux发行版并没有很好的比较。文本模式系统安装程序在硬件检测或系统配置方面提供的功能很少，在安装后的设置中将大部分配置工作留给了用户。在对现代硬件的支持方面，FreeBSD通常落后于Linux，尤其是在支持诸如无线网卡或数码相机等，高端的台式机和笔记本电脑方面。那些试图在桌面或工作站上开发项目的用户，以充分利用FreeBSD的速度和稳定性，而不是FreeBSD本身。

**优点**：快速稳定;安装24000多个软件应用程序（或“端口”）的可用性;非常好的文档
**缺点**：在支持新颖和异乎寻常的硬件方面，往往落后于Linux，商业应用程序的可用性有限;缺少图形化配置工具
**软件包管理**：使用二进制包或基于源的“端口”（TBZ）的完整命令行包管理基础架构，
**可用版本**：用于AMD64，ARM / ARMEL，i386，IA64，MIPS / MIPSEL，PC98 PowerPC，SPARC64和Xbox处理器的安装CD
**基于FreeBSD的替代方案**：PC-BSD（桌面），GhostBSD（带有GNOME的live DVD）
**其他BSD的替代品**：OpenBSD，NetBSD，DragonFly BSD

![img](https://t10.baidu.com/it/u=738469029,1955729914&fm=173&app=25&f=JPEG?w=480&h=384&s=CDAABC5460BE373E9596C88D0300A0C9)

### 1.1.5 Linux系统的特点与应用

Linux操作系统一直是广泛应用于的操作系统，许多软硬件厂商都设计开发采用Linux操作系统的产品。而Linux系统能大范围的应用于，也是因为Linux系统所具有的特点优势。今天小编就来介绍下使用Linux系统的特点。

#### （1）**Linux**系统是免费的自由软件
Linux系统是通过公共许可协议GPL的自由软件。这种软件具有两个特点，一是开放源代码并免责提供，二是开发者可以根据自身需要自由修改、复制和发布程序的源码。因此，用户可以从互联网上很方便地免费下载并使用Linux操作系统，不需要担心版权问题。

####（2）良好的硬件平台可移植性
硬件平台可移植性是指将操作系统从一个硬件平台转移到另一个硬件平台时，只需改变底层的少量代码，无需改变自身的运行方式。Linux系统最早诞生于PC机环境，一系列版木都充分利用了X86 CPU的任务切换能力，使X86 CPU的效能发挥得淋漓尽致。另外，Linux系统几乎能在所有主流CPU搭建的体系结构上运行，包括 Intel/AMD、HP-PA、MIPS、Powerpc、 ULTRASPARC和 ALPHA等，其伸缩性超过了所有其他类型的操作系统。

####（3）完全符合**POSIX**标准
POSⅨ也称为可移植的Linux操作系统接口，是由ANSI和ISO制订的一种国际标准，它在源代码级别上定义了一组最小的Linux操作系统接口。Linux系统遵循这一标准，使得它和其他类型的Linux系统之间可以很方便地相互移植平台上的应用软件。

####（4）具有良好的图形用户界面
Linux系统具有类似于Windows操作系统的图形界面，其名称是X-Window系统。X-Window是一种起源于Linux操作系统的标准图形界而，它可以为用户提供一种具有多种窗口管理功能的对象集成环境。

####（5）具有强大的网络功能
由于Linux系统是依靠互联网平台迅速发展起来的，所以也具有强大的网络功能。它在内核中实现了 TCP/TP协议簇，提供了对 TCP/TP协议簇的支持。同时，它还可以支持其他各种类型的通信协议，如 IPX'SPX、 Apple Talk、PP、SLP和ATM等。

####（6）丰富的应用程序和开发工具
由于 Linux系统具有良好的可移植性，目前绝大部分其他Linux系统下使用的流行软件都已经被移植到 Linux系统中。另外，由于 Linux得到了IBM、 Intel、 Oracle及 Syabse等知名公司的支持，这些公司的知名软件也都移植到了 Linux系统中，因此， Linux获得越来越多的应用程序和应用开发工具。

####（7）良好的安全性和稳定性
Linux系统采取了多种安全措施，如任务保护机制、审计跟踪、核心报校、访问授权等，为网络多用户环境中的用户提供了强大的安全保障。由于Linux系统的开放性及其他一些原因，使其对计算机病具有良好的防御机制， Linux平台基木上不需要安装防病毒软件。另外，Linux系统具有极强的稳定性，可以长时间稳定地运行。

## 1.2 利用VMware Workstation搭建实验环境

### 1.2.1 VMware Workstation的基本操作

1. vmware workstation的编辑功能，在虚拟机关闭的情况下能够调整内存大小、CPU个数、网络连接方式，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/3b03be7aa010bc33bb14340e92efa25f0d143f81.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

2. 点击“编辑”>>"虚拟网络参数"，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/efb861bd4c7c34b3596d330f5841037de0373181.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

3. 能够添加和删除网卡，对网卡的IP地址进行编辑，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/d4071b96b814f4d0c62fc867cdfe474ec3832381.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

4. 虚拟机的快照功能，及时系统崩溃了，能恢复到创建快照的还原点，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/a99a494afa32939caddbdf075719ce2c5a1b1581.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

5. 点击“编辑”>>"安装虚拟机工具"，能够在虚拟机和宿主机直接进行复制粘贴操作，包括文字和文件，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/6834ecc4ec995943942d484b95425d6b05d10481.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

6. 点击“虚拟机”>>"可移动设备"，能将物理机的移动设备提供给虚拟机使用，比如移动硬盘、光驱等，如图。

   ![vmware workstation使用方法](https://exp-picture.cdn.bcebos.com/acfda02f4770461841f6e48eb08602214e577681.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

### 1.2.2 在虚拟机中安装Linux系统
所谓虚拟机（virtual machine），就是通过软件技术虚拟出来的一台计算机，它在使用层面和真实的计算机并没有什么区别。常见的虚拟机软件有 VMware Workstation（简称 VMware）、VirtualBox、Microsoft Virtual PC 等，其中 VMware 市场占有率最高，所以本节以 **VMware** 为例来讲解 Linux 的安装。

![VMware虚拟机](http://c.biancheng.net/uploads/allimg/190314/2-1Z314135355923.jpg)


VMware可以使你在一台计算机上同时运行多个操作系统，例如同时运行Windows、Linux和MacOS。在计算机上直接安装多个操作系统，同一个时刻只能运行一个操作系统，重启才可以切换；而Vmware可以同时运行多个操作系统，可以像Windows应用程序一样来回切换。站在使用者的角度讲，虚拟机系统和真实安装的系统是一样的，甚至可以在一台计算机上将几个虚拟机系统连接为一个局域网或连接到互联网。在虚拟机系统中，每一台虚拟产生的计算机都被称为“虚拟机”，而用来存储所有虚拟机的计算机则被称为“宿主机”。例如，你的 Windows 系统就是宿主机，而 VMware 安装的 Linux 则为虚拟机。

## VMware下载和安装

绝大多数初学者使用的是 Windows，所以本节只讲解在 Windows 下安装 VMware 和 Linux。VMware 有两个版本，分别是 VMware Workstation Pro 和 VMware Workstation Player。- Player 是免费版本，只能用于非商业用途，适合个人学习。- Pro 是商业版本，功能最强大，付费以后才能使用。

我们从互联网上找到了一个带密钥的 Pro 版本，并放在了百度网盘，大家可以无限制的使用：
VMware Workstation Pro 下载地址：
https://pan.baidu.com/s/1XXhFFh0Fx0vzvcd1A543Yg，提取码：2o19（下载得到的压缩包中含有 VMware 安装所需的秘钥，亲测有效，可放心使用）

> VMware 对计算机的硬件配置要求比较高，配置低了虚拟机会很慢，甚至不能运行。理论上，配置越高越好，现在主流的计算机配置都可以达到运行 VMware 的要求。
由于 VMware 的安装过程比较简单，与安装普通软件无异，因此不再过多阐述。这里假设读者已经下载并已安装好 VMware，接下来直接开始使用 VMware 安装 Linux 系统。

## VMware 安装 Linux 系统

启动 VMware，进入其主界面，如图 1 所示。

![VMware主界面](http://c.biancheng.net/uploads/allimg/190313/2-1Z31313391SR.jpg)
图 1 VMware 主界面

点击“创建新的虚拟机”，进入虚拟机设置向导界面，如图 2 所示，这里建议初学者选择“典型（推荐）”。

![虚拟机设置向导界面](http://c.biancheng.net/uploads/allimg/190313/2-1Z3131339362Y.jpg)
图 2 虚拟机设置向导界面

点击“下一步”，进入“安装操作系统”界面，若初学者已提前准备好 Linux 系统的映像文件（.iso 文件），此处可选择“安装程序光盘映像文件”，并通过“浏览”按钮找到要安装 Linux 系统的 iso 文件；否则选择“稍后安装操作系统”，如图 3 所示。

![安装客户机操作系统](http://c.biancheng.net/uploads/allimg/190313/2-1Z313134004B0.jpg)
图 3 安装客户机操作系统

建议初学者提前下载好 CenOS 映像系统，给大家提供 CentOS 6.5 映像文件迅雷下载地址（点击链接或复制链接到迅雷即可开始下载）：
- 32 位 CentOS 6.5 映像下载：<http://archive.kernel.org/centos-vault/6.5/isos/i386/CentOS-6.5-i386-bin-DVD1.iso>
- 64 位 CentOS 6.5 映像下载：<http://archive.kernel.org/centos-vault/6.5/isos/x86_64/CentOS-6.5-x86_64-bin-DVD1.iso>

点击“下一步”，进入“选择客户机操作系统”，选择“Linux”，并在“版本”下拉列表框中选择要安装的对应的 Linux 版本，这里选择“CentOS 6”，如图 4 所示。

![选择客户机操作系统](http://c.biancheng.net/uploads/allimg/190313/2-1Z3131340523V.jpg)
图 4 选择客户机操作系统

继续“下一步”，进入“命名虚拟机”界面，给虚拟机起一个名字（如“CentOS 6.5”），然后单击“浏览”按钮，选择虚拟机系统安装文件的保存位置，如图 5 所示。

![命名虚拟机](http://c.biancheng.net/uploads/allimg/190313/2-1Z313134110361.jpg)
图 5 命名虚拟机

单击"下一步"按钮，进入"指定磁盘容量"界面。默认虚拟硬盘大小为 20GB（虚拟硬盘会以文件形式存放在虚拟机系统安装目录中）。虚拟硬盘的空间可以根据需要调整大小，但不用担心其占用的空间，因为实际占用的空间还是以安装的系统大小而非此处划分的硬盘大小为依据的。比如你设定了硬盘容量为20GB，但是安装Linux只用了4GB，那么实际上只会在你的Windows分区中占用4GB的空间，占用空间会随着虚拟机系统使用的空间增加而增加。此“指定磁盘容量”界面保持默认设置即可，如图 6 所示。

![指定磁盘容量界面](http://c.biancheng.net/uploads/allimg/190313/2-1Z3131341392M.jpg)
图 6 指定磁盘容量界面

接下来进入“已准备好创建虚拟机”界面，确认虚拟机设置，不需改动则单击"完成"按钮，开始创建虚拟机，如图 7 所示。

![img](http://c.biancheng.net/uploads/allimg/180927/2-1P92G05509264.jpg)
图 7 已准备好创建虚拟机

这里，我们可以略做调整，单击"自定义硬件"按钮进入硬件调整界面。为了让虚拟机中的系统运行速度快一点，我们可以选择"内存"调整虚拟机内存大小，但是建议虚拟机内存不要超过宿主机内存的一半。CentOS6.x 最少需要 628MB 及以上内存分配，否则会开启简易安装过程，如图 8 所示。

![img](http://c.biancheng.net/uploads/allimg/180927/2-1P92G055391A.jpg)
图 8 定制硬件

选择“新CD/DVD(IDE)”可以选择光驱配置。如果选择“使用物理驱动器”，则虚拟机会使用宿主机的物理光驱；如果选择“使用 ISO 映像文件”，则可以直接加载 ISO 映像文件，单击“浏览”按钮找到 ISO 映像文件位置即可，如图 9 所示。

![img](http://c.biancheng.net/uploads/allimg/180927/2-1P92G0561A28.jpg)
图 9 光盘配置

选择"网络适配器"将进入 VMware 新手设置中最难以理解的部分——设置网络类型，如图 10 所示。此设置较复杂，不过网络适配器配置在虚拟机系统安装完成后还可以再行修改。

![img](http://c.biancheng.net/uploads/allimg/180927/2-1P92G05640305.jpg)
图 10 网络适配器配置

VMware 提供的网络连接有 5 种，分别是"桥接模式"、"NAT 模式"、"仅主机模式"、"自定义"和"LAN 区段"：

- 桥接模式：相当于虚拟机的网卡和宿主机的物理网卡均连接到虚拟机软件所提供的 VMnet0 虚拟交换机上，因此虚拟机和宿主机是平等的，相当于一个网络中的两台计算机。这种设置既可以保证虚拟机和宿主机通信，也可以和局域网内的其他主机通信，还可以连接 Internet，是限制最少的连接方式，推荐新手使用。
- NAT 模式：相当于虚拟机的网卡和宿主机的虚拟网卡 VMnet8 连接到虚拟机软件所提供的 VMnet8 虚拟交换机上，因此本机是通过 VMnet8 虚拟网卡通信的。在这种网络结构中，VMware 为虚拟机提供了一个虚拟的 NAT 服务器和一个虚拟的 DHCP 服务器，虚拟机利用这两个服务器可以连接到 Intemet。所以，在正常情况下，虚拟机系统只要设定自动获取 IP 地址，就能既和宿主机通信，又能连接到 Internet了。但是这种设置不能连接局域网内的其他主机。
- 仅主机模式：宿主机和虚拟机通信使用的是 VMware 的虚拟网卡 VMnet1，但是这种连接没有 NAT 服务器为虚拟机提供路由功能，所以仅主机网络只能连接宿主机，不能连接局域网，也不能连接 Internet 网络。
- 自定义网络：可以手工选择使用哪块虚拟机网卡。如果选择 Vmnet1，就相当于桥接网络；如果选择 VMnet8，就相当于 NAT 网络。
- LAN 区段：这是新版 VMware 新增的功能，类似于交换机中的 VLAN（虚拟局域网），可以在多台虚拟机中划分不同的虚拟网络。

以上对于 VMware 网络的描述，读者看完了可能会有点困惑。简单总结—下，在 VMware 安装好后，会生成两个虚拟网卡 VMnet1 和 VMnet8 (在 Windows 系统的"网络连接"中可以査看到），如图 11 所示。

![img](http://c.biancheng.net/uploads/allimg/180927/2-1P92G05S0605.jpg)
图 11 虚拟网卡

其中常用设置有以下 2 种：
1. 需要宿主机的 Windows 和虚拟机的 Linux 能够进行网络连接，使用"桥接模式"（桥接时，Linux 也可以访问互联网，只是虚拟机需要配置和宿主机 Windows 同样的联网环境）；
2. 需要宿主机的 Windows 和虚拟机的 Linux 能够进行网络连接，同时虚拟机的 Linux 可以通过宿主机的 Windows 连入互联网，使用"NAT模式"。

硬盘配置设置完成后，点击图 7 中的“完成”按钮，就成功创建了一台虚拟机！对于在图 3 中提前下载好 CentOS 映像并作相应设置的读者，此时 VMware 会直接启动 Linux CentOS 系统，如图 12 所示。

![VMware启动Linux系统](http://c.biancheng.net/uploads/allimg/190313/2-1Z313134224516.jpg)
图 12 VMware 启动 Linux 系统

而在图 3 中选择“稍后安装操作系统”的读者，此时必须先下载某个 Linux 映像文件，并通过“编辑虚拟机设置->CD/DVD（IDE）”中，选择“使用ISO映像文件”，手动添加 iso 文件，然后点击“确定”即可手动开启 Linux 系统。如图 13 所示。

![img](http://c.biancheng.net/uploads/allimg/190313/2-1Z313134255L5.gif)
	经过以上几步，我们就成功地用 VMware 虚拟机安装好了 Linux 系统。

### 1.2.3 VMware Workstation的高级设置

可以为选定的虚拟机配置高级设置以禁用内存页面修整，启用模板模式，启用自动磁盘清理以及启用基于虚拟化的安全性 (VBS)。如果要为所选虚拟机配置其他高级选项，请选择虚拟机 > 设置，单击选项选项卡，然后选择高级。

#### 网络类型
NAT模式：公网IP地址，私有IP地址

## 1.3 Linux系统的基本操作

### 1.3.1 什么是Shell

在计算机科学中，Shell是指“为使用者提供操作界面”的软件（命令解析器）。它类似于DOS下command.com和后来的cmd.exe。它接收用户命令，然后调用相应的应用程序。同时它又是一种程序设计语言。它分为两大类：一类是图形界面shell。二类是命令行式shell。

### 1.3.2 启动Shell

Shell脚本的执行方式一般有三种：（1）bash script-name 或者 sh script-name；（2）path/script-name或者./script-name；（3）source script-name或者. script-name。

### 1.3.3 命令提示符

进入带有开发桌面的Linux系统，右键点击桌面出现菜单，点击其中的打开终端即可进入界面。

### 1.3.4 Shell命令格式

在我的CentOS-8.1 64位中，默认的格式为：

```bash
[august@localhost ~]$ 
```

### 1.3.5 关机与重启命令

#### 关机命令：

1、halt 立刻关机；
2、poweroff 立刻关机；
3、shutdown -h now 立刻关机(root用户使用)；
4、shutdown -h 10 10分钟后自动关机；
如果是通过shutdown命令设置关机的话，可以用shutdown -c命令取消关机。

#### 重启命令：

1、reboot；
2、shutdown -r now 立刻重启(root用户使用)；
3、shutdown -r 10 过10分钟自动重启(root用户使用)；
4、shutdown -r 20:35 在时间为20:35时候重启(root用户使用)；
如果是通过shutdown命令设置重启的话，可以用shutdown -c命令取消重启。

### 1.3.6 远程登录Linux

xshell 

ssh 目标主机的IP地址

## 1.4 思考与练习

# 第2章 文件和目录管理

## 2.1 Linux设计思想

1.该程序应小而具体。该程序应尽可能小，并且只关注一件事。不要开发似乎有用但在90%的情况下不使用的功能。
2.程序不仅需要考虑性能，程序的可移植性更为重要，shell和perl，python等脚本比c具有更好的可移植性。
3.一切都是文件，请尝试使用文本文件存储数据，避免使用二进制文件，因为文本文件具有很高的可读性，并且已经有许多处理工具，例如awk，sed，grep等。
4.让每个程序成为一个过滤器。程序需要与其他工具结合使用。管道支持非常重要。
5.批处理执行需要考虑任何程序，并尽量避免强制的用户交互或界面。

## 2.2 文件和目录的相关概念

### 2.2.1 Linux的目录结构

```bash
[august@localhost ~]$ ls /
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
```

1.bin，存放常用命令的目录，如vi，su。

2.boot，存放引导系统启动的相关文件。

3.dev, 该目录下存放的是 Linux 的外部设备。

4.etc,用来存放所有的系统管理所需要的配置文件和子目录。

5.home,用户的主目录在 Linux 中，每个用户都有一个自己的目录，一般目录名是以用户的账号命名的。

6.lib,这个目录里存放着系统最基本的动态连接共享库，其作用类似于 Windows 里的 DLL 文件。几乎所有的应用程序都需要用到这些共享库。

7.lib64,可以uname -a查看下内核是否位64位的。

8.media，linux 系统会自动识别一些设备，例如U盘、光驱等等，当识别后，Linux 会把识别的设备挂载到这个目录下。

9.mnt，系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将光驱挂载在 /mnt/ 上，然后进入该目录就可以查看光驱里的内容了。

10.opt，这是给主机额外安装软件所摆放的目录。比如你安装一个ORACLE数据库则就可以放到这个目录下。默认是空的。

11.proc，它是一种伪文件系统（也即虚拟文件系统），存储的是当前内核运行状态的一系列特殊文件，这个目录是一个虚拟的目录，它是系统内存的映射，我们可以通过直接访问这个目录来获取系统信息。

12.root，该目录为系统管理员，也称作超级权限者的用户主目录。

13.run，是一个临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。如果你的系统上有 /var/run 目录，应该让它指向 run。

14.sbin，这里存放的是系统管理员使用的系统管理程序。

15.srv，该目录存放一些服务启动之后需要提取的数据。

16.sys，这是linux2.6内核的一个很大的变化，该目录下安装了2.6内核中新出现的一个文件系统。

17.tmp，这个目录是用来存放一些临时文件的。

18.usr，这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于 windows 下的 program files 目录。

19.var，这个目录中存放着在不断扩充着的东西，我们习惯将那些经常被修改的目录放在这个目录下。包括各种日志文件。

### 2.2.2 根目录和家目录

1、根目录：

```bash
[august@localhost ~]$ cd /
[august@localhost /]$ ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
```

/是根目录，cd /进入根目录后，我们使用 ls 命令可以看见很多目录。

2、家目录：

```bash
[august@localhost /]$ cd ~
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面
[august@localhost ~]$ pwd
/home/aguust
```

~代表home目录，pwd表示查看普通用户的家目录。

### 2.2.3 绝对路径和相对路径

1、绝对路径：

从根目录开始，依次将各级子目录的名字组合起来，形成的路径就称为某个文件的绝对路径。例如，根目录（/）下有目录usr，usr目录下有子目录bin，bin目录下有文件chsh，则chsh文件的绝对路径就是：/usr/bin/chsh。

2、相对路径：

相对当前所在路径的位置，例如当前所在的位置为/usr，也就是在根目录的usr子目录下，则chsh文件相对当前位置的路径为：bin/chsh。

总结：在路径中一些特殊符号的说明：。 表示用户所处的当前目录；…… 表示上级目录；~ 表示当前用户自己的家目录；~USER 表示用户名为USER的家目录，这里的USER是在/etc/passwd中存在的用户名。

## 2.3 文件和目录操作命令

### 2.3.1 ls命令—列表显示

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面
[august@localhost ~]$ cd -
/
[august@localhost /]$ ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
[august@localhost /]$ ls -la
总用量 24
dr-xr-xr-x.  17 root root  224 3月  28 07:29 .
dr-xr-xr-x.  17 root root  224 3月  28 07:29 ..
lrwxrwxrwx.   1 root root    7 5月  10 2019 bin -> usr/bin
dr-xr-xr-x.   6 root root 4096 3月  28 07:40 boot
drwxr-xr-x.  20 root root 3260 3月  28 08:11 dev
drwxr-xr-x. 135 root root 8192 3月  28 07:40 etc
drwxr-xr-x.   3 root root   20 3月  28 07:37 home
lrwxrwxrwx.   1 root root    7 5月  10 2019 lib -> usr/lib
lrwxrwxrwx.   1 root root    9 5月  10 2019 lib64 -> usr/lib64
drwxr-xr-x.   2 root root    6 5月  10 2019 media
drwxr-xr-x.   3 root root   18 3月  28 07:32 mnt
drwxr-xr-x.   2 root root    6 5月  10 2019 opt
dr-xr-xr-x. 258 root root    0 3月  28 08:11 proc
dr-xr-x---.   5 root root  184 3月  28 07:41 root
drwxr-xr-x.  42 root root 1220 3月  28 08:12 run
lrwxrwxrwx.   1 root root    8 5月  10 2019 sbin -> usr/sbin
drwxr-xr-x.   2 root root    6 5月  10 2019 srv
dr-xr-xr-x.  13 root root    0 3月  28 08:11 sys
drwxrwxrwt.  17 root root 4096 3月  28 08:17 tmp
drwxr-xr-x.  12 root root  144 3月  28 07:29 usr
drwxr-xr-x.  21 root root 4096 3月  28 07:40 var

```



### 2.3.2 touch命令—创建空文件

在某个目录下创建一个空文件，命令为 “touch [选项] [文件]” 例如我在家目录下创建一个名叫empty的空文件，可以使用指令：

```bash
[august@localhost /]$ cd ~
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面
[august@localhost ~]$ touch empty
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  empty
```



### 2.3.3 mkdir命令—创建目录

mkdir的指令格式：mkdir [-p] 目录名    

①当前默认目录下使用指令创建目录：

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  empty
[august@localhost ~]$ mkdir Create
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  empty

```

②使用 mkdir 的参数 -p 递归创建（需要进入更高的权限）：

```bash
[august@localhost ~]$ su root
密码：
[root@localhost aguust]# mkdir -p /Create/work
[root@localhost aguust]# cd /Create
[root@localhost Create]# ls
work
```

这里在Create目录下创建了work子目录。

### 2.3.4 rmdir命令—删除空目录

rmdir的指令格式：rmidr [-p] 目录名        

rmdir 命令只能删除空目标，所以能不能删除完全取决于是否是空目录。我把上面创建的空目录Create进行删除操作。

```bash
[august@localhost ~]$ rmdir Create
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  empty
```



### 2.3.5 cp命令—复制文件或目录

cp 命令的基本格式：cp [选项] 源文件 目标文件

首先创建一个空目录 touch ，把空目录 touch 复制到 test目录下：

```bash
[august@localhost ~]$ mkdir test
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  empty  test  touch
[august@localhost ~]$ cp -r touch test/
[august@localhost ~]$ cd test/
[august@localhost test]$ ls
touch
```

### 2.3.6 mv命令—移动文件或目录

mv 指令可以在不同的目录之间移动文件或目录，也可以对文件和目录进行重命名。该命令的基本格式：mv [选项] 源文件 目标文件 



### 2.3.7 rm命令—删除文件或目录

rm 是强大的删除命令，它可以永久性地删除文件系统中指定的文件或目录。在使用 rm 命令删除文件或目录时，系统不会产生任何提示信息。此命令的基本格式：rm [选项] 文件或目录。

1、删除家目录下的empty文本文件：

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  empty  test  touch
[august@localhost ~]$ rm empty
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  test  touch

```

2、删除目录 touch 以及子目录中的所有文件：

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  test  touch
[august@localhost ~]$ rm -r touch
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  test
```

### 2.3.8 通配符和扩展符

1、常用的通配符：

```
* 代表0个或者多个特殊字符
? 代表的是任意一个字符
[]代表的是中括号中的任意一个
[-]代表的是一个范围
[^]^是反向选择符号从字面意思可以知道也就是非的意思
---------------------------------------
常用的特殊符号:
# 注释说明
$ 变量符号
\ 转义字符
； 连续命令执行分割符号
{} 中间是命令块
'' 反点号中间的先执行
/ 目录符号，路径分割
& 把作业放到后台去执行
~ 用户的主文件夹
！逻辑运算上的非
```

2、常用的扩展符：

```
1.路径名扩展：【*】【[.]】【?】等，通过通配符实现的扩展机制
2.波浪线扩展：【~用户名】扩展为指定用户的主目录名，默认为当前用户主目录
3.算术扩展：【$((expression))】支持整数的加 (+) 减 (-) 乘 (*) 除 (/) 取余 (%) 和取幂 (**)
4.花括号扩展：【{a,b,c}】【{a…c}】用花括号里的模式，扩展出相应的字符串
5.参数扩展：【$变量】，将变量扩展为对应的字符串
6.命令替换：【$(命令)】将命令的输出作为一个扩展模式
7.单词分割：空白分隔的参数直接只会保留一个空格
```

### 2.3.9 文件和目录操作技巧

```
1：文件操作常用命令

   1、文件（文件夹）清单命令  ls

   2、文件（文件夹）复制命令  cp -R

   3、文件（文件夹）移除命令  mv

   4、文件（文件夹）删除命令  rm -rf

2：目录操作常用命令

   1、创建目录  mkdir

   2、删除目录  rm -rf

   3、切换目录  cd 

3：文件和目录权限管理

   1、更改文件（目录）权限 chmod -R 

   2、更改文件（目录）属主 chown -R 

4：查找文件命令  find 目录 -name 

   1、查找相关名字的文件或者目录  find 目录 -name '名字'

   2、查找相关名字的文件中包含某些内容的文件 find 目录 -type f -name | xrags grep '内容'
```



## 2.4 文件内容操作命令

### 2.4.1 cat命令—显示文本文件的内容

使用 cat 命令显示work1中的文本内容：

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  test  work1
[august@localhost ~]$ cat work1
I am a student
```

cat 的一些常用参数：

```bash
-A, --show-all            等于-vET 
-b, --number-nonblank   对非空输出行编号
-e                        等于-vE 
-E, --show-ends           在每行结束处显示"$" 
-n, --number    对输出的所有行编号
-s, --squeeze-blank       不输出多行空行 
-t                        与-vT 等价 
-T, --show-tabs           将跳格字符显示为^I 
-u                        (被忽略) 
-v, --show-nonprinting    使用^ 和M- 引用，除了LFD和 TAB 之外 
--help     显示此帮助信息并退出
--version    显示版本信息并退出 
```



### 2.4.2 more命令和less命令—分页显示文件内容

more 命令的格式：more [参数] 文件

```bash
 参数选项：
 -d        显示帮助，而不是响铃
  -f        统计逻辑行数而不是屏幕行数
  -l        抑制换页(form feed)后的暂停
  -p        不滚屏，清屏并显示文本
  -c        不滚屏，显示文本并清理行尾
  -u        抑制下划线
  -s        将多个空行压缩为一行
  -NUM      指定每屏显示的行数为 NUM
  +NUM      从文件第 NUM 行开始显示
  +/STRING  从匹配搜索字符串 STRING 的文件位置开始显示
  -V        输出版本信息并退出
```

如：

```bash
[august@localhost ~]$ more +1 work1
I am a student
```

less 命令的格式： less [参数] 文件

```
参数选项：
-b <缓冲区大小> 设置缓冲区的大小 
-e  当文件显示结束后，自动离开 
-f  强迫打开特殊文件，例如外围设备代号、目录和二进制文件 
-g  只标志最后搜索的关键词 
-i  忽略搜索时的大小写 
-m  显示类似more命令的百分比 
-N  显示每行的行号 
-o  <文件名> 将less 输出的内容在指定文件中保存起来 
-Q  不使用警告音 
-s  显示连续空行为一行 
-S  行过长时间将超出部分舍弃 
-x  <数字> 将“tab”键显示为规定的数字空格 
/  字符串：向下搜索“字符串”的功能 
?  字符串：向上搜索“字符串”的功能
n：重复前一个搜索（与 / 或 ? 有关） 
N：反向重复前一个搜索（与 / 或 ? 有关） 
b  向后翻一页 
d  向后翻半页
h  显示帮助界面 
Q  退出less 命令 
u  向前滚动半页 
y  向前滚动一行 
空格键 滚动一页 
回车键 滚动一行
```



### 2.4.3 head命令和tail命令—显示文件开头或末尾的部分内容

1、使用 head 指令查看 work1文本文件的前二段内容：

```bash
[august@localhost ~]$ ls
公共  模板  视频  图片  文档  下载  音乐  桌面  Create  test  work1
[august@localhost ~]$ cat work1
   I am a student
    虚拟机（Virtual Machine）指通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。
    虚拟系统通过生成现有操作系统的全新虚拟镜像，它具有真实windows系统完全一样的功能，进入虚拟系统后，所有操作都是在这个全新的独立的虚拟系统里面进行，可以独立安装运行软件，保存数据，拥有自己的独立桌面，不会对真正的系统产生任何影响 ，而且具有能够在现有系统与虚拟镜像之间灵活切换的一类操作系统。
    虚拟机技术最早由 IBM 于上世纪六七十年代提出，被定义为硬件设备的软件模拟实现，通常的使用模式是分时共享昂贵的大型机。 虚拟机监视器（Virtual Machine Monitor，VMM）是虚拟机技术的核心，它是一层位于操作系统和计算机硬件之间的代码，用来将硬件平台分割成多个虚拟机。
   VMM 运行在特权模式，主要作用是隔离并且管理上层运行的多个虚拟机，仲裁它们对底层硬件的访问，并为每个客户操作系统虚拟一套独立于实际硬件的虚拟硬件环境（包括处理器，内存，I/O 设备）。VMM 采用某种调度算法在各个虚拟机之间共享 CPU，如采用时间片轮转调度算法
[august@localhost ~]$ head -n 2 work1
   I am a student
    虚拟机（Virtual Machine）指通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。
```

2、使用 tail 指令查看 work1文本文件的最后一段文件内容：

```bash
[august@localhost ~]$ tail -n 1 work1
   VMM 运行在特权模式，主要作用是隔离并且管理上层运行的多个虚拟机，仲裁它们对底层硬件的访问，并为每个客户操作系统虚拟一套独立于实际硬件的虚拟硬件环境（包括处理器，内存，I/O 设备）。VMM 采用某种调度算法在各个虚拟机之间共享 CPU，如采用时间片轮转调度算法

```



### 2.4.4 wc命令—文件内容统计

wc 指令的格式： wc [选项] 文件

```bash
常见的几个参数选项：
  -c, --bytes            print the byte counts
  -m, --chars            print the character counts
  -l, --lines            print the newline counts
      --files0-from=文件	从指定文件读取以NUL 终止的名称，如果该文件被
					指定为"-"则从标准输入读文件名
  -L, --max-line-length	显示最长行的长度
  -w, --words			显示单词计数
```

如：统计 work1文本文件中文字的段数：

```bash
[august@localhost ~]$ wc -l work1
5 work1
```



### 2.4.5 echo命令—输出指定内容

1、echo -n 不换行输出：

```bash
[august@localhost ~]$ echo -n "please"
please[august@localhost ~]$ 
```

2、echo -e 指令输出转义字符：

```bash
please[august@localhost ~]$ cd
[august@localhost ~]$ echo -e "please\tgive me"
please	give me
```



### 测试1：

1. ##### 查看Linux系统的IP地址

   ```bash
   [august@localhost ~]$ ifconfig -a
   ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
           ether 00:0c:29:ef:e3:b5  txqueuelen 1000  (Ethernet)
           RX packets 157  bytes 26378 (25.7 KiB)
           RX errors 0  dropped 0  overruns 0  frame 0
           TX packets 0  bytes 0 (0.0 B)
           TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   
   lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
           inet 127.0.0.1  netmask 255.0.0.0
           inet6 ::1  prefixlen 128  scopeid 0x10<host>
           loop  txqueuelen 1000  (Local Loopback)
           RX packets 400  bytes 34664 (33.8 KiB)
           RX errors 0  dropped 0  overruns 0  frame 0
           TX packets 400  bytes 34664 (33.8 KiB)
           TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   
   virbr0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
           inet 192.168.122.1  netmask 255.255.255.0  broadcast 192.168.122.255
           ether 52:54:00:8c:19:c0  txqueuelen 1000  (Ethernet)
           RX packets 0  bytes 0 (0.0 B)
           RX errors 0  dropped 0  overruns 0  frame 0
           TX packets 0  bytes 0 (0.0 B)
           TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   
   virbr0-nic: flags=4098<BROADCAST,MULTICAST>  mtu 1500
           ether 52:54:00:8c:19:c0  txqueuelen 1000  (Ethernet)
           RX packets 0  bytes 0 (0.0 B)
           RX errors 0  dropped 0  overruns 0  frame 0
           TX packets 0  bytes 0 (0.0 B)
           TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   
   ```

   

2. ##### 在Linux中利用ping命令测试能否与主机192.168.80.100通信

   ```bash
   [august@localhost ~]$ ping 192.168.80.100
   connect: 网络不可达
   ```

   显示网络不可达，所以无法主机192.168.80.100通信；

### 2.4.6 grep命令—文件内容查找(重要)

grep指令的格式：grep [选项] 模式 文件名：

```bash
下列是常用的几种选项：
-c	仅列出文件中包含模式的行数。
-i	忽略模式中的字母大小写。
-l	列出带有匹配行的文件名。
-n	在每一行的最前面列出行号。
-v	列出没有匹配模式的行。
-w	把表达式当做一个完整的单字符来搜寻，忽略那些部分匹配的行。
```

查看 work1 文本文件内容中的含有“虚拟机“字符的内容：

```bash
[august@localhost ~]$ grep "虚拟机" work1
    虚拟机（Virtual Machine）指通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。
    虚拟机技术最早由 IBM 于上世纪六七十年代提出，被定义为硬件设备的软件模拟实现，通常的使用模式是分时共享昂贵的大型机。 虚拟机监视器（Virtual Machine Monitor，VMM）是虚拟机技术的核心，它是一层位于操作系统和计算机硬件之间的代码，用来将硬件平台分割成多个虚拟机。
   VMM 运行在特权模式，主要作用是隔离并且管理上层运行的多个虚拟机，仲裁它们对底层硬件的访问，并为每个客户操作系统虚拟一套独立于实际硬件的虚拟硬件环境（包括处理器，内存，I/O 设备）。VMM 采用某种调度算法在各个虚拟机之间共享 CPU，如采用时间片轮转调度算法

```

grep 还要许多参数选项，还有一些是正则匹配模式查看如下：

```bash
正则表达式选择与解释:
  -E, --extended-regexp     PATTERN 是一个可扩展的正则表达式(缩写为 ERE)
  -F, --fixed-strings       PATTERN 是一组由断行符分隔的定长字符串。
  -G, --basic-regexp        PATTERN 是一个基本正则表达式(缩写为 BRE)
  -P, --perl-regexp         PATTERN 是一个 Perl 正则表达式
  -e, --regexp=PATTERN      用 PATTERN 来进行匹配操作
  -f, --file=FILE           从 FILE 中取得 PATTERN
  -i, --ignore-case         忽略大小写
  -w, --word-regexp         强制 PATTERN 仅完全匹配字词
  -x, --line-regexp         强制 PATTERN 仅完全匹配一行
  -z, --null-data           一个 0 字节的数据行，但不是空行

Miscellaneous:
  -s, --no-messages         suppress error messages
  -v, --invert-match        select non-matching lines
  -V, --version             display version information and exit
      --help                display this help text and exit

输出控制:
  -m, --max-count=NUM       NUM 次匹配后停止
  -b, --byte-offset         输出的同时打印字节偏移
  -n, --line-number         输出的同时打印行号
      --line-buffered       每行输出清空
  -H, --with-filename       为每一匹配项打印文件名
  -h, --no-filename         输出时不显示文件名前缀
      --label=LABEL         将LABEL 作为标准输入文件名前缀
  -o, --only-matching       show only the part of a line matching PATTERN
  -q, --quiet, --silent     suppress all normal output
      --binary-files=TYPE   assume that binary files are TYPE;
                            TYPE is 'binary', 'text', or 'without-match'
  -a, --text                equivalent to --binary-files=text
  -I                        equivalent to --binary-files=without-match
  -d, --directories=ACTION  how to handle directories;
                            ACTION is 'read', 'recurse', or 'skip'
  -D, --devices=ACTION      how to handle devices, FIFOs and sockets;
                            ACTION is 'read' or 'skip'
  -r, --recursive           like --directories=recurse
  -R, --dereference-recursive
                            likewise, but follow all symlinks
      --include=FILE_PATTERN
                            search only files that match FILE_PATTERN
      --exclude=FILE_PATTERN
                            skip files and directories matching FILE_PATTERN
      --exclude-from=FILE   skip files matching any file pattern from FILE
      --exclude-dir=PATTERN directories that match PATTERN will be skipped.
  -L, --files-without-match print only names of FILEs containing no match
  -l, --files-with-matches  print only names of FILEs containing matches
  -c, --count               print only a count of matching lines per FILE
  -T, --initial-tab         make tabs line up (if needed)
  -Z, --null                print 0 byte after FILE name

文件控制:
  -B, --before-context=NUM  打印以文本起始的NUM 行
  -A, --after-context=NUM   打印以文本结尾的NUM 行
  -C, --context=NUM         打印输出文本NUM 行
  -NUM                      same as --context=NUM
      --group-separator=SEP use SEP as a group separator
      --no-group-separator  use empty string as a group separator
      --color[=WHEN],
      --colour[=WHEN]       use markers to highlight the matching strings;
                            WHEN is 'always', 'never', or 'auto'
  -U, --binary              do not strip CR characters at EOL (MSDOS/Windows)
  -u, --unix-byte-offsets   report offsets as if CRs were not there
                            (MSDOS/Windows)
```

### 2.4.7 diff命令—文件内容对比

diff 指令的格式：diff 文件1 文件2

diff的参数选项：

```bash
-q, --brief                   report only when files differ
  -s, --report-identical-files  report when two files are the same
  -c, -C NUM, --context[=NUM]   output NUM (default 3) lines of copied context
  -u, -U NUM, --unified[=NUM]   output NUM (default 3) lines of unified context
  -e, --ed                      output an ed script
  -n, --rcs                     output an RCS format diff
  -y, --side-by-side            output in two columns
  -W, --width=NUM               output at most NUM (default 130) print columns
      --left-column             output only the left column of common lines
      --suppress-common-lines   do not output common lines

  -p, --show-c-function         show which C function each change is in
  -F, --show-function-line=RE   show the most recent line matching RE
      --label LABEL             use LABEL instead of file name
                                  (can be repeated)

  -t, --expand-tabs             expand tabs to spaces in output
  -T, --initial-tab             make tabs line up by prepending a tab
      --tabsize=NUM             tab stops every NUM (default 8) print columns
      --suppress-blank-empty    suppress space or tab before empty output lines
  -l, --paginate                pass output through 'pr' to paginate it

  -r, --recursive                 recursively compare any subdirectories found
      --no-dereference            don't follow symbolic links
  -N, --new-file                  treat absent files as empty
      --unidirectional-new-file   treat absent first files as empty
      --ignore-file-name-case     ignore case when comparing file names
      --no-ignore-file-name-case  consider case when comparing file names
  -x, --exclude=PAT               exclude files that match PAT
  -X, --exclude-from=FILE         exclude files that match any pattern in FILE
  -S, --starting-file=FILE        start with FILE when comparing directories
      --from-file=FILE1           compare FILE1 to all operands;
                                    FILE1 can be a directory
      --to-file=FILE2             compare all operands to FILE2;
                                    FILE2 can be a directory

  -i, --ignore-case               ignore case differences in file contents
  -E, --ignore-tab-expansion      ignore changes due to tab expansion
  -Z, --ignore-trailing-space     ignore white space at line end
  -b, --ignore-space-change       ignore changes in the amount of white space
  -w, --ignore-all-space          ignore all white space
  -B, --ignore-blank-lines        ignore changes where lines are all blank
  -I, --ignore-matching-lines=RE  ignore changes where all lines match RE
```

## 2.5 日期和时间的相关命令

### 2.5.1 date命令—显示或修改日期和时间

date 指令的格式：date [选项] [参数] 

这里还要一些其他选项和参数我列举出来,想详细查看请输入指令 date --help：

```bash
选项:
-d <字符串>: 显示字符串所指定的时间或日期. 字符串前后加双引号
-s <字符串>: 设置字符串所指定的时间或日期. 字符串前后加双引号

参数:
%H : 小时,24小时制 (00-23)
%I : 小时,12小时制 (01-12)
%M : 分钟 (00-59)
%S : 秒 (00-59)
%p : 显示 AM 或 PM
%s : 从1970年1月1日00:00:00到当前经历的秒数
%F : 显示年月日 (%Y-%m-%d)
%Y : 显示年 (4位,例如2016)
%y : 显示年 (2为,例如2016则16)
%m : 月份
%d :  日
%X : 显示时间的格式 (%H:%M:%S)
%T : 显示时间,24小时制 (hh:mm:ss)
```



### 2.5.2 hwclock命令—显示或修改硬件时钟

hwclock 指令的格式：hwclock [功能] [选项]

还有一些参数选项，下面列举出来一些，详细查看请输入指令 hwclock --help：

```bash
--adjust：hwclock每次更改硬件时钟时，都会记录在/etc/adjtime文件中。使用--adjust参数，可使hwclock根据先前的记录来估算硬件时钟的偏差，并用来校正目前的硬件时钟；
--debug：显示hwclock执行时详细的信息；
--directisa：hwclock预设从/dev/rtc设备来存取硬件时钟。若无法存取时，可用此参数直接以I/O指令来存取硬件时钟；
--hctosys：将系统时钟调整为与目前的硬件时钟一致；
--set --date=<日期与时间>：设定硬件时钟；
--show：显示硬件时钟的时间与日期；
--systohc：将硬件时钟调整为与目前的系统时钟一致；
--test：仅测试程序，而不会实际更改硬件时钟；
--utc：若要使用格林威治时间，请加入此参数，hwclock会执行转换的工作；
```



### 2.5.3 stat命令—查看文件元数据

## 2.6 文件查找命令

### 2.6.1 locate命令—简单快速的文件查找命令

locate 指令的格式：locate [选项] [参数]

ocate命令其实是find -name的另一种写法，但是要比后者快得多，原因在于它不搜索具体目录，而是搜索一个数据库/var/lib/locatedb，这个数据库中含有本地所有文件信息。Linux系统自动创建这个数据库，并且每天自动更新一次，所以使用locate命令查不到最新变动过的文件。为了避免这种情况，可以在使用locate之前，先使用updatedb命令，手动更新数据库。

```bash
 -d<目录>或--database=<目录>：指定数据库所在的目录；
  -b：只匹配路径中的基名；
  -c：统计出共有多少个符合条件的文件；
  -r：BRE
  -u：更新slocate数据库
```

### 2.6.2 find命令—强大的文件查找命令(重要)

find 指令的格式：find [选项] [参数]

find命令用来在指定目录下查找文件。任何位于参数之前的字符串都将被视为欲查找的目录名。如果使用该命令时，不设置任何参数，则find命令将在当前目录下查找子目录与文件。并且将查找到的子目录和文件全部进行显示。

### 测试2：

##### 1. 为Linux系统设置IP地址192.168.80.10/24

##### 2. 显示/etc目录中的所有内容，包括隐藏文件和目录

##### 3. 以长格式显示/etc目录本身的详细信息

##### 4. 在/root/test1目录中创建一个名为temp1的空文件

##### 5. 将/root/test1目录强制删除

##### 6. 将文件/etc/passwd复制一份进行备份，仍然保存在/etc目录下，备份的文件名为passwd.bak

##### 7. 分屏查看/etc/passwd文件的内容

##### 8. 查看/etc/passwd文件的后5行内容

##### 9. 从/etc/passwd文件中找出所有以root字符串开头的行

##### 10. 统计/etc/passwd文件的行数

### 2.6.3 xargs命令—find辅助命令

使用 find命令的-exec选项处理匹配到的文件时， find命令将所有匹配到的文件一起传递给exec执行。但有些系统对能够传递给exec的命令长度有限制，这样在find命令运行几分钟之后，就会出现溢出错误。错误信息通常是“参数列太长”或“参数列溢出”。这就是xargs命令的用处所在，特别是与find命令一起使用。

## 2.7 内部命令和外部命令

### 2.7.1 什么是内部命令和外部命令

内部命令是DOS 系统中自带的，使用时只要输入命令就能执行，而外部命令使用是，需要有装有外部命令的软盘或光盘，才能够使用。
具体讲：内部命令以外的其他dos可执行程序都可以称为外部命令。
区别：
1、内部命令在系统启动时就调入内存，是常驻内存的，所以执行效率高。
2、外部命令是系统的软件功能，用户需要时才从硬盘中读入内存

### 2.7.2 type命令—判断是内部命令还是外部命令

终端中输入 type 可以查看命令是内部命令还是外部命令。格式为：type  要查看的命令

### 2.7.3 which命令—查找外部命令所对应的程序文件

which命令用于查找Linux外部命令所对应的程序文件，其搜索范围由环境变量PATH决定。

## 2.8 其他辅助命令

### 2.8.1 ln命令—为文件或目录建立链接

链接文件有点类似于Windows 的所谓快捷方式，但并不完全一样。链接有两种方式，软链接和硬链接。链接只会在目的位置生成一个文件的链接文件，实际不会占用磁盘空间，相当于Windows中的快捷方式。硬链接会在目的位置上生成一个和源文件大小相同的文件。无论是软链接还是硬链接，文件都保持同步变化。软链接是可以跨分区的，但是硬链接必须在同一个文件系统，并且不能对目录进行硬链接，而符号链接可以指向任意的位置。

### 2.8.2 alias命令—设置命令别名

**语　　法：**alias[别名]=[指令名称]

**补充说明：**用户可利用alias，自定指令的别名。若仅输入alias，则可列出目前所有的别名设置。　alias的效力仅及于该次登入的操作。若要每次登入是即自动设好别名，可在.profile或.cshrc中设定指令的别名。  

**参　　数：**若不加任何参数，则列出目前所有的别名设置。

### 2.8.3 history命令—查看命令历史记录

**语　　法：**hdparm [-CfghiIqtTvyYZ][-a <快取分区>][-A <0或1>][-c ][-d <0或1>][-k <0或1>][-K <0或1>][-m <分区数>][-n <0或1>][-p ][-P <分区数>][-r <0或1>][-S <时间>][-u <0或1>][-W <0或1>][-X <传输模式>][设备]  

**补充说明：**hdparm可检测，显示与设定IDE或SCSI硬盘的参数。 

**参　　数：**  

```
-a<快取分区>  设定读取文件时，预先存入块区的分区数，若不加上<快取分区>选项，则显示目前的设定。  
-A<0或1>  启动或关闭读取文件时的快取功能。  
-c<I/O模式>  设定IDE32位I/O模式。 
-C  检测IDE硬盘的电源管理模式。  
-d<0或1>  设定磁盘的DMA模式。 
-f  将内存缓冲区的数据写入硬盘，并清楚缓冲区。 
-g  显示硬盘的磁轨，磁头，磁区等参数。 
-h  显示帮助。 
-i  显示硬盘的硬件规格信息，这些信息是在开机时由硬盘本身所提供。 
-I  直接读取硬盘所提供的硬件规格信息。 
-k<0或1>  重设硬盘时，保留-dmu参数的设定。  
-K<0或1>  重设硬盘时，保留-APSWXZ参数的设定。  
-m<磁区数>  设定硬盘多重分区存取的分区数。  
-n<0或1>  忽略硬盘写入时所发生的错误。
-p<PIO模式>  设定硬盘的PIO模式。  
-P<磁区数>  设定硬盘内部快取的分区数。 
-q  在执行后续的参数时，不在屏幕上显示任何信息。 
-r<0或1>  设定硬盘的读写模式。 
-S<时间>  设定硬盘进入省电模式前的等待时间。
```



### 2.8.4 help命令—查看命令帮助信息

### 2.8.5 man命令—查看命令帮助手册

```
SYNOPSIS
       man  [-C  file]  [-d]  [-D]  [--warnings[=warnings]]  [-R  encoding] [-L locale] [-m system[,...]] [-M path] [-S list] [-e extension] [-i|-I]
       [--regex|--wildcard] [--names-only] [-a] [-u] [--no-subpages] [-P pager] [-r prompt] [-7] [-E encoding]  [--no-hyphenation]  [--no-justifica‐
       tion] [-p string] [-t] [-T[device]] [-H[browser]] [-X[dpi]] [-Z] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [-w|-W] [-S list] [-i|-I] [--regex] [section] term ...
       man -f [whatis options] page ...
       man  -l  [-C  file]  [-d]  [-D]  [--warnings[=warnings]] [-R encoding] [-L locale] [-P pager] [-r prompt] [-7] [-E encoding] [-p string] [-t]
       [-T[device]] [-H[browser]] [-X[dpi]] [-Z] file ...
       man -w|-W [-C file] [-d] [-D] page ...
       man -c [-C file] [-d] [-D] page ...
       man [-?V]

DESCRIPTION
       man is the system's manual pager. Each page argument given to man is normally the name of a program, utility or function.   The  manual  page
       associated  with each of these arguments is then found and displayed. A section, if provided, will direct man to look only in that section of
       the manual.  The default action is to search in all of the available sections, following a pre-defined order and to show only the first  page
       found, even if page exists in several sections.
```



### 2.8.6 clear命令—清屏

## 2.9 重定向和管道(重要)

### 2.9.1 标准输入与输出

执行一个shell命令行时通常会自动打开三个标准文件，即标准输入文件（stdin），通常对应终端的键盘；标准输出文件（stdout）和标准错误输出文件（stderr），这两个文件都对应终端的屏幕。进程将从标准输入文件中得到输入数据，将正常输出数据到标准输出文件，而将错误信息送到标准错误文件中。

### 2.9.2 标准输出重定向

### 2.9.3 标准输入重定向

### 2.9.4 标准错误重定向

### 测试3：

##### 1. 以长格式显示root用户家目录中的所有内容，包括隐藏文件和目录。

##### 2. 在/etc目录中查找所有名称以“net”开头，以“.conf”结尾的文件。

##### 3. 从/root/install.log文件中查找包含字符串“lib”的行。

##### 4. 以k、M、G等容量单位显示/etc目录中所有文件和目录的详细信息。

##### 5. 将/etc/fstab文件复制到/tmp目录中，并重命名为hi.txt

##### 6. 找到find命令的命令文件路径。

##### 7. 将/etc/passwd文件中前10行的内容复制到/root/pass.txt文件中。

##### 8. 以长格式列出/dev目录中以“d”、“f”开头并且文件名为3个字符的文件。# ll -d /dev/[df]??

##### 9. 将执行find / -user student命令时产生的错误信息重定向到/dev/null文件中。# find / -user student 2>/dev/null

##### 10. 在/tmp目录中创建一个名为ssh的软链接，指向源文件/etc/ssh/sshd_config

### 2.9.5 管道符“|”(重要)

管道符（pipe）用“|”这个界定符号表示，如果需要对linux命令的输出结果进行再次处理，就可以使用管道符+管道命令解决。

例如通过ps命令可以查看系统中的进程，但如果需要查看指定进程，就需要在ps命令返回的结果中进行筛选，如查看java进程：

```
ps -aux | ``grep` `java
```

## 2.10 Vi编辑器的使用(重要)

### 2.10.1 Vi编辑器的工作模式

#### 1) 命令行模式

```
该模式是进入 vi 编辑器后的默认模式。任何时候，不管用户处于何种模式，按下`Esc`键即可进入命令模式。

在命令模式下，用户可以输入 vi 命令，用于管理自己的文档。此时从键盘上输入的任何字符都被当做编辑命令来解释。若输入的字符是合法的 vi 命令，则 vi 在接受用户命令之后完成相应的动作。

但需注意的是，所输入的命令并不回显在屏幕上。若输入的字符不是 vi 的合法命令，vi 会响铃报警。
```

#### 2) 文本输入模式

```
在命令模式下输入插入命令`i`、附加命令`a`、打开命令`o`、修改命令`c`、取代命令`r`或替换命令`s`都可以进入文本输入模式。

在该模式下，用户输入的任何字符都被 vi 当做文件内容保存起来，并将其显示在屏幕上。在文本输入过程中，若想回到命令模式下，按下`Esc`键即可。
```

#### 3) 末行模式

```
末行模式也称 ex 转义模式。

在命令模式下，用户按`:`键即可进入末行模式下，此时 vi 会在显示窗口的最后一行（通常也是屏幕的最后一行）显示一个`:`作为末行模式的说明符，等待用户输入命令。多数文件管理命令都是在此模式下执行的（如把编辑缓冲区的内容写到文件中等）。

末行命令执行完后，vi 自动回到命令模式。
```



### 2.10.2 命令模式的基本操作

### 2.10.3 插入模式的基本操作

### 2.10.4 底行模式的基本操作

### 2.10.5 可视模式的基本操作

### 2.10.6 Vi编辑器案例

## 2.11 思考与练习

# 第3章 用户和权限管理

## 3.1 用户和组的概念

### 3.1.1 用户帐号的类型

### 3.1.2 用户组的类型

### 3.1.3 UID和GID

### 3.1.4 利用id命令查看用户身份信息

## 3.2 用户和组的配置文件

### 3.2.1 用户帐号文件/etc/passwd

### 3.2.2 用户密码文件/etc/shadow

### 3.2.3 用户组配置文件

## 3.3 管理用户和组

### 3.3.1 useradd命令—创建用户帐号

### 3.3.2 passwd命令—为用户帐号设置密码

### 3.3.3 su命令—切换用户身份

### 3.3.4 userdel命令—删除用户帐号

### 3.3.5 usermod命令—修改用户帐号属性

### 3.3.6 groupadd命令—创建用户组

### 3.3.7 gpasswd命令—添加、删除组成员

### 3.3.8 groupdel命令—删除用户组

### 3.3.9 创建用户的相关配置文件

## 3.4 管理权限和归属

### 3.4.1 权限与归属的概念

### 3.4.2 查看权限和归属

### 3.4.3 利用chmod命令设置权限

### 3.4.4 利用chown命令设置归属

## 3.5 配置文件访问控制列表（FACL）

### 3.5.1 设置FACL

### 3.5.2 管理FACL

### 3.5.3 启用FACL支持

### 3.5.4 配置FACL时应注意的问题

## 3.6 设置特殊权限

### 3.6.1 设置SET位权限

### 3.6.2 设置粘滞位（SBIT）权限

### 3.6.3 设置umask值

## 3.7 find命令按文件属性/权限查找

### 3.7.1 根据文件属性查找

### 3.7.2 根据文件权限查找

## 3.8 系统权限的其他相关设置

### 3.8.1 设置扩展属性

### 3.8.2 限制切换到root用户

### 3.8.3 使用sudo机制提升权限

## 3.9 思考与练习

# 第4章 磁盘和文件系统管理

## 4.1 磁盘分区与格式化

### 4.1.1 Linux磁盘及分区的表示方法

### 4.1.2 Linux的文件系统

### 4.1.3 查看分区信息

### 4.1.4 在虚拟机中添加硬盘

### 4.1.5 利用fdisk对硬盘进行分区

### 4.1.6 格式化分区

## 4.2 挂载存储设备

### 4.2.1 什么是挂载

### 4.2.2 挂载硬盘分区

### 4.2.3 查看系统中已挂载的设备

### 4.2.4 挂载光驱

### 4.2.5 挂载移动存储设备

### 4.2.6 挂载ISO镜像

### 4.2.7 卸载存储设备

### 4.2.8 自动挂载

## 4.3 磁盘配额管理（quota）

### 4.3.1 什么是磁盘配额

### 4.3.2 设置磁盘配额

### 4.3.3 验证并查看磁盘配额

## 4.4 磁盘阵列管理（RAID）

### 4.4.1 什么是RAID

### 4.4.2 RAID实现方式

### 4.4.3 配置RAID 10

### 4.4.4 RAID性能测试

### 4.4.5 RAID故障模拟

### 4.4.6 配置RAID 5和备份盘

## 4.5 逻辑卷管理（LVM）

### 4.5.1 LVM的相关概念

### 4.5.2 系统默认LVM设置

### 4.5.3 创建物理卷（PV）

### 4.5.4 创建卷组（VG）

### 4.5.5 创建逻辑卷（LV）

### 4.5.6 使用逻辑卷

### 4.5.7 扩展逻辑卷空间

### 4.5.8 删除LVM分区

## 4.6 思考与练习

# 第5章 软件包管理

## 5.1 文件打包与压缩

### 5.1.1 du命令—查看目录或文件占用磁盘空间的大小

### 5.1.2 tar命令—文件打包与压缩

## 5.2 Linux系统中的软件安装方法

### 5.2.1 源码安装方式

### 5.2.2 RPM安装方式

### 5.2.3 YUM安装方式

## 5.3 利用RPM进行软件包管理

### 5.3.1 了解RPM软件包

### 5.3.2 安装/卸载软件包

### 5.3.3 查询软件包

## 5.4 利用YUM进行软件包管理

### 5.4.1 配置YUM源

### 5.4.2 检测YUM源

### 5.4.3 常用的YUM命令

### 5.4.4 YUM故障排错

## 5.5 利用源码编译安装软件

### 5.5.1 源码编译简介

### 5.5.2 源码编译安装的基本流程

## 5.6 思考与练习

# 第6章 进程和服务管理

## 6.1 进程的相关介绍

### 6.1.1 什么是进程

### 6.1.2 进程的状态

### 6.1.3 父进程和子进程

### 6.1.4 进程的属性

### 6.1.5 进程的分类

## 6.2 查看进程状态

### 6.2.1 ps命令—查看进程静态信息

### 6.2.2 top命令—查看进程的动态信息

### 6.2.3 伪文件系统（/proc）

## 6.3 控制进程

### 6.3.1 前台启动与后台启动 

### 6.3.2 解除进程与终端之间的关系

### 6.3.3 终止进程执行

## 6.4 查看用户的登录信息

### 6.4.1 users命令—查看登录用户名

### 6.4.2 who命令—查看登录用户的信息

### 6.4.3 w命令—查看登录用户的详细信息

### 6.4.4 last命令—查看登录记录

### 6.4.5 “踢出”可疑用户

## 6.5 查看系统资源的占用信息

### 6.5.1 查看CPU的硬件信息

### 6.5.2 uptime命令—查看CPU的使用情况

### 6.5.3 free命令—查看内存的使用情况

### 6.5.4 df命令—查看硬盘的使用情况

## 6.6 服务的相关介绍

### 6.6.1 什么是服务

### 6.6.2 系统初始化进程systemd

#### （1）服务目录

在之前的5.x/6.x系统中，系统的服务都是存放在/etc/init.d/目录中的，但是在7.x的系统中，已经发生了改变，如下：

```bash
-------------------------查看CentOS7之前的系统服务存放位置-------------------------
[root@node1 ~]# ls /etc/init.d/
auditd            halt       killall     network   rdma         saslauthd
blk-availability  ip6tables  mdmonitor   nfs-rdma  restorecond  single
crond             iptables   netconsole  postfix   rsyslog      sshd
functions         kdump      netfs       rdisc     sandbox      udev-post

-------------------------查看CentOS7的/etc/init.d/目录-------------------------
[root@ctf ~]# ll /etc/init.d/
总用量 40
-rw-r--r--. 1 root root 18281 8月  19 2019 functions
-rwxr-xr-x. 1 root root  4569 8月  19 2019 netconsole
-rwxr-xr-x. 1 root root  7928 8月  19 2019 network
-rw-r--r--. 1 root root  1160 4月   1 2020 README
此目录不再是系统服务的存放位置，因此重启服务也不能使用/etc/init.d/servername restart来启动。
```

#### （2）系统运行级别

CentOS7中，系统的运行级别已没有0～6之说，运行级别的inittab文件也不再包含0～6级别的说明，如下：

```bash
[root@ctf ~]# cat /etc/inittab
# inittab is no longer used when using systemd.
#
# ADDING CONFIGURATION HERE WILL HAVE NO EFFECT ON YOUR SYSTEM.
#
# Ctrl-Alt-Delete is handled by /usr/lib/systemd/system/ctrl-alt-del.target
#
# systemd uses 'targets' instead of runlevels. By default, there are two main 
targets:#
# multi-user.target: analogous to runlevel 3
# graphical.target: analogous to runlevel 5
#
# To view current default target, run:
# systemctl get-default
#
# To set a default target, run:
# systemctl set-default TARGET.target
#
```

查看系统默认运行级别：

```bash
[root@ctf ~]# systemctl get-default
graphical.target
```

设置默认运行级别：

```bash
[root@ctf ~]# systemctl set-default multi-user.target
rm '/etc/systemd/system/default.target'
ln -s '/usr/lib/systemd/system/multi-user.target' '/etc/systemd/system/default.target'
[root@ctf ~]# systemctl get-default
multi-user.target
```

查看已设置运行级别的服务状态（下次启动状态）：

```bash
[root@ctf ~]# systemctl list-unit-files | grep multi-user
multi-user.target                             enabled
```

#### （3）服务下次启动状态

在CentOS7之前的系统中，使用命令chkconfig --list可查看所有服务的下次启动状态，但在CentOS7中，此命令已不可用。

```bash
[root@ctf init.d]# chkconfig --list

注：该输出结果只显示 SysV 服务，并不包含
原生 systemd 服务。SysV 配置数据
可能被原生 systemd 配置覆盖。 

      要列出 systemd 服务，请执行 'systemctl list-unit-files'。
      查看在具体 target 启用的服务请执行
      'systemctl list-dependencies [target]'。

netconsole     	0:关	1:关	2:关	3:关	4:关	5:关	6:关
network        	0:关	1:关	2:开	3:开	4:开	5:开	6:关
```

如上，此命令列出的只是一些基本的服务。要想查看所有的服务，根据提示命令查看：

```bash
[root@ctf init.d]# systemctl list-unit-files
UNIT FILE                                     STATE   
proc-sys-fs-binfmt_misc.automount             static  
dev-hugepages.mount                           static  
.....
firewalld.service                             enabled
httpd.service                                 enabled
.....
ctrl-alt-del.target                           disabled
```

服务启动之后，要想下次重启生效，在CentOS7之前要使用命令chkconfig servername on，但在CentOS7中，已不能使用该命令。

```bash
[root@ctf ~]# systemctl start httpd.service //启动apache，后面的.service也可以不写
[root@ctf ~]# systemctl status httpd //查看httpd服务的运行状态
● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; enabled; vendor preset: disabled)
   Active: active (running) since 一 2021-03-08 09:43:29 CST; 5min ago
     Docs: man:httpd(8)
           man:apachectl(8)
  Process: 1499 ExecStop=/bin/kill -WINCH ${MAINPID} (code=exited, status=0/SUCCESS)
  Process: 1428 ExecReload=/usr/sbin/httpd $OPTIONS -k graceful (code=exited, status=0/SUCCESS)
 Main PID: 1510 (httpd)
   Status: "Total requests: 0; Current requests/sec: 0; Current traffic:   0 B/sec"
   CGroup: /system.slice/httpd.service
           ├─1510 /usr/sbin/httpd -DFOREGROUND
           ├─1511 /usr/sbin/httpd -DFOREGROUND
           ├─1512 /usr/sbin/httpd -DFOREGROUND
           ├─1513 /usr/sbin/httpd -DFOREGROUND
           ├─1514 /usr/sbin/httpd -DFOREGROUND
           └─1515 /usr/sbin/httpd -DFOREGROUND

3月 08 09:43:29 ctf.itecs.cn systemd[1]: Starting The Apache HTTP Server...
3月 08 09:43:29 ctf.itecs.cn systemd[1]: Started The Apache HTTP Server.
```

设置服务下次开机状态为关闭/启动：

```bash
[root@ctf ~]# systemctl disable httpd
Removed symlink /etc/systemd/system/multi-user.target.wants/httpd.service.
[root@ctf ~]# systemctl enable httpd
Created symlink from /etc/systemd/system/multi-user.target.wants/httpd.service to /usr/lib/systemd/system/httpd.service.
```



### 6.6.3 systemd unit

## 6.7 利用systemctl命令管理服务

### 6.7.1 管理服务运行状态

### 6.7.2 管理服务启动状态

### 6.7.3 vsftpd服务管理示例

## 6.8 管理系统运行级别

### 6.8.1 什么是运行级别

### 6.8.2 切换和设置运行级别

### 6.8.3 重置root用户密码

## 6.9 管理计划任务

### 6.9.1 配置at一次性计划任务

### 6.9.2 配置cron周期性计划任务

## 6.10 思考与练习

# 第7章 Shell脚本编程基础

## 7.1 创建Shell脚本程序

### 7.1.1 什么是Shell脚本编程

### 7.1.2 Shell脚本的基本语法

### 7.1.3 编写Shell脚本文件

## 7.2 Shell变量

### 7.2.1 用户自定义变量

### 7.2.2 环境变量

### 7.2.3 位置变量

### 7.2.4 预定义变量

## 7.3 条件测试与比较

### 7.3.1 文件状态测试

### 7.3.2 整数值比较

### 7.3.3 字符串比较

### 7.3.4 逻辑测试

## 7.4 程序结构

### 7.4.1 if选择语句

### 7.4.2 case分支语句

### 7.4.3 for循环语句

### 7.4.4 while循环语句

### 7.4.5 循环控制语句

### 7.4.6 shift和exit语句

### 7.4.7 多任务并发执行

## 7.5 Shell函数

### 7.5.1 函数的定义和调用

### 7.5.2 函数的参数传递

## 7.6 常用的文本编辑命令

### 7.6.1 正则表达式

### 7.6.2 cut命令—按列截取文件内容

### 7.6.3 sort命令—对文本信息进行排序

### 7.6.4 sed命令

### 7.6.5 AWK命令

## 7.7 思考与练习


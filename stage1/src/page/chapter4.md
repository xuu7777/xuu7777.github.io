###系统目录
* Program Files：
这个文件夹是Windows系统中相当重要的一个。一部分系统程序会在里面，比如IE浏览器。同时它也是你安装的第三方软件所在目录。一旦你删了那你所安装在里面的程序全部都用不了了。

* Program Files（x86）：
这个文件夹是64位操作系统专有的，如果你是32位的操作系统那只有一个Program Files文件夹。它的作用其实跟Program Files一样，里面存储的是你所安装的32位的软件资源。32位的程序在安装的时候就会默认装到（x86）这里来，而那些64位的或者没有位数区分的软件就装到Program Files那里去。

* Windows：
这个可以说是操作系统的一个心脏。整个操作系统的运行就是靠它，绝大部分的系统文件都藏在Windows这个文件夹来了。所以这个文件夹千万不要乱动，分分钟让你系统崩溃。

* 用户/user/Documents and settings：
用户文件夹，里面存放的都是你的个人文件，各种软件数据就是在里面，基本上都是跟系统无关系的，我的话点进去看到不顺眼的一言不合就删掉它。

* system32：
核心文件夹，Windows内核所在之处。它在系统在。

* SysWOW64：
64位系统独有的文件夹，也是一个运行库。没了它，就不能运行32位的程序。

* $RECYCLE.BIN：
回收站文件夹，这个文件夹不用删，你那个垃圾桶满了就清理掉就可以了。

* boot:
系统引导文件目录，开机系统加载的时候要找的信息就是这里来了，默认情况下就是隐藏。是绝对不能删除的一个文件夹，否则后果严重。

* ProgramData：
公用文件夹，里面存放被创建的文件。像开始菜单那些东西都是在里面的。不能删。

###服务
几乎所有的操作系统在启动的时候都会启动一些不需要与用户交互的进程，这些进程在Windows中就被称作服务。

#####服务的启动类型：
1. 自动
2. 手动
3. 禁止

###Local System（本地系统）：
举例来说，以Local System账户运行的服务主要有：
1. Windows Update （Windows 更新）
2. Com+（管理基于组件对象模型 （COM+） 的组件的配置和跟踪）
3. Messenger Service （支持短信及相关功能）
4. Task Scheduler （在此计算机上配置和计划自动任务）
5. Server （支持此计算机通过网络的文件、打印、和命名管道共享）
6. Windows Installer （添加、修改和删除作为Windows Installer 程序包（. msi、 msp）提供的应用程序）

###Network service（网络服务）：
* DNS服务

* Local Service（本地服务）：
Local Service账户是预设的拥有最小权限的本地账户，并在网络凭证中具有匿名
的身份。
注意运行于此账户下的进程和运行于Network Service账户下的进程的区别在于运行Local Service账户下的进程只能访问允许匿名访问的网络资源。
* DHCP服务。

###端口：


在网络技术中，端口（Port）大致有两种意思：
* 一是物理意义上的端口，比如，ADSL Modem、集线器、交换机、路由器用于连接其他网络设备的接口，如RJ-45端口、SC端口等等。　
　　
* 二是逻辑意义上的端口，一般是指TCP/IP协议中的端口，端口号的范围从0到65535，比如用于浏览网页服务的80端口，用于FTP服务的21端口等等。我们这里将要介绍的就是逻辑意义上的端口。

###查看端口


在Windows 2000/XP/Server 2003中要查看端口，可以使用Netstat命令：　　依次点击“开始→运行”，键入“cmd”并回车，打开命令提示符窗口。在命令提示符状态下键入“netstat -a -n”，按下回车键后就可以看到以数字形式显示的TCP和UDP连接的端口号及状态。

###关闭/开启端口


在Windows中如何关闭/打开端口，因为默认的情况下，有很多不安全的或没有什么用的端口是开启的，比如Telnet服务的23端口、FTP服务的21端口、SMTP服务的25端口、RPC服务的135端口等等。为了保证系统的安全性，我们可以通过下面的方法来关闭/开启端口。

1. 关闭端口　　比如在Windows 2000/XP中关闭SMTP服务的25端口，可以这样做：首先打开“控制面板”，双击“管理工具”，再双击“服务”。接着在打开的服务窗口中找到并双击“Simple Mail Transfer Protocol（SMTP）”服务，单击“停止”按钮来停止该服务，然后在“启动类型”中选择“已禁用”，最后单击“确定”按钮即可。这样，关闭了SMTP服务就相当于关闭了对应的端口。

2. 开启端口　　如果要开启该端口只要先在“启动类型”选择“自动”，单击“确定”按钮，再打开该服务，在“服务状态”中单击“启动”按钮即可启用该端口，最后，单击“确定”按钮即可。提示：在Windows 98中没有“服务”选项，你可以使用防火墙的规则设置功能来关闭/开启端口。

###各种端口的作用端口：


0服务：Reserved说明：通常用于分析操作系统。这一方法能够工作是因为在一些系统中“0”是无效端口，当你试图使用通常的闭合端口连接它时将产生不同的结果。一种典型的扫描，使用IP地址为0.0.0.0，设置ACK位并在以太网层广播。

* 端口：1  服务：tcpmux说明：这显示有人在寻找SGI Irix机器。Irix是实现tcpmux的主要提供者，默认情况下tcpmux在这种系统中被打开。Irix机器在发布是含有几个默认的无密码的帐户，如：IP、GUEST UUCP、NUUCP、DEMOS、TUTOR、DIAG、OUTOFBOX等。许多管理员在安装后忘记删除这些帐户。因此HACKER在INTERNET上搜索tcpmux并利用这些帐户。

* 端口：7  服务：Echo说明：能看到许多人搜索Fraggle放大器时，发送到X.X.X.0和X.X.X.255的信息。

* 端口：19  服务：Character Generator说明：这是一种仅仅发送字符的服务。UDP版本将会在收到UDP包后回应含有垃圾字符的包。TCP连接时会发送含有垃圾字符的数据流直到连接关闭。HACKER利用IP欺骗可以发动DoS攻击。伪造两个chargen服务器之间的UDP包。同样Fraggle DoS攻击向目标地址的这个端口广播一个带有伪造受害者IP的数据包，受害者为了回应这些数据而过载。

* 端口：21  服务：FTP说明：FTP服务器所开放的端口，用于上传、下载。

* 端口：22  服务：Ssh说明：PcAnywhere建立的TCP和这一端口的连接可能是为了寻找ssh。

* 端口：23  服务：Telnet说明：Telnet远程登录。

* 端口：25  服务：SMTP说明：SMTP服务器所开放的端口，用于发送邮件。

* 端口：31  服务：MSG Authentication说明：木马Master Paradise、Hackers Paradise开放此端口。

* 端口：42  服务：WINS Replication说明：WINS复制

* 端口：53  服务：Domain Name Server（DNS）说明：DNS服务器所开放的端口，入侵者可能是试图进行区域传递（TCP），欺骗DNS（UDP）或隐藏其他的通信。因此防火墙常常过滤或记录此端口。

* 端口：67  服务：Bootstrap Protocol Server说明：通过DSL和Cable modem的防火墙常会看见大量发送到广播地址255.255.255.255的数据。这些机器在向DHCP服务器请求一个地址。HACKER常进入它们，分配一个地址把自己作为局部路由器而发起大量中间人（man-in-middle）攻击。客户端向68端口广播请求配置，服务器向67端口广播回应请求。这种回应使用广播是因为客户端还不知道可以发送的IP地址。

* 端口：69  服务：Trival File Transfer说明：许多服务器与bootp一起提供这项服务，便于从系统下载启动代码。但是它们常常由于错误配置而使入侵者能从系统中窃取任何文件。它们也可用于系统写入文件。

* 端口：79  服务：Finger Server说明：入侵者用于获得用户信息，查询操作系统，探测已知的缓冲区溢出错误，回应从自己机器到其他机器Finger扫描。

* 端口：80  服务：HTTP说明：用于网页浏览。木马Executor开放此端口。

* 端口：99  服务：Metagram Relay说明：后门程序ncx99开放此端口。

* 端口：102  服务：Message transfer agent(MTA)-X.400 over TCP/IP说明：消息传输代理。

* 端口：109  服务：Post Office Protocol -Version3说明：POP3服务器开放此端口，用于接收邮件，客户端访问服务器端的邮件服务。POP3服务有许多公认的弱点。关于用户名和密码交换缓冲区溢出的弱点至少有20个，这意味着入侵者可以在真正登陆前进入系统。成功登陆后还有其他缓冲区溢出错误。

* 端口：110  服务：SUN公司的RPC服务所有端口说明：常见RPC服务有rpc.mountd、NFS、rpc.statd、rpc.csmd、rpc.ttybd、amd等

* 端口：113  服务：Authentication Service说明：这是一个许多计算机上运行的协议，用于鉴别TCP连接的用户。使用标准的这种服务可以获得许多计算机的信息。但是它可作为许多服务的记录器，尤其是FTP、POP、IMAP、SMTP和IRC等服务。通常如果有许多客户通过防火墙访问这些服务，将会看到许多这个端口的连接请求。记住，如果阻断这个端口客户端会感觉到在防火墙另一边与E-MAIL服务器的缓慢连接。许多防火墙支持TCP连接的阻断过程中发回RST。这将会停止缓慢的连接。

* 端口：119  服务：Network News Transfer Protocol说明：NEWS新闻组传输协议，承载USENET通信。这个端口的连接通常是人们在寻找USENET服务器。多数ISP限制，只有他们的客户才能访问他们的新闻组服务器。打开新闻组服务器将允许发/读任何人的帖子，访问被限制的新闻组服务器，匿名发帖或发送SPAM。

* 端口：135  服务：Location Service说明：Microsoft在这个端口运行DCE RPC end-point mapper为它的DCOM服务。这与UNIX 111端口的功能很相似。使用DCOM和RPC的服务利用计算机上的end-point mapper注册它们的位置。远端客户连接到计算机时，它们查找end-point mapper找到服务的位置。HACKER扫描计算机的这个端口是为了找到这个计算机上运行Exchange Server吗？什么版本？还有些DOS攻击直接针对这个端口。

* 端口：137、138、139  服务：NETBIOS Name Service说明：其中137、138是UDP端口，当通过网上邻居传输文件时用这个端口。而139端口：通过这个端口进入的连接试图获得NetBIOS/SMB服务。这个协议被用于windows文件和打印机共享和SAMBA。还有WINS Regisrtation也用它。

* 端口：143  服务：Interim Mail Access Protocol v2说明：和POP3的安全问题一样，许多IMAP服务器存在有缓冲区溢出漏洞。记住：一种LINUX蠕虫（admv0rm）会通过这个端口繁殖，因此许多这个端口的扫描来自不知情的已经被感染的用户。当REDHAT在他们的LINUX发布版本中默认允许IMAP后，这些漏洞变的很流行。这一端口还被用于IMAP2，但并不流行。

* 端口：161  服务：SNMP说明：SNMP允许远程管理设备。所有配置和运行信息的储存在数据库中，通过SNMP可获得这些信息。许多管理员的错误配置将被暴露在Internet。Cackers将试图使用默认的密码public、private访问系统。他们可能会试验所有可能的组合。SNMP包可能会被错误的指向用户的网络。

* 端口：177  服务：X Display Manager Control Protocol说明：许多入侵者通过它访问X-windows操作台，它同时需要打开6000端口。

* 端口：389  服务：LDAP、ILS说明：轻型目录访问协议和NetMeeting Internet Locator Server共用这一端口。

* 端口：443  服务：Https说明：网页浏览端口，能提供加密和通过安全端口传输的另一种HTTP。

* 端口：456  服务：[NULL]说明：木马HACKERS PARADISE开放此端口。

* 端口：513  服务：Login,remote login说明：是从使用cable modem或DSL登陆到子网中的UNIX计算机发出的广播。这些人为入侵者进入他们的系统提供了信息。

* 端口：544  服务：[NULL]说明：kerberos kshell

* 端口：548  服务：Macintosh,File Services(AFP/IP)说明：Macintosh,文件服务。

* 端口：553  服务：CORBA IIOP（UDP）说明：使用cable modem、DSL或VLAN将会看到这个端口的广播。CORBA是一种面向对象的RPC系统。入侵者可以利用这些信息进入系统。

* 端口：555  服务：DSF说明：木马PhAse1.0、Stealth Spy、IniKiller开放此端口。

* 端口：568  服务：Membership DPA说明：成员资格DPA。

* 端口：569  服务：Membership MSN说明：成员资格MSN。

* 端口：635  服务：mountd说明：Linux的mountd Bug。这是扫描的一个流行BUG。大多数对这个端口的扫描是基于UDP的，但是基于TCP的mountd有所增加（mountd同时运行于两个端口）。记住mountd可运行于任何端口（到底是哪个端口，需要在端口111做portmap查询），只是Linux默认端口是635，就像NFS通常运行于2049端口。

* 端口：636  服务：LDAP说明：SSL（Secure Sockets layer）

* 端口：666  服务：Doom Id Software说明：木马Attack FTP、Satanz Backdoor开放此端口

* 端口：993  服务：IMAP说明：SSL（Secure Sockets layer）

* 端口：1001、1011  服务：[NULL]说明：木马Silencer、WebEx开放1001端口。木马Doly Trojan开放1011端口。

* 端口：1024  服务：Reserved说明：它是动态端口的开始，许多程序并不在乎用哪个端口连接网络，它们请求系统为它们分配下一个闲置端口。基于这一点分配从端口1024开始。这就是说第一个向系统发出请求的会分配到1024端口。你可以重启机器，打开Telnet，再打开一个窗口运行natstat -a将会看到Telnet被分配1024端口。还有SQL session也用此端口和5000端口。

* 端口：1025、1033  服务：1025：network blackjack 1033：[NULL]说明：木马netspy开放这2个端口。

* 端口：1080  服务：SOCKS说明：这一协议以通道方式穿过防火墙，允许防火墙后面的人通过一个IP地址访问INTERNET。理论上它应该只允许内部的通信向外到达INTERNET。但是由于错误的配置，它会允许位于防火墙外部的攻击穿过防火墙。WinGate常会发生这种错误，在加入IRC聊天室时常会看到这种情况。

* 端口：1170  服务：[NULL]说明：木马Streaming Audio Trojan、Psyber Stream Server、Voice开放此端口。

* 端口：1234、1243、6711、6776  服务：[NULL]说明：木马SubSeven2.0、Ultors Trojan开放1234、6776端口。木马SubSeven1.0/1.9开放1243、6711、6776端口。

* 端口：1245  服务：[NULL]说明：木马Vodoo开放此端口。

* 端口：1433  服务：SQL说明：Microsoft的SQL服务开放的端口。

* 端口：1492  服务：stone-design-1说明：木马FTP99CMP开放此端口。

* 端口：1500  服务：RPC client fixed port session queries说明：RPC客户固定端口会话查询

* 端口：1503  服务：NetMeeting T.120说明：NetMeeting T.120

* 端口：1524  服务：ingress说明：许多攻击脚本将安装一个后门SHELL于这个端口，尤其是针对SUN系统中Sendmail和RPC服务漏洞的脚本。如果刚安装了防火墙就看到在这个端口上的连接企图，很可能是上述原因。可以试试Telnet到用户的计算机上的这个端口，看看它是否会给你一个SHELL。连接到600/pcserver也存在这个问题。

###通过端口可以做什么：


* 信息收集
* 目标探测
* 服务判断
* 系统判断
* 系统角色分析

###注册表


注册表是windows中的一个重要的数据库，用于存储系统和应用程序的设置信息，早在windows3.0推出OLE技术的时候，注册表就已经出现，随后推出windows用户经常接触的内容，并在其后的操作系统中继续沿用至今。

###注册表结构：


1.HKEY_CLASSES_ROOT  管理文件系统，根据windows中安装的应用程序的扩展名，该根键指明其文件类型的名称，相应打开该文件索要调用的程序等等信息。  


2.HEKY_CURRENT_USER  管理当前的用户信息，在这个根键中保存了本地计算机中存放的当前登录的用户信息，包括用户登录用户名和暂存的密码。在用户登录windows98时，其信息从HKEY_USERS中相应的项拷贝到HEKY_CURRENT_USER中。


3.HEKY_LOCAL_MACHINE  管理当前系统硬件的配置，在这个根键中保存了本地计算机硬件配置数据，此根键下的自关键字包括SYSTEM.DAT中，用来提供HKEY_LOCAL_MACHINE 所需的信息，或者在远程计算机中可访问的一组键中，这个根键里面的许多子键与System.ini文件中的设置项类似。


4.HEKY_USERS  管理系统的用户信息，在这个根键中保存了存放在本地计算机口令列表中的用户标识和密码列表，同时每个用户的预配置信息都存储在HKEY_USERS 根键中，HKEY_USERS是远程计算机中访问的根键之一。


5.HKEY_CURRENR_CONFIG  管理当前用户的系统配置，在这个根键中保存着定义当前用户桌面配置（如显示器等等）的数据，该用户使用过的文档列表（MRU），应用程序配置和其他有关当前用户的windows98中文版的安装信息。

###常用DOS命令：


* `color ?`  改变cmd颜色


* `ping -t -| 65550 ip`  死亡之ping（发送大于64k的文件并一直ping就成了死亡之ping） 


* `ipconfig`  查看ip


* `ipconfig/release`  释放ip


* `ipconfig/renew`  重新获得ip


* `systeminfo`  查看系统信息


* `arp -a`


* `net view`  查看局域网内其他计算机名称


* `shudown -s -t 180 -c"你被黑了，系统马上关机"`


* `dir`  查看目录


* `cd`  切换目录


* `start 域名`  打开网页


* `start 123.txt`  打开123.txt


* `conpy con c:\123.txt`  创建123.txt文件


* `ctrl + z`  回车


* `md 目录名`  创建目录


* `rd 123`  删除文件夹


* `ren 原文件名  新文件名`  重命名文件名


* `del`  删除文件


* `copy`  复制文件


* `move`  移动文件


* `tree`  树形列出文件夹结构


* `telnet` 


* `net use k:\\192.168.1.1\c$`


* `net use k:\\192.168.1.1\c$ /del`


* `net start`  查看开启了哪些服务


* `net start 服务名`  开启服务（如：net start telnet，net start schedule）


* `net stop 服务名`  停止某服务


* `net user 用户名 密码 /add`  建立用户


* `net user guest /active:yes`  激活guest用户


* `net user`  查看有哪些用户


* `net user 账户名`  查看账户的属性


* `net localGroup administrators 用户名/add`  把“用户”添加到管理员中使其具有管理员权限，注意:administrator后加s用复数


* `net user guest 12345`  用guest用户登录后用将密码改为12345


* `net password`  密码 更改系统登录密码


* `net share`  查看本地开启的共享


* `net share ipc$`  开启ipc$共享


* `net share ipc$ /del`  删除ipc$共享


* `net share c$ /del`  删除c:共享



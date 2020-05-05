## 网站篇
* http讲解
* 静态网站
* 动态网站
* 网站搭建

#####http协议：
* 超文本传输协议（HTTP，HyperText Transfer Protocol)是互联网上应用最为广泛的一种网络协议。所有的WWW文件都必须遵守这个标准。设计HTTP最初的目的是为了提供一种发布和接收HTML页面的方法。

#####请求头格式
#####请求头(request-header)
* Accept： 表明客户同端可接受的请求回应的媒体类型范围列表。星号“*”用于按范围将类型分组，用“*/*”指示可接受全部类型；用“type/*”指示可接受 type类型的所有子类型，如“ Accept: image/gif, image/jpeg, */*”；
Accept-Charset：客户端所能识别的字符集编码格式，格式：“Accept-Charset: 字符集1，字符集2”，如：“ Accept-Charset: iso-8859-1, GBK”；
* Accept-Language：客户端所能识别的语言，格式：“Accept-Language: 语言1，语言2”，如：” Accept-Language: zh-cn, en-us”；
* Host：客户请求的主机域名或主机IP，格式：“Host: 域名或IP[:端口号]”，如：“Host: localhost:80“，请求行中若有HTTP/1.1则必须有该请求头；
* User-Agent：表明用户所使用的浏览器标志，主要用于统计的目的；
* Referer：指明该请求是从哪个关联连接而来；
* Accept-Encoding：客户端所能识别的编码压缩格式，如：“Accept-Encoding: gzip, deflate”；
* If- Modified-Since：该字段与客户端缓存相关，客户端所访问的URL自该指定日期以来在服务端是否被修改过，如果修改过则服务端返回新的修改后 的信息，如果未修改过则服务器返回304表明此请求所指URL未曾修改过，如：“If-Modified-Since: Fri, 2 Sep 2006 19:37:36 GMT”；
* If-None-Match：该字段与客户端缓存相关，客户端发送URL请求的同时发送该字段及标识，如 果服务端的标识与客户端的标识一致，则返回304表明此URL未修改过，如果不一致则服务端返回完整的数据信息，如：“If-None-Match: 0f0a893aad8c61:253, 0f0a893aad8c61:252, 0f0a893aad8c61:251”；
* Cookie：为扩展字段，存储与客户端，向同一域名的服务端发送属于该域的cookie，如：“Cookie: MailUserName=whouse”；
响应格式
* ccept-Ranges：表明服务端接收的数据单位，如：“Accept-Ranges: bytes”, ；
* Location：服务端向客户端返回此信息以使客户端进行重定向
* Server：服务端返回的用于标识自己的一些信息，如：“ Server: Microsoft-IIS/6.0”；
* ETag：服务端返回的响应数据的标识字段，客户端可根据此字段的值向服务器发送某URL是否更新的信息；


#####服务器返回状态码
* 1xx：表明服务端接收了客户端请求，客户端继续发送请求；
* 2xx：客户端发送的请求被服务端成功接收并成功进行了处理；
* 3xx：服务端给客户端返回用于重定向的信息；
* 4xx：客户端的请求有非法内容；
* 5xx：服务端未能正常处理客户端的请求而出现意外错误。


举例：
* 100 : 服务端希望客户端继续；  
* 200 : 服务端成功接收并处理了客户端的请求；
* 301 : 客户端所请求的URL已经移走，需要客户端重定向到其它的URL；
* 304 : 客户端所请求的URL未发生变化；
* 400 : 客户端请求错误；
* 403 : 客户端请求被服务端所禁止；
* 404 : 客户端所请求的URL在服务端不存在；
* 500 : 服务端在处理客户端请求时出现异常；
* 501 : 服务端未实现客户端请求的方法或内容；
* 502 : 此为中间代理返回给客户端的出错信息，表明服务端返回给代理时出错；
* 503 : 服务端由于负载过高或其它错误而无法正常响应客户端请求；
* 504 " 此为中间代理返回给客户端的出错信息，表明代理连接服务端出现超时。


#####静态网站：
静态网站是指全部由HTML（标准通用标记语言的子集）代码格式页面组成的网站，所有的内容包含在网页文件中。网页上也可以出现各种视觉动态效果，如GIF动画、FLASH动画、滚动字幕等，而网站主要是静态化的页面和代码组成，一般文件名均以htm、html、shtml等为后缀。

#####动态网站:
动态网站并不是指具有动画功能的网站，而是指网站内容可根据不同情况动态变更的网站，一般情况下动态网站通过数据库进行架构。 动态网站除了要设计网页外，还要通过数据库和编程序来使网站具有更多自动的和高级的功能。动态网站体现在网页一般是以asp，jsp，php，aspx等技术，而静态网页一般是HTML（标准通用标记语言的子集）结尾，动态网站服务器空间配置要比静态的网页要求高，费用也相应的高，不过动态网页利于网站内容的更新，适合企业建站。动态是相对于静态网站而言。


###IIS 6.0 搭建ASP+SqlServer：



1.  管理工具--管理您的服务器
![avatar](/src/static/img/aspserver1.png)
2.  添加或删除角色
![avatar](/src/static/img/aspserver2.png)
3.  点击下一步
![avatar](/src/static/img/aspserver3.png)
4.  选择自定义配置，点击下一步
![avatar](/src/static/img/aspserver4.png)
5.  选择应用程序服务器，点击下一步
![avatar](/src/static/img/aspserver5.png)
6.  启用ASP.NET，点击下一步
![avatar](/src/static/img/aspserver6.png)
7.  配置向导完成
![avatar](/src/static/img/aspserver7.png)
8.  管理工具--IIS管理器
![avatar](/src/static/img/aspserver8.png)
9.  Web服务扩展，允许Active Server Pages
![avatar](/src/static/img/aspserver9.png)
10.  新建网站
![avatar](/src/static/img/aspserver10.png)
11.  点击下一步
![avatar](/src/static/img/aspserver11.png)
12.  输入网站描述，点击下一步
![avatar](/src/static/img/aspserver12.png)
13.  点击下一步
![avatar](/src/static/img/aspserver13.png)
14.  选择ASP源码路径，点击下一步
![avatar](/src/static/img/aspserver14.png)
15.  设置读取权限，点击下一步
![avatar](/src/static/img/aspserver15.png)
16.  点击完成
![avatar](/src/static/img/aspserver16.png)
17.  点击设置站点属性
![avatar](/src/static/img/aspserver17.png)
18.  设置主页入口
![avatar](/src/static/img/aspserver18.png)
19.  设置主目录执行权限，启用父路径
![avatar](/src/static/img/aspserver19.png)
20.  新建数据库
![avatar](/src/static/img/aspserver20.png)
21.  输入数据库名称，点击确定
![avatar](/src/static/img/aspserver21.png)
22.  点击还原数据库
![avatar](/src/static/img/aspserver22.png)
23.  选择目标数据库，选择备份文件
![avatar](/src/static/img/aspserver23.png)
24.  覆盖现有数据库，原始文件名路径可能不对，有时候注意需要修改
![avatar](/src/static/img/aspserver24.png)
25.  还原完成
![avatar](/src/static/img/aspserver25.png)
26.  启用SqlServer 1433端口
![avatar](/src/static/img/aspserver26.png)
27.  启用SqlServer 1433端口
![avatar](/src/static/img/aspserver27.png)
28.  修改源码数据库配置文件
![avatar](/src/static/img/aspserver28.png)
29.  浏览站点源码
![avatar](/src/static/img/aspserver29.png)
30.  本地访问测试
![avatar](/src/static/img/aspserver30.png)
31.  局域网访问测试
![avatar](/src/static/img/aspserver31.png)
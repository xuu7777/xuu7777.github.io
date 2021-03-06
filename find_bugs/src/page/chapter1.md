## 佛系心态
* 大小通吃
* 舍和不舍
* 耐心和细心
* 状态不好的时候别挖洞
* 佛系心态，漏洞收不收都坚持自信心态


## 利用搜索引擎

* 利用搜索引擎进行收集相关域名信息以及其他信息，是极为重要的。
* 搜索引擎的语法  是必须要掌握的。
* 谷歌搜索由于某些原因，所以不能正常访问，可以通过vpn，修改host，或者访问镜像网站。

* 镜像网站和搜索引擎：


1. https://ac.scmor.com/
2. https://coderschool.cn/1853.html
3. https://www.zizaifan.com/html/google.html
4. 百度搜索：https://www.baidu.com
5. crt.sh搜索：https://crt.sh/
6. nosec搜索：https://nosec.org/
7. 必应搜索: http://cn.bing.com/
8. 中国搜索:http://www.chinaso.com/ ...


## 域名信息收集
* 收集二、三等级域名信息是极为重要的：


1. subDomainsBrute:https://github.com/lijiejie/subDomainsBrute
2. 子域名挖掘机：https://www.webshell.cc/6384.html


* 同时也需要一个强大的字典


1. Blasting_dictionary：https://github.com/rootphantomer/Blasting_dictionary
2. fuzz_dict：https://github.com/TuuuNya/fuzz_dict


## 巧用各大平台


* 利用一些域名解析网站获取域名相关的注册信息，以及其他关联的域名注册信息，解析信息等等，然后也可以利用QQ群，百度贴吧等交互平台查询关于企业以及员工方面的信息，当然也可以用Github这个平台进行索索相关域名信息以及其他信息。


## 测试过程中收集


* 在进行漏洞挖掘的过程中，养成一个信息收集的习惯是一个必要的挖掘技巧。在测试不同的平台都要进行信息收集，当然收集这些信息不是为了其他用途，而是为了利用这些信息去挖掘更深的潜在危害的漏洞。


## 字典收集


* 软件是帮你自动化，其关键成功的因素，是靠你的字典全不全，根据企业信息和挖掘过程中产生的信息以及网上公布的信息进行不同组合，然后在测试不同平台的时候再从其中筛选出可靠的，然后组成一个迷你的强悍字典，以上就是关于Web方面的信息收集思路。


## App方面的信息收集


### 利用不同App市场
* 在大家想要测试App问题的时候，思路要扩大化，不管App是否还维护，只要还在上线，只要域名还可以访问，那么就要去进行测试，大家要学会在不同平台搜索App，然后凭借自己对企业的了解去找到潜在的相关App。因为一些App并不是以企业昵称命名的，比如你在安卓市场搜索企业相关App，然后你再去小米应用市场进行搜索企业相关App，可能你就会发现有搜索出来了几个新的App，因为一个平台并不会包含企业以前和现在的所有App，所以要取不同的App市场进行收集App。


### 本地App域名提取
* 一些比较隐私性的域名可能包含在App本地文件当中，比如某内部员工登录系统的App，但是由于有证书校验，你也抓不到数据包，此时你可以查看App的本地文件，然后就可以看到本地App内调用的是哪些域名，然后还有相关域名，从App内提取域名的相关程序很多。手机端免Root抓包工具：https://www.cr173.com/soft/1058109.html

##### 总结：信息的收集就是挖掘漏洞的一个基础步骤，学会在不同方向进行信息收集是决定你能否挖掘出漏洞的一个关键因素
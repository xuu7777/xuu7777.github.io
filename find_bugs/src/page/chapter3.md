## 常规信息收集


## 一、常规信息收集之域名


### 备案号查询
* 备案号查询是网站是否合法经营的标志，可随时到国家工业和信息化部网站备案系统上查询该ICP备案的相关详细信息。
* 网站：http://www.beianbeian.com/


点击反查，即可出现百度公司的相关资产。


![avatar](/src/static/img/bah1.png)


#### 子域名发现的原理


#### 利用现有的搜索引擎
* 网页搜索引擎（如：谷歌等）


* 空间搜索引擎（如：Shodan等）


* SSL证书（如：crt.sh等）


#### 爆破又分为两种：
* 直接访问子域名


* 利用DNS请求


#### 其他泄露信息：
* 如 crossdomain.xml 文件等


* 爬虫递归爬取等


* DNS域传送漏洞等


## 二、常规信息收集之子域名：暴力枚举


##### 工具1：
* Layer子域名挖掘机5.0 SAINTSEC更新版


* Author:Seay


* Modify：akast、dark3r


###### 支持服务接口、暴力搜索、同服挖掘三种模式，支持打开网站，复制域名、复制IP、复制CDN、支持导出检测结果等功能。


##### 工具2：
* subdomainsBurte


* Author：李劼杰


* 这个脚本的主要目标是发现其他工具无法探测到的域名。如Google，aizhan，fofa。高频扫描每秒DNS请求次数可超过1000次


* 下载地址：https://github.com/lijiejie/subDomainsBrute


##### 推荐工具：
* OneForAll

* 下载地址：https://github.com/shmilylty/OneForAll


## 三、常规信息收集之子域名：SSL证书查询


##### 推荐网站1：
* 推荐网站1：https://censys.io/ipv4


![avatar](/src/static/img/censys.png)


##### 推荐网站2：
* 推荐网站2：https://crt.sh/


![avatar](/src/static/img/crt.png)


##### 推荐网站3：
* 推荐网站3：https://dnsdumpster.com/


![avatar](/src/static/img/dns1.png)


## 四、常规信息收集之子域名：第三方查询
##### 推荐网站1：
* 推荐网站1：https://www.shodan.io/


![avatar](/src/static/img/sd.png)


##### 推荐网站2：
* 推荐网站2：https://fofa.so/


![avatar](/src/static/img/fofa.png)


## 五、常规信息收集之IP段
##### 推荐网站1：
* 推荐网站1：https://www.shodan.io/


![avatar](/src/static/img/sd.png)



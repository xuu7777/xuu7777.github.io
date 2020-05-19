### 逻辑漏洞


* 逻辑漏洞是指由于程序逻辑输入管控不严，导致程序不能够正常处理或处理错误，一般出现在登录注册、密码找回、信息查看、交易支付金额等。


#### 逻辑漏洞 - 任意用户密码重置


![avatar](/src/static/img/ljld1.png)
![avatar](/src/static/img/ljld2.png)
* https://cloud.tencent.com/developer/article/1607702


#### 逻辑漏洞 - 验证码爆破


![avatar](/src/static/img/ljld3.png)


#### 逻辑漏洞 - 万能验证码


![avatar](/src/static/img/ljld4.png)


#### 由于验证码在本地生产导致的任意用户注册


* 发送手机号验证码请求并拦截，发现在请求中已经生成了验证码，所以记下验证码后放包==》填写信息==》注册成功


![avatar](/src/static/img/ljld5.png)
![avatar](/src/static/img/ljld6.png)
![avatar](/src/static/img/ljld7.png)


#### 逻辑漏洞 - 验证码爆破
![avatar](/src/static/img/ljld8.png)


#### 无限制使用一元买价值899的vip会员
* 发起一个正常的购买请求，拦截请求数据包，修改参值，购买成功
* 注：coupon=优惠券，discount=折扣，product=这里可以看出来是一年的vip


![avatar](/src/static/img/ljld9.png)
![avatar](/src/static/img/ljld10.png)


#### 对登录密码框进行FUZZ
* 无验证码==》尝试admin、admin==》提醒密码错误==》使用密码字典


#### 对未知URL参数进行FUZZ
* 访问url报错→对url参数在burpsuite的intruder进行添加字典爆破→发现有效参数有：”path=/etc/passwd”


![avatar](/src/static/img/ljld11.png)
![avatar](/src/static/img/ljld12.png)

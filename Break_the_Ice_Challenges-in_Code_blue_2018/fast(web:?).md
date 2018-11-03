# ▼▼▼fast(web:?)▼▼▼

```
import binascii
import requests
import base64
#import urllib.parse

proxy={"http": "http://127.0.0.1:8080"}

url='http://web3.sl7ctf.cf/'
payload = {'SL7': 'value1'}
headers = {'User-Agent': 'Sample Header','Cookie':'PHPSESSID=ulo65saf1ntv5acpkr0o484i86'}

#SL7
r=requests.post(url, headers=headers,data=payload,proxies=proxy)
#print (r.content)

#---
print (r.headers['Feed-This'])
print ("---------")

value2=r.headers['Feed-This'].decode('hex')
print (value2)
print ("---------")

value2=value2.replace('%3D', '=')
print (value2)
print ("---------")

value2=base64.b64decode(value2)
print (value2)
print ("---------")



url='http://web3.sl7ctf.cf/'
payload = {'SL7': value2 }
headers = {'User-Agent': 'Sample Header','Cookie':'PHPSESSID=ulo65saf1ntv5acpkr0o484i86'}

s=requests.post(url, headers=headers,data=payload,proxies=proxy)
print (s.content)
print (s.headers)
```

↓

```
HTTP/1.1 200 OK
Date: Thu, 01 Nov 2018 07:37:27 GMT
Server: Apache/2.4.10 (Debian)
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Pragma: no-cache
Feed-This: 576d5a6b4d446448635577355a6c5a44595556696141253344253344
Vary: Accept-Encoding
Content-Length: 217
Connection: close
Content-Type: text/html; charset=UTF-8

<script>console.log('Post decode3([Feed-This]) as [SL7] as fast as you can, then only you will get flag')</script><center><h1> Congratulation !!!!! here is your flag SL7{7365d2dc34ec07ff7a834fd2fbbe9bf4}</h1></center>
SL7{7365d2dc34ec07ff7a834fd2fbbe9bf4}
```

↓

`SL7{7365d2dc34ec07ff7a834fd2fbbe9bf4}`

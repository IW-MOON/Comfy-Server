# Comfy-Server

### 1. 서버 아키텍처

![수정됨_server_archi](https://user-images.githubusercontent.com/72685070/103410350-375a7580-4bae-11eb-9999-6201cb7b14ab.png)


### 2. Nginx
> #### 1) Listen HTTP 80 Port
> #### 2) Listen HTTPS 443 Port

### 3. Express(Node)
> #### 1) Node Modules
>> * mysql
>> * aws-sdk
>> * winston
>> * winston-daily-rotate-file
>> * jsonwebtoken
>> * google-auth-library
![routes1](https://user-images.githubusercontent.com/72685070/103410629-8523ad80-4baf-11eb-97d2-1b0dae73a7b2.png)

> #### 2) Node Modules
>> * source/app.js
>>> + app.use('/', indexRouter)
>> * source/routes/index.js
>> * source/routes/login/index.js

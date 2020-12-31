# Comfy-Server

### 1. 서버 아키텍처

![수정됨_server_archi](https://user-images.githubusercontent.com/72685070/103410350-375a7580-4bae-11eb-9999-6201cb7b14ab.png)

#

### 2. Nginx
> #### 1) Listen HTTP 80 Port
> #### 2) Listen HTTPS 443 Port
#
### 3. Express(Node)
> #### 1) Node Modules
>> * mysql
>> * aws-sdk
>> * winston
>> * winston-daily-rotate-file
>> * jsonwebtoken
>> * google-auth-library




> #### 2) Node Modules



>> ![routes1](https://user-images.githubusercontent.com/72685070/103410629-8523ad80-4baf-11eb-97d2-1b0dae73a7b2.png)


>> * source/app.js
>>> - _app.use('/', indexRouter)_
>> ![routes2](https://user-images.githubusercontent.com/72685070/103411082-87870700-4bb1-11eb-9fb1-b0f9d6c634a4.png)
>> * source/routes/index.js
>>> - _const login = require('./login/index')_
>> * source/routes/login/index.js
>>> - _const controller = require('./login.controller')_
>>> - _router.post('/auth', controller.main)_

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




> #### 2) Routes구조





>> * source/app.js


>> ![routes1](https://user-images.githubusercontent.com/72685070/103410629-8523ad80-4baf-11eb-97d2-1b0dae73a7b2.png)


>>> - _app.use('/', indexRouter)_


>> * source/routes/index.js

>> ![routes2](https://user-images.githubusercontent.com/72685070/103411082-87870700-4bb1-11eb-9fb1-b0f9d6c634a4.png)


>>> - _const login = require('./login/index')_
>> * source/routes/login/index.js

>> ![routes3](https://user-images.githubusercontent.com/72685070/103411127-c87f1b80-4bb1-11eb-994f-7e76a3fb4a7a.png)


>>> - _const controller = require('./login.controller')_
>>> - _router.post('/auth', controller.main)_

>> * source/routes/login/login.controller.js
>>> - _const dao = require('./login.dao')_
>>> - _const auth_config_dev = require('/source/config/auth_config_dev.js');_
>>> ``` Javascript
>>> exports.main = (req, res, next) => {
>>>   const result = await dao.selectToken(payload);
>>> }
>> * source/routes/login/login.dao.js
>>> - _const db_config_dev = require('/source/config/db_config_dev.js')_
>>> - _const conn = db_config_dev.init()_
>>> ``` Javascript
>>> db_config_dev.connect(conn);
>>> module.exports = {
>>>   selectToken : function(payload){
>>>     var sql = 'SELECT token FROM user WHERE GOOGLE_ID = ?';
>>>     var params = [payload.sub];
>>>     try {
>>>       return new Promise(function(resolve, reject){
>>>         conn.query(sql, params, function(err,rows){
>>>           if(err) reject(err);
>>>           resolve(rows);
>>>         });
>>>       });
>>>     }
>>>   }
>>> }

# Mapty Pro Restful API Specification

## 用户管理

###  注册

```json
POST /auth/register

请求：
{
    "username": "string",
    "password": "string",
    "email": "string",
}

响应：
//成功
{
  "code": 200,
  "description": "Register successfully.",
  "timestamp": "2022-11-19T02:07:50.165+0000",
  "data": {
    "id": 11,
    "username": "string",
    "password": "string",
    "email": "string"
  }
}

// 失败
{
  "code": 400,
  "description": "User has existed.",
  "timestamp": "2022-11-19T02:07:27.129+0000",
  "data": null
}
```

### 登录

```json
POST /auth/login

请求：
{
    "username": "string",
    "password": "string",
    "email": "string",
}

响应：
//成功
{
  "code": 200,
  "description": "Login successfully.",
  "timestamp": "2022-11-19T02:03:41.510+0000",
  "data": {
    "id": 1,
    "username": "string",
    "password": "string",
    "email": "string"
  }
}

// 失败
{
  "code": 400,
  "description": "User does not exist.",
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}
```

### 重置密码

```json
POST /auth/resetPassword

请求
// header
"username": "string"
"password": "string"
// body
{
    "oldPassword": "string",
    "newPassword": "string",
}

响应
// 成功
{
  "code": 200,
  "description": "Reset password successfully.",
  "timestamp": "2022-11-19T02:03:41.510+0000",
  "data": {
    "id": 1,
    "username": "string",
    "password": "string",
    "email": "string"
  }
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.",
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}

```

### 更新用户信息

```json
POST /auth/updateUserProfile

请求
// header
"username": "string"
"password": "string"
// body
{
    "newUsername": "string",
    "newEmail": "string"
}

响应
// 成功
{
  "code": 200,
  "description": "Update user profile successfully.",
  "timestamp": "2022-11-19T02:03:41.510+0000",
  "data": {
    "id": 1,
    "username": "string",
    "password": "string",
    "email": "string"
  }
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.", // Password does not change.
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}

```


## 内容管理

### 获取用户的 Journey

```json
GET /journey/getByUser

请求：
// header
"username": "string"
"password": "string"
// body
N/A


响应：
// 成功
{
   "code":200,
   "description":"Get data successfully.",
   "timestamp":"2022-11-19T01:54:46.832+0000",
   "data":[
      {
         "id":0,
         "title":"string",
         "description":"string",
         "userId": 0,
         "waypoints":[
            {
               "label":"string",
               "time":"string",
               "coordinate": "(45, 45)"
            },
            ...
         ]
      },
      ...
   ]
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.",
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}
```

### 创建 Journey

```json
POST /journey/create

请求：
// header
"username": "string"
"password": "string"
// body
{
   "title":"string",
   "description":"string",
   "userId": 0,
   "waypoints":[
      {
         "label":"string",
         "time":"string",
         "coordinate": "(45, 45)"
      },
      "..."
   ]
}

响应：
// 成功
{
   "code":200,
   "description":"Create journey successfully.",
   "timestamp":"2022-11-19T01:54:46.832+0000",
   "data": null,
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.", // 或者 Journey has existed.
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}
```

## 评论系统

### 发送评论

```json
POST /comment/sendCommentByUser

请求：
// header
"username": "string"
"password": "string"
// body
{
    "targetUsername": "string",
    "content":"string",
    "journeyTitle": "string",
}

响应：
// 成功
{
   "code":200,
   "description":"Send journey comments successfully.",
   "timestamp":"2022-11-19T01:54:46.832+0000",
   "data": null
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.", // 或者 Journey does not exist.
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}
```

### 查询评论 

```json
POST /comment/getCommentByJourney

请求：
// header
"username": "string"
"password": "string"
// body
{
   "username": "string",
   "journeyTitle": "string",
}

响应：
// 成功
{
   "code":200,
   "description":"Get journey comments successfully.",
   "timestamp":"2022-11-19T01:54:46.832+0000",
   "data":[
      {
         "userId":0,
         "sourceUsername":"string",
         "content":"string",
         "time":"2022-11-19T01:54:46.832+0000"
      },
      {
         "userId":1,
         "sourceUsername":"string",
         "content":"string",
         "time":"2022-11-19T01:54:46.832+0000"
      },
      "..."
   ]
}

// 失败
{
  "code": 400,
  "description": "Authorization failed.", // 或者 Journey does not exist.
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": null
}
```
# 登录

**URL** `/auth/login`

**Method:** `POST`

**Auth required** : `NO`

**Data constraints**

  ```json
  {
    "username": "[登录的用户名]",
    "email": "[登录的邮箱]",
    "password": "[用户名或邮箱对应的密码]]"
  }
  ```

**Data example**

  ```json
  {
    "username": "test-username",
    "email": "iloveauth@example.com",
    "password": "abcd1234"
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
  {
    "code": 200,
    "description": "Login successfully.",
    "timestamp": "2022-11-19T02:03:41.510+0000",
    "data": {
      "id": 1,
      "username": "string",
      "email": "string",
      "password": "string"
    }
  }
  ```

 
## Error Response:

**Code** : `400 FAILED`

**Content example**

  ```json
  {
    "code": 400,
    "description": "User does not exist.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data": null
  }
  ```

# 重置密码

**URL** `/auth/resetPassword`

**Method:** `POST`

**Auth required** : `YES`

**Data constraints**

  ```json
  {
    "oldPassword": "[旧的密码]",
    "newPassword": "[新的密码]"
  }
  ```

**Data example**

  ```json
  {
    "oldPassword": "abcd1234",
    "newPassword": "abcd123456"
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
  {
    "code": 200,
    "description": "Reset password successfully.",
    "timestamp": "2022-11-19T02:03:41.510+0000",
    "data": {
      "id": 1,
      "username": "test-username",
      "password": "abcd1234",
      "email": "iloveauth@example.com"
    }
  }
  ```

 
## Error Response:

**Code** : `400 FAILED`

**Content example**

  ```json
  {
    "code": 400,
    "description": "Authorization failed.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data": null
  }
  ```

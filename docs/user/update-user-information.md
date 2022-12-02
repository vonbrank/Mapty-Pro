# 更新用户信息

**URL** `/auth/updateUserProfile`

**Method:** `POST`

**Auth required** : `YES`

**Data constraints**

  ```json
  {
    "newUsername": "string",
    "newEmail": "string"
  }
  ```

**Data example**

  ```json
  {
    "newUsername": "test-username",
    "newEmail": "iloveauth@example.com"
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
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

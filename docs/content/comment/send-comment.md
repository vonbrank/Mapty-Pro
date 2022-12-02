# 发送评论

**URL** `/comment/sendCommentByUser`

**Method:** `POST`

**Auth required** : `YES`

**Data constraints**

  ```json
  {
    "targetUsername": "[收到评论的用户]",
    "content":"[评论内容]",
    "journeyTitle": "[评论所属的 Journey]",
  }
  ```

**Data example**

  ```json
  {
    "targetUsername": "test-target-username",
    "content":"Hello world.",
    "journeyTitle": "test-journey-title",
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
  {
    "code":200,
    "description":"Send journey comments successfully.",
    "timestamp":"2022-11-19T01:54:46.832+0000",
    "data": null
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

  OR

  ```json
  {
    "code": 400,
    "description": "Journey does not exist.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data": null
  }
  ```

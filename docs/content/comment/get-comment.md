# 查询评论

**URL** `/comment/getCommentByJourney`

**Method:** `POST`

**Auth required** : `NO`

**Data constraints**

  ```json
	{
		"username": "[Journey 的所有者]",
		"journeyTitle": "[Journey 的标题]",
	}
  ```

**Data example**

  ```json
	{
		"username": "test-username",
		"journeyTitle": "test-journey-title",
	}
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
  {
    "code": 200,
    "description": "Get journey comments successfully.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data":[
        {
          "userId":0,
          "sourceUsername": "string",
          "targetUsername": "string",
          "content": "string",
          "time": "2022-11-19T01:54:46.832+0000"
        },
        {
          "userId":1,
          "sourceUsername": "string",
          "targetUsername": "string",
          "content": "string",
          "time": "2022-11-19T01:54:46.832+0000"
        }
    ]
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

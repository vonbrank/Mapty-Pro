# 创建 Journey

**URL** `/journey/create`

**Method:** `POST`

**Auth required** : `YES`

**Data constraints**

  ```json
  {
    "title":"[Journey 的标题]",
    "description":"[Journey 的描述]",
    "userId": "[Journey 创建者的 id]",
    "waypoints":[
        {
          "label":"[路径点的名字]]",
          "time":"[到达路径点的时间（格式为 hh-mm ）]",
          "coordinate": "[路径点的坐标（格式为）(lat, lng)]"
        }
    ]
  }
  ```

**Data example**

  ```json
  {
    "title":"string",
    "description":"string",
    "userId": 0,
    "waypoints":[
      {
        "label":"place-name",
        "time":"8-0",
        "coordinate": "(45, 45)"
      }
    ]
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
  {
    "code":200,
    "description":"Create journey successfully.",
    "timestamp":"2022-11-19T01:54:46.832+0000",
    "data": null,
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
    "description": "Journey has existed.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data": null
  }
  ```

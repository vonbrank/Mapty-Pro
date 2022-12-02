# 创建 Journey

**URL** `/journey/getByUser`

**Method:** `GET`

**Auth required** : `YES`

**Data constraints**

N/A

**Data example**

N/A

## Success Response:

**Code** : `200 OK`

**Content example**

  ```json
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

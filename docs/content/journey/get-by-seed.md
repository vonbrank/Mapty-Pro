# 随机获取一定数量的 Journey

**URL** `/journey/getBySeed`

**Method:** `GET`

**Auth required** : `NO`

**Data constraints**

  ```json
  {
    "seed": "[随机种子]",
    "count": "[Journey 的数量]"
  }
  ```

  相同的种子可以生成相同的序列

**Data example**

  ```json
  {
    "seed": "998244353",
    "count": "5"
  }
  ```

## Success Response:

**Code** : `200 OK`

**Content example**

```json
{
  "code": 200,
  "description": "Get data successfully.",
  "timestamp": "2022-11-19T01:54:46.832+0000",
  "data": [
    {
      "id": 0,
      "title": "string",
      "description": "string",
      "userId": 0,
      "waypoints": [
        {
            "label": "string",
            "time": "string",
            "coordinate": "(45, 45)"
        }
      ]
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
    "description": "Error occurred.",
    "timestamp": "2022-11-19T01:54:46.832+0000",
    "data": null
}
```

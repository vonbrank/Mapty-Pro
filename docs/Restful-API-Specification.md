# Mapty Pro Restful API Specification

Inspired by [@jamescooke](https://github.com/jamescooke)'s [restapidocs](https://github.com/jamescooke/restapidocs).

## 用户验证

`Auth required` 字段为 `YES` 的 API 需要进行用户验证，具体来说，其请求的 header 部分包含用户名和密码，格式如下：

```txt
"username": "string"
"password": "string"
```

收到请求后应首先验证用户名和密码的对应关系，验证失败的返回 `400 Authorization failed.` 

## 用户管理

+ [注册](./user/register.md)：`POST /auth/register`
+ [登录](./user/login.md)：`POST /auth/login`
+ [重置密码](./user/reset-password.md)：`POST /auth/resetPassword`
+ [更新用户信息](./user/update-user-information.md) `POST /auth/updateUserProfile`

## 内容管理

+ [获取用户的 Journey](./content/journey/get-by-user.md) `GET /journey/getByUser`
+ [随机获取一定数量的 Journey](./content/journey/get-by-seed.md) `GET /journey/getByUser`
+ [创建 Journey](./content/journey/create-journey.md) `POST /journey/create`

## 评论系统

+ [发表评论](./content/comment/send-comment.md) `POST /comment/sendCommentByUser`
+ [查询评论](./content/comment/get-comment.md) `POST /comment/getCommentByJourney`


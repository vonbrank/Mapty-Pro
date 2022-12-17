# Mapty Pro

这是一个简单的 Web 前后端分离项目，是哈尔滨工业大学 2022 年秋季学期【CS33461：面向服务的软件系统】课程的组队大作业。本项目使用 TypeScript(React) + Java(Spring Boot) + MySQL 实现前后端分离，开发灵感源自[Jonas Schmedtmann]() 的 [Mapty]() ，开发技术参考了 [Antabot](https://github.com/Antabot) 的 [White-Jotter](https://github.com/Antabot/White-Jotter)。受开发周期问题影响，本项目几乎未考虑任何安全防护问题，因此请勿将其用于生产环境。

## 总览

[Mapty Pro](https://github.com/vonbrank/Mapty-Pro) 是一个地图应用，允许用户创建并登录账户，同时支持修改个人信息、重置密码等。

![zWIb38.png](https://s1.ax1x.com/2022/12/10/zWIb38.png)

`Journey` 是 Mapty Pro 的核心概念，可以用于描述一个已发生或计划中的行程。一个 `Journey`  包含一个标题和一段描述，以及一组 `Waypoint` 的集合，每个 `Waypoint` 包含一个 tag 和一个经纬度坐标。

Mapty Pro 支持显示地图元素与渲染 `Journey` ，用户亦可使用编辑器创建 `Journey` 。

## 架构

Mapty Pro 采用前后端分离的 Web 应用架构。

![zWH7ZQ.md.png](https://s1.ax1x.com/2022/12/10/zWH7ZQ.md.png)

目前前端项目部署在 [app.netlify.com](https://app.netlify.com/) ，后端项目与数据库均运行在 Docker 容器中，部署在私有的云服务器上。

## 技术栈

### 前端

+ TypeScript: JavaScript 的超集，实现前端项目的类型安全
+ React: 前端框架，使用 TSX/JSX 描述组件树，构建虚拟 DOM 并与物理 DOM 同步，实现声明式渲染
+ Redux: 状态管理框架，实现 React 的跨组件通信
+ Axios: HTTP 库，使得前端易于与后端进行 HTTP 通信
+ Leaflet: 地图库，实现前端的地图渲染。旧版的 Leaflet 需要手动操作 DOM 树，此处使用 React Leaflet —— 一个基于 React 的 Leaflet 封装

### 后端

+ Java: 主流的后端编程语言
+ Spring Boot: 后端框架，使得 Restful API 易于编写
+ Spring Data JPA: ORM 框架，使得后端开发中免于使用 SQL 语句直接操作数据库
+ Docker: 虚拟化容器

### 数据库

+ MySQL: 流行的关系型数据库

## 私有化部署

可分别参考前端与后端项目的项目文档：

+ 前端项目：https://github.com/vonbrank/Mapty-Pro-Frontend

+ 后端项目：https://github.com/vonbrank/Mapty-Pro-Backend

## 其他内容

+ Restful API 规约：[Mapty Pro Restful API Specification](./docs/Restful-API-Specification.md)

## 参考文献

+ Mapty: https://mapty.netlify.app
+ White-Jotter: https://github.com/Antabot/White-Jotter

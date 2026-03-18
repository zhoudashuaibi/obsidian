---
title: CORS：预检请求与携带凭证
tags:
  - 网络与浏览器
  - 7.1 HTTP
  - 面试
status: active
date: 2026-03-18
---

# CORS：预检请求与携带凭证

## 📌 核心概念
CORS 是浏览器的跨域访问控制机制。简单请求可直接发出，非简单请求会先发 OPTIONS 预检，服务端通过一组 Access-Control-* 响应头声明是否允许。

## 💻 代码示例
```http
Access-Control-Allow-Origin: https://app.example.com
Access-Control-Allow-Methods: GET,POST,PUT
Access-Control-Allow-Headers: Content-Type, Authorization
Access-Control-Allow-Credentials: true
```

## 🛠 实战场景
前后端分离、本地开发联调、主站调用子域接口、带 Cookie 的跨域登录都离不开 CORS。

## 🎯 面试怎么问
- 什么请求会触发预检？
- 为什么携带凭证时不能把 Allow-Origin 写成 *？
- 预检请求可以缓存吗？

## ⚠️ 易错点 / 高阶拓展
CORS 是浏览器限制，不是服务端能力。服务端“收到了请求”不代表浏览器允许 JS 读取响应。

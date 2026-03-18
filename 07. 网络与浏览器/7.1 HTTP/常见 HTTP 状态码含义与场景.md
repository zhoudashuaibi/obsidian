---
title: 常见 HTTP 状态码含义与场景
tags:
  - 网络与浏览器
  - 7.1 HTTP
  - 面试
status: active
date: 2026-03-18
---

# 常见 HTTP 状态码含义与场景

## 📌 核心概念
HTTP 状态码表示一次请求的处理结果。常见面试重点集中在 2xx 成功、3xx 重定向、4xx 客户端错误、5xx 服务端错误，以及它们在缓存、鉴权、容灾里的实际语义。

## 💻 代码示例
```text
200 OK
201 Created
204 No Content
301 Moved Permanently
304 Not Modified
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
429 Too Many Requests
500 Internal Server Error
502 Bad Gateway
503 Service Unavailable
```

## 🛠 实战场景
接口设计、统一错误码映射、网关层限流、静态资源缓存都会用到状态码，不只是“背数字”。

## 🎯 面试怎么问
- 401 和 403 有什么区别？
- 304 为什么不算重定向页面跳转？
- 502 和 503 分别说明什么问题？

## ⚠️ 易错点 / 高阶拓展
很多人把业务失败一律返回 200 + code 字段。实际对外 API、监控告警、缓存协商都更依赖正确的 HTTP 状态码。

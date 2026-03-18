---
title: Cookie vs Session vs JWT 对比
tags:
  - 网络与浏览器
  - 7.1 HTTP
  - 面试
status: active
date: 2026-03-18
---

# Cookie vs Session vs JWT 对比

## 📌 核心概念
Cookie 是浏览器存储机制，Session 是服务端会话状态，JWT 是自包含令牌格式。三者常组合使用：Cookie 负责自动携带，Session/JWT 负责身份表达。

## 💻 代码示例
```http
Set-Cookie: sid=abc; HttpOnly; Secure; SameSite=Lax
Authorization: Bearer <jwt>
```

## 🛠 实战场景
做登录态设计时，需要在“服务端可控”“跨域”“多端接入”“是否支持无状态扩容”之间取舍。

## 🎯 面试怎么问
- Cookie、Session、JWT 分别解决什么问题？
- JWT 为什么适合分布式，但又难以主动失效？
- 把 JWT 放在 localStorage 有什么风险？

## ⚠️ 易错点 / 高阶拓展
不要把 JWT 理解成更安全的 Session。JWT 只是另一种身份凭证表达方式，安全性仍取决于存储位置、签名算法、失效策略和传输链路。

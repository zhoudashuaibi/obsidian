---
title: CSRF：攻击原理与 Token 和 SameSite 防御
tags:
  - 网络与浏览器
  - 7.3 安全
  - 面试
status: active
date: 2026-03-18
---

# CSRF：攻击原理与 Token 和 SameSite 防御

## 📌 核心概念
CSRF 利用了浏览器会自动携带 Cookie 的特性，诱导已登录用户在第三方站点发起伪造请求。常见防御是 CSRF Token、SameSite Cookie、二次验证和严格校验来源。

## 💻 代码示例
```http
Set-Cookie: sid=abc; HttpOnly; Secure; SameSite=Lax
X-CSRF-Token: 7f9a2b
```

## 🛠 实战场景
转账、改密码、修改邮箱等高风险写操作必须考虑 CSRF。

## 🎯 面试怎么问
- CSRF 为什么通常依赖 Cookie 登录态？
- SameSite 有哪些取值？
- 为什么 GET 也可能有风险？

## ⚠️ 易错点 / 高阶拓展
把接口改成 POST 并不能天然防 CSRF。关键在于请求是否能被第三方站点无感触发并自动带上身份信息。

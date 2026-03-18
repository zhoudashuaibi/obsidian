---
title: CSP 内容安全策略
tags:
  - 网络与浏览器
  - 7.3 安全
  - 面试
status: active
date: 2026-03-18
---

# CSP 内容安全策略

## 📌 核心概念
CSP 通过响应头限制页面可加载和执行的资源来源，是对 XSS、第三方脚本失控的重要补充。它的核心是白名单和执行约束，而不是内容过滤。

## 💻 代码示例
```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.example.com; object-src 'none'; base-uri 'self' 
```

## 🛠 实战场景
后台系统、运营平台、接入多个第三方 SDK 的站点，通常都会用 CSP 缩小脚本执行面。

## 🎯 面试怎么问
- CSP 能解决什么问题？
- nonce 和 hash 的用途是什么？
- 为什么上线前常先用 Report-Only？

## ⚠️ 易错点 / 高阶拓展
CSP 不是银弹。策略过宽等于没配，策略过严又可能打挂业务，所以常先观测再逐步收紧。

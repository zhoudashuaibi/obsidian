---
title: Cookie vs localStorage vs sessionStorage vs IndexedDB 对比
tags:
  - 网络与浏览器
  - 7.4 存储
  - 面试
status: active
date: 2026-03-18
---

# Cookie vs localStorage vs sessionStorage vs IndexedDB 对比

## 📌 核心概念
几种前端存储方案在容量、生命周期、是否自动携带到服务端、读写方式上差异明显。Cookie 小且会随请求发送，Web Storage 简单同步，IndexedDB 适合结构化大数据离线存储。

## 💻 代码示例
```js
localStorage.setItem('theme', 'dark')
sessionStorage.setItem('tabId', 'a1')
await db.put('users', { id: 1, name: 'zhou' })
```

## 🛠 实战场景
做登录态、草稿箱、离线缓存、客户端配置持久化时，选错存储介质会直接影响安全性和性能。

## 🎯 面试怎么问
- 这几种存储的容量和生命周期差异？
- 为什么不建议把敏感 token 放 localStorage？
- IndexedDB 适合哪些场景？

## ⚠️ 易错点 / 高阶拓展
localStorage 是同步 API，大量读写会阻塞主线程；Cookie 也不适合塞大对象，会增加每次请求体积。

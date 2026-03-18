---
title: Koa vs Express 核心差异
tags:
  - Node.js
  - 8.3 Express 
  - 面试
status: active
date: 2026-03-18
---

# Koa vs Express 核心差异

## 📌 核心概念
Express 更早、更生态化，中间件大量依赖回调链；Koa 更轻量，强调 async/await 和更清晰的请求响应封装。两者都能做 Web 服务，但编程体验和抽象层次不同。

## 💻 代码示例
```js
// Express
app.get('/users', (req, res) => res.json([]))

// Koa
router.get('/users', (ctx) => { ctx.body = [] })
```

## 🛠 实战场景
技术选型时通常会从生态成熟度、团队习惯、对中间件控制能力三个角度比较。

## 🎯 面试怎么问
- 为什么 Koa 被称为更现代？
- Express 和 Koa 的上下文对象有什么差别？
- 项目选型时你会怎么选？

## ⚠️ 易错点 / 高阶拓展
不要把 Koa 等同于“性能一定更强”。多数业务里差异更多体现在模型和开发体验，而不是绝对吞吐。

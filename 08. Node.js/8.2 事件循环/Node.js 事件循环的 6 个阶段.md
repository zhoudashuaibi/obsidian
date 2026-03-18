---
title: Node.js 事件循环的 6 个阶段
tags:
  - Node.js
  - 8.2 事件循环
  - 面试
status: active
date: 2026-03-18
---

# Node.js 事件循环的 6 个阶段

## 📌 核心概念
Node.js 事件循环基于 libuv，常见六个阶段依次是 timers、pending callbacks、idle/prepare、poll、check、close callbacks。不同队列的执行时机差异决定了回调顺序。

## 💻 代码示例
```text
timers -> pending -> idle/prepare -> poll -> check -> close
process.nextTick queue / microtask queue 会穿插在阶段之间清空
```

## 🛠 实战场景
排查回调顺序、理解 setImmediate 与 setTimeout 差异、分析 IO 任务为什么先执行，都离不开事件循环阶段模型。

## 🎯 面试怎么问
- Node 事件循环有哪些阶段？
- poll 阶段主要做什么？
- 微任务在 Node 中何时执行？

## ⚠️ 易错点 / 高阶拓展
不要把浏览器事件循环模型原封不动套到 Node。Node 还要考虑 libuv 阶段和 nextTick 的特殊优先级。

---
title: Node.js 与浏览器事件循环的差异
tags:
  - Node.js
  - 8.2 事件循环
  - 面试
status: active
date: 2026-03-18
---

# Node.js 与浏览器事件循环的差异

## 📌 核心概念
浏览器更强调渲染帧与宏微任务协作，Node.js 更强调 libuv 阶段与 IO 调度。两者都有微任务，但 Node 额外有 process.nextTick 且优先级更高。

## 💻 代码示例
```text
浏览器: script -> microtask -> render -> macrotask
Node: phase -> nextTick -> microtask -> next phase
```

## 🛠 实战场景
同样一段异步代码在浏览器和 Node 执行顺序可能不同，SSR 或同构项目面试常拿这点提问。

## 🎯 面试怎么问
- Node 和浏览器的微任务处理有何不同？
- 为什么浏览器里没有 libuv 六阶段？
- SSR 环境下要注意什么？

## ⚠️ 易错点 / 高阶拓展
不要只背“都有宏任务和微任务”。真正差异在调度阶段、IO 模型和渲染参与方式。

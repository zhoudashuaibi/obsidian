---
title: setImmediate vs setTimeout vs process.nextTick
tags:
  - Node.js
  - 8.2 事件循环
  - 面试
status: active
date: 2026-03-18
---

# setImmediate vs setTimeout vs process.nextTick

## 📌 核心概念
三者都能把逻辑延后，但执行优先级不同。process.nextTick 会在当前阶段结束后立刻清空；setTimeout 属于 timers 阶段；setImmediate 属于 check 阶段。

## 💻 代码示例
```js
setTimeout(() => console.log('timeout'))
setImmediate(() => console.log('immediate'))
process.nextTick(() => console.log('nextTick'))
```

## 🛠 实战场景
面试高频就是让你预测输出顺序，再顺带考察你是否理解 Node 与浏览器微任务差异。

## 🎯 面试怎么问
- 这三者的执行顺序一定固定吗？
- 为什么 nextTick 不能滥用？
- IO 回调里 setImmediate 为什么常比 setTimeout 更早？

## ⚠️ 易错点 / 高阶拓展
process.nextTick 队列过长会饿死事件循环，让 IO 没机会进入后续阶段。

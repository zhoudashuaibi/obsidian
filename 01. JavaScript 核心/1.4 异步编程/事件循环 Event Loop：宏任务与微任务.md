---
title: 事件循环 Event Loop：宏任务与微任务
tags:
  - JavaScript
  - 异步编程
  - 面试
status: active
date: 2026-03-18
---

# 事件循环 Event Loop：宏任务与微任务

## 📌 核心概念
JavaScript 主线程一次只执行一个任务。同步代码跑完后，事件循环会从任务队列中取任务继续执行；每轮宏任务结束后，会先清空微任务队列，再决定是否进行渲染。

## 💻 代码示例
```js
console.log(1);

setTimeout(() => console.log(2), 0);
Promise.resolve().then(() => console.log(3));
queueMicrotask(() => console.log(4));

console.log(5);
// 输出：1 5 3 4 2
```

## 🛠 实战场景
分析页面卡顿、接口回调顺序、Vue/React 更新批处理时，都绕不开事件循环。很多“为什么先打印这个”的题，本质都在考任务调度。

## 🎯 面试怎么问
- 宏任务和微任务分别有哪些？
- 为什么 Promise 回调比 setTimeout 更早执行？
- 浏览器渲染发生在事件循环的哪个阶段？

## ⚠️ 易错点 / 高阶拓展
浏览器和 Node.js 的事件循环细节不同；面试要先答通用模型，再补充运行时差异。注意“微任务过多也会阻塞渲染”。


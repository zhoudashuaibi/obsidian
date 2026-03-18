---
title: Promise：链式调用、错误处理、静态方法
tags:
  - JavaScript
  - 异步编程
  - 面试
status: active
date: 2026-03-18
---

# Promise：链式调用、错误处理、静态方法

## 📌 核心概念
Promise 用统一状态机抽象异步结果：`pending`、`fulfilled`、`rejected`。链式调用依赖 `then` 返回新 Promise；错误会沿链冒泡到最近的 `catch`；常见静态方法用于并发编排。

## 💻 代码示例
```js
fetch('/api/user')
  .then((res) => res.json())
  .then((data) => ({ ...data, loaded: true }))
  .catch((err) => {
    console.error('request failed', err);
    return { loaded: false };
  })
  .finally(() => {
    console.log('done');
  });
```

## 🛠 实战场景
前端请求层、弹窗确认流、资源预加载都经常组合 `Promise.all`、`allSettled`、`race`、`finally` 实现更清晰的异步控制。

## 🎯 面试怎么问
- Promise 为什么能链式调用？
- `then` 里抛错会发生什么？
- `all`、`race`、`allSettled` 分别适合什么场景？

## ⚠️ 易错点 / 高阶拓展
不要把 Promise 当成“立即执行的异步函数”，它的执行器是同步执行的。手写题通常会考状态不可逆、回调队列、值穿透和 thenable 解析。


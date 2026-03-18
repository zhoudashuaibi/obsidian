---
title: async 与 await 原理与错误处理
tags:
  - JavaScript
  - 异步编程
  - 面试
status: active
date: 2026-03-18
---

# async 与 await 原理与错误处理

## 📌 核心概念
`async/await` 是基于 Promise 的语法糖，让异步流程写起来像同步代码。`await` 会暂停当前 async 函数后续逻辑，把控制权交还调用栈，待 Promise 完成后再恢复执行。

## 💻 代码示例
```js
async function loadUser() {
  try {
    const res = await fetch('/api/user');
    if (!res.ok) throw new Error('network error');
    return await res.json();
  } catch (error) {
    console.error(error);
    return null;
  }
}
```

## 🛠 实战场景
串行依赖请求、表单提交、初始化流程特别适合 `async/await`。代码更平铺，但并发任务仍需要 `Promise.all` 等手段组合。

## 🎯 面试怎么问
- `async/await` 和 Promise 的关系是什么？
- `await` 后面的表达式不是 Promise 会怎样？
- 如何优雅处理多个异步任务的错误？

## ⚠️ 易错点 / 高阶拓展
不要把多个无依赖请求都顺手写成串行 `await`；这样会白白增加总耗时。高频追问是 Babel 如何把 async 编译成 generator。


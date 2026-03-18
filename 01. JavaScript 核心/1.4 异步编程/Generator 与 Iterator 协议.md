---
title: Generator 与 Iterator 协议
tags:
  - JavaScript
  - 异步编程
  - 面试
status: active
date: 2026-03-18
---

# Generator 与 Iterator 协议

## 📌 核心概念
Iterator 协议规定对象提供 `next()` 并返回 `{ value, done }`；Generator 函数通过 `function*` 和 `yield` 快速生成迭代器。它既能按需产出值，也能承载可暂停的流程控制。

## 💻 代码示例
```js
function* createIds() {
  yield 1;
  yield 2;
  yield 3;
}

const it = createIds();
console.log(it.next()); // { value: 1, done: false }
console.log(it.next()); // { value: 2, done: false }
console.log(it.next()); // { value: 3, done: false }
```

## 🛠 实战场景
自定义遍历、惰性计算、早期 redux-saga 异步流程都大量使用 Generator。它非常适合解释“暂停 / 恢复执行”这一抽象。

## 🎯 面试怎么问
- 什么是 Iterator 协议？
- Generator 和普通函数最大区别是什么？
- `yield`、`next`、`return`、`throw` 如何配合？

## ⚠️ 易错点 / 高阶拓展
很多人只会写 `for...of`，却不知道底层依赖迭代器协议。高阶题会追问 `yield*`、可迭代对象、以及 async generator。


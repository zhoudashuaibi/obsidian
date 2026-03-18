---
title: call、apply、bind 手写实现
tags:
  - JavaScript
  - 执行上下文
  - 面试
status: active
date: 2026-03-18
---

# call、apply、bind 手写实现

## 📌 核心概念
`call`、`apply`、`bind` 都用于显式绑定 `this`。前两者会立即执行，区别在于参数组织形式；`bind` 返回新函数，可延迟调用，并支持预置参数。

## 💻 代码示例
```js
Function.prototype.myCall = function (context, ...args) {
  const target = context ?? globalThis;
  const key = Symbol('fn');
  target[key] = this;
  const result = target[key](...args);
  delete target[key];
  return result;
};
```

## 🛠 实战场景
封装通用函数、修复回调中的 this 丢失、函数柯里化预置参数时都可能用到。手写题常拿它考察你对 `this` 和函数对象的理解深度。

## 🎯 面试怎么问
- `call`、`apply`、`bind` 的区别是什么？
- 手写时为什么常用 `Symbol` 临时挂载函数？
- `bind` 返回的函数能否作为构造函数？

## ⚠️ 易错点 / 高阶拓展
实现时别漏掉 `null/undefined` 默认指向、原始值装箱、返回值透传、`bind` 的构造调用兼容等细节。


---
title: 类型判断：typeof、instanceof、Object.prototype.toString
tags:
  - JavaScript
  - 类型系统
  - 面试
status: active
date: 2026-03-18
---

# 类型判断：typeof、instanceof、Object.prototype.toString

## 📌 核心概念
`typeof` 适合判断原始类型和函数，但 `null` 会返回 `object`；`instanceof` 判断原型链上是否出现某构造函数的 `prototype`；`Object.prototype.toString.call` 最稳定，适合跨 iframe、数组、日期、正则等精确判断。

## 💻 代码示例
```js
console.log(typeof 'hi'); // string
console.log(typeof null); // object，历史遗留问题

console.log([] instanceof Array); // true
console.log(new Date() instanceof Date); // true

const getTag = (value) => Object.prototype.toString.call(value);
console.log(getTag([])); // [object Array]
console.log(getTag(null)); // [object Null]
```

## 🛠 实战场景
封装通用工具库时，通常会组合使用三种方式：先用 `typeof` 快速分流，再用 `toString` 精确判断对象细分类型。

## 🎯 面试怎么问
- `typeof null` 为什么是 `object`？
- `instanceof` 的底层原理是什么？
- 如何实现一个可靠的 `isArray` / `isPlainObject`？

## ⚠️ 易错点 / 高阶拓展
`instanceof` 会受原型链和跨运行时环境影响；手写时常考 `Symbol.hasInstance`、原型链遍历，以及 `Array.isArray` 为什么比 `instanceof Array` 更稳。


---
title: Symbol 与 BigInt 使用场景
tags:
  - JavaScript
  - 类型系统
  - 面试
status: active
date: 2026-03-18
---

# Symbol 与 BigInt 使用场景

## 📌 核心概念
`Symbol` 用于创建唯一值，适合做对象私有键、常量枚举、协议扩展；`BigInt` 用于表示超出 `Number.MAX_SAFE_INTEGER` 的整数，避免精度丢失。它们都是 ES6+ 后补足语言能力的重要原始类型。

## 💻 代码示例
```js
const id = Symbol('id');
const user = {
  name: 'Tom',
  [id]: 1001,
};

console.log(user[id]); // 1001

const big = 9007199254740993n;
console.log(big + 2n); // 9007199254740995n
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
```

## 🛠 实战场景
前者常用于防止对象字段冲突、实现迭代器等内置协议；后者适用于大整数 ID、金融分账流水号、加密算法中的整数运算。

## 🎯 面试怎么问
- `Symbol` 解决了什么问题？
- `BigInt` 和 `Number` 为什么不能直接混算？
- `Symbol.iterator`、`Symbol.toStringTag` 有什么作用？

## ⚠️ 易错点 / 高阶拓展
`Symbol` 不是“真正私有”，仍可通过 `Object.getOwnPropertySymbols` 取到；`BigInt` 不能和 `Math` 大多数方法直接混用，也不能参与 `JSON.stringify` 默认序列化。


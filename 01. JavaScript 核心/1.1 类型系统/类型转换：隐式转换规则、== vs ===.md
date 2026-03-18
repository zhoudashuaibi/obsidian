---
title: 类型转换：隐式转换规则、== vs ===
tags:
  - JavaScript
  - 类型系统
  - 面试
status: active
date: 2026-03-18
---

# 类型转换：隐式转换规则、== vs ===

## 📌 核心概念
JavaScript 在运算、比较、模板拼接时会触发隐式转换，常见规则包括 `ToPrimitive`、`ToNumber`、`ToString`。`===` 不做类型转换，`==` 会按抽象相等规则转换两边后再比较，因此容易出现反直觉结果。

## 💻 代码示例
```js
console.log('5' + 1); // '51'
console.log('5' - 1); // 4
console.log(Boolean([])); // true

console.log(0 == false); // true
console.log('' == false); // true
console.log(null == undefined); // true
console.log(0 === false); // false
```

## 🛠 实战场景
接口字段常来自 URL、表单、localStorage，很多线上 bug 都是字符串数字混用导致。例如价格比较、分页参数、权限开关判断。

## 🎯 面试怎么问
- `==` 和 `===` 的区别是什么？
- `[] == ![]` 为什么是 `true`？
- 对象参与运算时会经历哪些转换步骤？

## ⚠️ 易错点 / 高阶拓展
建议业务代码默认使用 `===`；只有明确利用 `null == undefined` 这类规则时才使用 `==`。高阶追问会考 `valueOf`、`toString`、`Symbol.toPrimitive` 的优先级。


---
title: 原始类型 vs 引用类型
tags:
  - JavaScript
  - 类型系统
  - 面试
status: active
date: 2026-03-18
---

# 原始类型 vs 引用类型

## 📌 核心概念
JavaScript 的原始类型包含 `string`、`number`、`boolean`、`null`、`undefined`、`symbol`、`bigint`，它们通常按值存储；对象、数组、函数属于引用类型，变量里保存的是地址引用。面试常考拷贝、参数传递、比较运算的行为差异。

## 💻 代码示例
```js
const a = 1;
const b = a;

const user = { name: 'Tom' };
const copy = user;

copy.name = 'Jerry';

console.log(a === b); // true，值相同
console.log(user === copy); // true，指向同一地址
console.log(user.name); // Jerry
```

## 🛠 实战场景
表单草稿、配置对象、React/Vue 状态更新都依赖这个差异。比如你以为做了“复制”，实际只是共享了同一个对象引用，随后修改子属性会污染原状态。

## 🎯 面试怎么问
- 原始类型和引用类型在内存里分别怎么存？
- 函数传参到底是传值还是传引用？
- `const` 声明对象后为什么还能改属性？

## ⚠️ 易错点 / 高阶拓展
对象赋值、数组展开、`Object.assign` 都只是浅拷贝；嵌套对象仍然共享引用。追问通常会延伸到 [[前段知识库/深拷贝实现|深拷贝实现]] 与不可变数据更新。


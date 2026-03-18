---
title: 变量提升 vs 函数提升
tags:
  - JavaScript
  - 作用域
  - 面试
status: active
date: 2026-03-18
---

# 变量提升 vs 函数提升

## 📌 核心概念
编译阶段会先处理声明，再执行代码。`function` 声明会连同函数体一起提升；`var` 只提升声明，赋值保留在原位置，因此访问时可能得到 `undefined`。

## 💻 代码示例
```js
console.log(foo); // undefined
var foo = 1;

bar(); // 'ok'
function bar() {
  console.log('ok');
}

// baz(); // TypeError
var baz = function () {};
```

## 🛠 实战场景
老项目里经常能看到 `var` 和函数声明混用，不理解提升就很难解释初始化顺序、覆盖行为和“为什么能先调用后声明”。

## 🎯 面试怎么问
- 什么是变量提升？
- 函数声明和函数表达式的提升差异是什么？
- 为什么 `var` 提前访问不报错而 `let` 会报错？

## ⚠️ 易错点 / 高阶拓展
提升不是“代码真的移动了”，而是创建执行上下文时先登记声明。面试追问常结合 AO/VO、TDZ、块级作用域一起考。


---
title: let 与 const 暂时性死区 TDZ
tags:
  - JavaScript
  - 作用域
  - 面试
status: active
date: 2026-03-18
---

# let 与 const 暂时性死区 TDZ

## 📌 核心概念
`let`、`const` 具有块级作用域，在声明前虽然已经被登记，但不能访问，这段区域叫暂时性死区（TDZ）。`const` 还要求声明时必须初始化，且绑定不能被重新赋值。

## 💻 代码示例
```js
{
  // console.log(a); // ReferenceError
  let a = 1;

  const config = { debug: true };
  config.debug = false; // 可以改属性
  // config = {}; // TypeError
}

for (let i = 0; i < 3; i += 1) {
  setTimeout(() => console.log(i), 0);
}
```

## 🛠 实战场景
循环绑定、异步回调、条件分支中的局部变量都适合使用 `let`；配置常量、不可重新绑定的引用适合 `const`。

## 🎯 面试怎么问
- 什么是暂时性死区？
- `let`、`const`、`var` 的核心区别有哪些？
- `const` 定义的对象为什么还能改属性？

## ⚠️ 易错点 / 高阶拓展
TDZ 的价值在于减少“声明前使用”的隐式 bug。注意 `const` 只保证绑定不变，不保证对象深层不可变。


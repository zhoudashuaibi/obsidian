---
title: 箭头函数与普通函数 this 差异
tags:
  - JavaScript
  - 执行上下文
  - 面试
status: active
date: 2026-03-18
---

# 箭头函数与普通函数 this 差异

## 📌 核心概念
箭头函数没有自己的 `this`、`arguments`、`prototype`，它会词法捕获外层最近一层非箭头函数的 `this`。普通函数的 `this` 由调用方式决定，因此两者适用场景完全不同。

## 💻 代码示例
```js
const obj = {
  name: 'Tom',
  normal() {
    setTimeout(function () {
      console.log(this.name); // undefined 或 window.name
    }, 0);

    setTimeout(() => {
      console.log(this.name); // Tom
    }, 0);
  },
};

obj.normal();
```

## 🛠 实战场景
React 类组件旧代码、DOM 事件、对象方法、数组回调里经常需要根据是否要继承外层 this 来选择函数形式。

## 🎯 面试怎么问
- 箭头函数为什么不能当构造函数？
- 箭头函数中的 this 为什么不能被 call/apply 改变？
- 什么场景不该使用箭头函数？

## ⚠️ 易错点 / 高阶拓展
对象方法若直接写成箭头函数，`this` 往往不是对象本身。需要动态 this 的场景，如事件监听器、原型方法，不适合箭头函数。


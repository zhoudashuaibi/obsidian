---
title: this 的四种绑定规则
tags:
  - JavaScript
  - 执行上下文
  - 面试
status: active
date: 2026-03-18
---

# this 的四种绑定规则

## 📌 核心概念
`this` 的指向不是函数定义时确定，而是调用时决定。高频总结是四种绑定规则：默认绑定、隐式绑定、显式绑定、`new` 绑定；若同时出现，以优先级更高的规则为准。

## 💻 代码示例
```js
function show() {
  console.log(this.name);
}

const obj = { name: 'Tom', show };
obj.show(); // 隐式绑定
show.call({ name: 'Jerry' }); // 显式绑定
const ins = new show(); // new 绑定，this 指向新对象
```

## 🛠 实战场景
面试里几乎必考，业务里最常出现在事件回调、类方法解构调用、定时器、对象方法传参后丢失上下文。

## 🎯 面试怎么问
- `this` 到底是谁决定的？
- 四种绑定规则的优先级是什么？
- `bind` 后再 `new` 会发生什么？

## ⚠️ 易错点 / 高阶拓展
不要说“this 指向函数自己”或“指向定义它的对象”，这都是常见误区。箭头函数不适用这四种规则，是另一套词法绑定。


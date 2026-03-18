---
title: prototype vs __proto__ vs Object.getPrototypeOf
tags:
  - JavaScript
  - 原型继承
  - 面试
status: active
date: 2026-03-18
---

# prototype vs __proto__ vs Object.getPrototypeOf

## 📌 核心概念
`prototype` 是函数作为构造器时给实例共享的原型对象；`__proto__` 是大多数对象实例上的访问器属性，指向其内部原型；`Object.getPrototypeOf` 是标准方式，用于读取对象原型。

## 💻 代码示例
```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayHi = function () {
  console.log(this.name);
};

const p = new Person('Tom');
console.log(p.__proto__ === Person.prototype); // true
console.log(Object.getPrototypeOf(p) === Person.prototype); // true
```

## 🛠 实战场景
团队 code review 中常会看到直接操作 `__proto__` 的代码，应该优先改为 `Object.create`、`Object.setPrototypeOf` 或 class 语法，表达更清晰也更规范。

## 🎯 面试怎么问
- 三者分别是什么？
- `new` 时实例和构造函数原型是如何关联的？
- 为什么不推荐直接使用 `__proto__`？

## ⚠️ 易错点 / 高阶拓展
`prototype` 只有函数对象才有；普通对象没有这个属性。面试高频追问是 `new` 的四个步骤，以及 `constructor` 属性是否可靠。


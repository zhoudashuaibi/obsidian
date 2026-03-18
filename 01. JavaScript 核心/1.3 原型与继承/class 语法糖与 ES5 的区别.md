---
title: class 语法糖与 ES5 的区别
tags:
  - JavaScript
  - 原型继承
  - 面试
status: active
date: 2026-03-18
---

# class 语法糖与 ES5 的区别

## 📌 核心概念
`class` 本质仍然基于原型和构造函数，只是提供了更接近传统面向对象语言的写法。它支持 `extends`、`super`、静态方法、字段语法，但底层依旧是原型链。

## 💻 代码示例
```js
class Person {
  constructor(name) {
    this.name = name;
  }

  sayHi() {
    return `hi ${this.name}`;
  }

  static create(name) {
    return new Person(name);
  }
}
```

## 🛠 实战场景
团队协作中 class 写法可读性更好，尤其适合 SDK、数据模型、错误类型封装。但调试原型链问题时，还是要回到底层模型理解。

## 🎯 面试怎么问
- 为什么说 class 只是语法糖？
- class 方法为什么默认不可枚举？
- `extends` 和 `super` 底层做了什么？

## ⚠️ 易错点 / 高阶拓展
class 存在 TDZ，不能像函数声明那样随意提前使用。还要注意 class 字段、私有字段 `#x`、装饰器等新语法属于更现代的扩展能力。


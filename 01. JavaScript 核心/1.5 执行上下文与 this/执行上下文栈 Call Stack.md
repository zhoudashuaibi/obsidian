---
title: 执行上下文栈 Call Stack
tags:
  - JavaScript
  - 执行上下文
  - 面试
status: active
date: 2026-03-18
---

# 执行上下文栈 Call Stack

## 📌 核心概念
执行上下文描述代码运行时所需的环境信息，包含变量对象、作用域链、this 等。JavaScript 通过调用栈管理上下文：全局上下文先进栈，函数调用时创建新上下文压栈，执行完再弹出。

## 💻 代码示例
```js
function a() {
  console.log('a start');
  b();
  console.log('a end');
}

function b() {
  console.log('in b');
}

a();
```

## 🛠 实战场景
排查递归溢出、理解同步阻塞、解释为什么某段代码“先入后出”执行时，都需要从调用栈角度去看。

## 🎯 面试怎么问
- 什么是执行上下文？
- 调用栈的入栈和出栈顺序是什么？
- 为什么会出现 `Maximum call stack size exceeded`？

## ⚠️ 易错点 / 高阶拓展
作用域是静态的，执行上下文是动态创建的。面试中经常把两者放在一起考，回答时要主动拆开。


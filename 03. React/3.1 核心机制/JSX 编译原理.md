---
title: JSX 编译原理
tags:
  - React
  - 核心机制
  - 面试
status: active
date: 2026-03-18
---

# JSX 编译原理

## 📌 核心概念
JSX 不是浏览器原生语法，而是语法糖。构建阶段 Babel 或 SWC 会把 JSX 编译成 `React.createElement` 或新的 JSX Runtime 调用，再交给 React 生成虚拟 DOM 描述对象。

## 💻 代码示例
```jsx
function App() {
  return <h1 className="title">Hello</h1>;
}

// 编译后大致类似
function App() {
  return jsx('h1', {
    className: 'title',
    children: 'Hello',
  });
}
```

## 🛠 实战场景
理解 JSX 编译后长什么样，有助于解释为什么组件名必须大写、为什么不能直接返回多个兄弟节点，以及 key/props 是怎么传递的。

## 🎯 面试怎么问
- JSX 本质是什么？
- JSX 为什么需要编译？
- React 17 之后新的 JSX Runtime 改变了什么？

## ⚠️ 易错点 / 高阶拓展
不要把 JSX 当模板引擎，它本质是 JavaScript 表达式。高阶追问常会延伸到 Babel 插件、AST 转换和 `jsxDEV` 调试信息。


---
title: Tree Shaking 原理与条件
tags:
  - 前端工程化
  - 模块化
  - 面试
status: active
date: 2026-03-18
---

# Tree Shaking 原理与条件

## 📌 核心概念
Tree Shaking 是构建阶段删除未使用代码的优化能力，核心依赖 ESM 的静态依赖分析。只有导入导出关系在编译期可确定，打包器才能判断哪些导出真正被用到。

## 💻 代码示例
```js
// math.js
export const add = (a, b) => a + b;
export const sub = (a, b) => a - b;

// main.js
import { add } from './math.js';
console.log(add(1, 2));
```

## 🛠 实战场景
组件库、工具函数库打包时，Tree Shaking 能减少无用代码进入最终产物，是性能优化和包体控制的重要基础。

## 🎯 面试怎么问
- Tree Shaking 为什么依赖 ESM？
- 什么情况下 Tree Shaking 会失效？
- `sideEffects` 字段有什么作用？

## ⚠️ 易错点 / 高阶拓展
不要把它理解成“打包器自动变魔术”。只要存在副作用、不透明导入或 CommonJS 混用，优化空间就会受限。


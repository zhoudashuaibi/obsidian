---
title: Babel 编译流程：parse、transform、generate
tags:
  - 前端工程化
  - Babel
  - 面试
status: active
date: 2026-03-18
---

# Babel 编译流程：parse、transform、generate

## 📌 核心概念
Babel 的工作流程通常分三步：先把源码 parse 成 AST，再通过插件在 transform 阶段修改 AST，最后 generate 输出新代码。这是一套通用的代码转换流水线。

## 💻 代码示例
```js
const code = 'const sum = (a, b) => a + b';
// parse -> AST
// transform -> 修改节点
// generate -> 输出 ES5/其他格式代码
```

## 🛠 实战场景
理解 Babel 流程后，很多“语法降级”“自动注入”“按需引入”类问题都会更容易解释。

## 🎯 面试怎么问
- Babel 为什么要先转成 AST？
- transform 阶段通常做什么？
- generate 输出的只是字符串代码吗？

## ⚠️ 易错点 / 高阶拓展
Babel 不等于 polyfill，它主要处理语法与代码转换。语言能力补丁通常还要配合 core-js 等方案。


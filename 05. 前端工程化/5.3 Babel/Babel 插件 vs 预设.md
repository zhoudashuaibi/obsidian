---
title: Babel 插件 vs 预设
tags:
  - 前端工程化
  - Babel
  - 面试
status: active
date: 2026-03-18
---

# Babel 插件 vs 预设

## 📌 核心概念
插件是单一转换能力单元，预设则是一组插件集合。项目里常通过 preset 一次启用一类能力，比如环境降级、React JSX、TypeScript 语法解析。

## 💻 代码示例
```js
module.exports = {
  presets: ['@babel/preset-env'],
  plugins: ['@babel/plugin-transform-runtime'],
};
```

## 🛠 实战场景
实际配置 Babel 时，很少只用单插件。理解 preset 和 plugin 的层级关系，能帮助你读懂构建配置和排查冲突。

## 🎯 面试怎么问
- preset 和 plugin 的区别是什么？
- `preset-env` 为什么很常用？
- 插件执行顺序会影响结果吗？

## ⚠️ 易错点 / 高阶拓展
不要把 preset 理解成“更高级插件”，它本质上只是插件组合与封装。


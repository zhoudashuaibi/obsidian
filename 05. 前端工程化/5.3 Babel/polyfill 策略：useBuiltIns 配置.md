---
title: polyfill 策略：useBuiltIns 配置
tags:
  - 前端工程化
  - Babel
  - 面试
status: active
date: 2026-03-18
---

# polyfill 策略：useBuiltIns 配置

## 📌 核心概念
`useBuiltIns` 用于控制 Babel 如何按需注入 `core-js` polyfill。它解决的是“目标环境缺少新 API”问题，而不是语法转换本身。常见值有 `usage`、`entry`、`false`。

## 💻 代码示例
```js
module.exports = {
  presets: [[
    '@babel/preset-env',
    {
      useBuiltIns: 'usage',
      corejs: 3,
    },
  ]],
};
```

## 🛠 实战场景
要兼容旧浏览器时，polyfill 策略直接影响包体积、运行正确性和是否污染全局环境。

## 🎯 面试怎么问
- `useBuiltIns: usage` 和 `entry` 有什么区别？
- 为什么 Babel 不能自动解决所有兼容问题？
- `core-js` 在这里扮演什么角色？

## ⚠️ 易错点 / 高阶拓展
polyfill 可能污染全局对象，库开发和应用开发的策略也不同。回答时最好区分“语法降级”和“API 补丁”。


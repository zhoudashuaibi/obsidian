---
title: package.json exports 与 sideEffects 字段
tags:
  - 前端工程化
  - 包管理
  - 面试
status: active
date: 2026-03-18
---

# package.json exports 与 sideEffects 字段

## 📌 核心概念
`exports` 用于声明包的对外入口边界，限制可被导入的路径并支持条件导出；`sideEffects` 用于告诉打包器哪些文件有副作用，帮助 Tree Shaking 更准确地删除无用代码。

## 💻 代码示例
```js
{
  "exports": {
    ".": "./dist/index.js",
    "./style.css": "./dist/style.css"
  },
  "sideEffects": ["./dist/style.css"]
}
```

## 🛠 实战场景
组件库和工具库发布时，这两个字段会直接影响使用方式、构建优化效果和兼容性。

## 🎯 面试怎么问
- `exports` 解决了什么问题？
- `sideEffects: false` 能随便写吗？
- 为什么样式文件常需要保留副作用声明？

## ⚠️ 易错点 / 高阶拓展
字段配置不当会导致用户无法导入子路径，或者构建时把真正需要执行的样式/初始化代码误删。


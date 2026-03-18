---
title: Prettier 与 ESLint 协作
tags:
  - 前端工程化
  - 代码质量
  - 面试
status: active
date: 2026-03-18
---

# Prettier 与 ESLint 协作

## 📌 核心概念
Prettier 负责“怎么排版更统一”，ESLint 负责“代码是否合理、是否违规”。工程实践里通常让 Prettier 处理格式，让 ESLint 处理语义和质量，避免职责重叠。

## 💻 代码示例
```js
{
  "scripts": {
    "lint": "eslint .",
    "format": "prettier --write ."
  }
}
```

## 🛠 实战场景
多人协作项目里，统一格式化工具能减少无意义 diff，而 ESLint 则帮助守住可读性和正确性底线。

## 🎯 面试怎么问
- Prettier 和 ESLint 分别解决什么问题？
- 为什么常要禁用部分格式类 ESLint 规则？
- 保存时自动修复通常怎么配？

## ⚠️ 易错点 / 高阶拓展
不要强行让 ESLint 管所有格式细节，维护成本会很高。工具协作的关键是职责清晰。


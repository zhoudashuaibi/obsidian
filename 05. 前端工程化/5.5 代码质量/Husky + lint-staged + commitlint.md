---
title: Husky + lint-staged + commitlint
tags:
  - 前端工程化
  - 代码质量
  - 面试
status: active
date: 2026-03-18
---

# Husky + lint-staged + commitlint

## 📌 核心概念
这套组合常用于把代码质量检查前移到提交阶段：Husky 管 Git Hooks，lint-staged 只校验暂存文件，commitlint 约束提交信息格式。它能减少低质量代码进入主分支。

## 💻 代码示例
```js
{
  "lint-staged": {
    "*.{js,ts,tsx}": ["eslint --fix", "prettier --write"]
  }
}
```

## 🛠 实战场景
团队协作中，这种“提交即校验”的机制能明显降低 CI 失败率和 review 噪音。

## 🎯 面试怎么问
- 三者分别做什么？
- 为什么 lint-staged 只处理暂存文件？
- commitlint 的价值是什么？

## ⚠️ 易错点 / 高阶拓展
Hook 设计不能太重，否则会拖慢开发体验。合理策略是本地做快速检查，重检查交给 CI。


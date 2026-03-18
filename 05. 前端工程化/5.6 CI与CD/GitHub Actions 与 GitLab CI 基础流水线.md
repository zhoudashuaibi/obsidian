---
title: GitHub Actions 与 GitLab CI 基础流水线
tags:
  - 前端工程化
  - CI/CD
  - 面试
status: active
date: 2026-03-18
---

# GitHub Actions 与 GitLab CI 基础流水线

## 📌 核心概念
CI/CD 的核心是把构建、测试、发布流程自动化。GitHub Actions 与 GitLab CI 都是用 YAML 描述流水线任务，根据事件触发执行，从而减少人工步骤与环境差异。

## 💻 代码示例
```js
name: ci
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci
      - run: npm test
```

## 🛠 实战场景
前端项目最常见的流水线就是安装依赖、执行 lint/test/build，然后按分支或 tag 决定是否部署。

## 🎯 面试怎么问
- CI 和 CD 分别是什么意思？
- 前端基础流水线一般包含哪些步骤？
- GitHub Actions 和 GitLab CI 的配置思路有什么共性？

## ⚠️ 易错点 / 高阶拓展
面试不一定要求背具体语法，但要能说明“触发条件—任务编排—环境执行—产物与部署”这条主线。


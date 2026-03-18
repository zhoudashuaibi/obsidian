---
title: Suspense：数据获取集成
tags:
  - React
  - 并发特性
  - 面试
status: active
date: 2026-03-18
---

# Suspense：数据获取集成

## 📌 核心概念
Suspense 最早用于代码分割，后续逐渐扩展到数据获取协作。它的核心是：组件在“还没准备好”时抛出 Promise，由边界显示 fallback，待资源就绪后再继续渲染。

## 💻 代码示例
```jsx
<Suspense fallback={<div>loading...</div>}>
  <Profile />
</Suspense>
```

## 🛠 实战场景
懒加载页面、分块渲染、流式服务端渲染都能和 Suspense 配合，提升加载阶段的体验组织方式。

## 🎯 面试怎么问
- Suspense 的工作原理是什么？
- 它和传统 `loading` 状态写法有什么区别？
- Suspense 现在适合直接做所有数据请求吗？

## ⚠️ 易错点 / 高阶拓展
要区分“React 原生能力”和“数据层是否完整集成”。不是所有项目都应该贸然切到 Suspense 数据流。


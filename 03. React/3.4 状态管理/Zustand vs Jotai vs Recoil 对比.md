---
title: Zustand vs Jotai vs Recoil 对比
tags:
  - React
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# Zustand vs Jotai vs Recoil 对比

## 📌 核心概念
这三者都在尝试改善 React 状态管理体验，但切入点不同：Zustand 更像轻量 store；Jotai 基于原子状态组合；Recoil 也是原子化思路，并强调派生状态和依赖图。

## 💻 代码示例
```jsx
// Zustand 示例
const useStore = create((set) => ({
  count: 0,
  inc: () => set((state) => ({ count: state.count + 1 })),
}));
```

## 🛠 实战场景
选择状态库时，团队通常会从学习成本、更新粒度、调试体验、SSR 支持、生态成熟度来比较，而不是只看 API 写法是否爽。

## 🎯 面试怎么问
- 这三种状态库的设计思路分别是什么？
- 哪个更适合中小型 React 项目？
- 原子化状态有什么优势和成本？

## ⚠️ 易错点 / 高阶拓展
Recoil 官方推进节奏曾让社区顾虑较多，实际选型要看维护活跃度和团队接受度。不要只说“哪个最火”，要结合场景。


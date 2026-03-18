---
title: useMemo 与 useCallback：正确使用时机
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useMemo 与 useCallback：正确使用时机

## 📌 核心概念
`useMemo` 用于缓存计算结果，`useCallback` 用于缓存函数引用。它们的价值不在于“默认更快”，而在于避免昂贵计算重复执行，或减少子组件因引用变化导致的无意义渲染。

## 💻 代码示例
```jsx
const filtered = useMemo(() => {
  return list.filter((item) => item.visible);
}, [list]);

const handleClick = useCallback((id) => {
  onSelect(id);
}, [onSelect]);
```

## 🛠 实战场景
大列表筛选、图表数据转换、配合 `React.memo` 稳定 props 引用，是它们最常见的使用场景。

## 🎯 面试怎么问
- `useMemo` 和 `useCallback` 的区别是什么？
- 什么时候不该使用它们？
- 为什么滥用缓存反而可能更慢？

## ⚠️ 易错点 / 高阶拓展
缓存本身也有成本：依赖比较、内存占用、心智负担。没有明确性能问题或引用稳定需求时，别机械地全项目套一层。


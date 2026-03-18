---
title: useRef：DOM 引用 vs 存储可变值
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useRef：DOM 引用 vs 存储可变值

## 📌 核心概念
`useRef` 返回一个在整个组件生命周期内稳定存在的对象，常见用途有两类：获取 DOM/组件实例引用，以及在不触发重渲染的情况下保存可变值。

## 💻 代码示例
```jsx
function SearchInput() {
  const inputRef = useRef(null);
  const renderCountRef = useRef(0);

  renderCountRef.current += 1;

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current?.focus()}>focus</button>
    </div>
  );
}
```

## 🛠 实战场景
输入框聚焦、滚动容器控制、缓存定时器 id、保存上一次值，都是 `useRef` 的典型场景。

## 🎯 面试怎么问
- `useRef` 和 `useState` 的区别是什么？
- 改 `ref.current` 为什么不触发渲染？
- `forwardRef` 出现的背景是什么？

## ⚠️ 易错点 / 高阶拓展
不要用 ref 逃避状态设计。凡是需要驱动 UI 的数据，仍应使用 state。ref 更适合“跨渲染保存但不参与渲染”的值。


---
title: useState：批量更新与函数式更新
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useState：批量更新与函数式更新

## 📌 核心概念
`useState` 用于给函数组件声明状态。React 会对同一批次中的状态更新做批处理，减少重复渲染；当新状态依赖旧状态时，应使用函数式更新，避免闭包拿到旧值。

## 💻 代码示例
```jsx
function Counter() {
  const [count, setCount] = useState(0);

  const addTwice = () => {
    setCount((prev) => prev + 1);
    setCount((prev) => prev + 1);
  };

  return <button onClick={addTwice}>{count}</button>;
}
```

## 🛠 实战场景
计数器、表单输入、筛选条件、弹窗开关等几乎所有组件状态都离不开 `useState`。

## 🎯 面试怎么问
- `useState` 是同步还是异步？
- 为什么连续 `setState(count + 1)` 可能只加一次？
- 函数式更新适合什么场景？

## ⚠️ 易错点 / 高阶拓展
不要把批量更新简单理解成“异步”。更准确地说，它是 React 在一次更新周期内统一处理多个更新。


---
title: Context API 的局限性
tags:
  - React
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# Context API 的局限性

## 📌 核心概念
Context 适合跨层传值，但不擅长高频、细粒度更新。它缺少 selector、时间旅行调试、模块边界、复杂中间件生态，因此更像“共享通道”，不是完整状态管理方案。

## 💻 代码示例
```jsx
const AuthContext = createContext(null);

function App() {
  const [user, setUser] = useState(null);
  return <AuthContext.Provider value={{ user, setUser }}><Page /></AuthContext.Provider>;
}
```

## 🛠 实战场景
小型项目用 Context 没问题，但当共享状态越来越多、更新越来越频繁时，维护成本会明显上升。

## 🎯 面试怎么问
- Context 适合做什么，不适合做什么？
- 为什么说 Context 不是 Redux 替代品？
- Context 的性能问题来自哪里？

## ⚠️ 易错点 / 高阶拓展
回答这类题不要极端化。Context 不是不能用，而是要明确边界：低频、全局、简单共享非常合适。


---
title: useContext：性能问题与解决方案
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useContext：性能问题与解决方案

## 📌 核心概念
`useContext` 让组件跨层级读取共享数据，但只要 Provider 的 `value` 引用变化，所有消费该 context 的组件都会重新渲染。它很适合低频全局信息，不适合高频细粒度状态。

## 💻 代码示例
```jsx
const ThemeContext = createContext('light');

function App() {
  const value = useMemo(() => ({ theme: 'dark' }), []);
  return <ThemeContext.Provider value={value}><Page /></ThemeContext.Provider>;
}

function Title() {
  const { theme } = useContext(ThemeContext);
  return <h1>{theme}</h1>;
}
```

## 🛠 实战场景
主题、国际化、权限、用户信息等低频共享数据可以用 Context；高频状态更适合拆分 Context 或引入专门状态管理。

## 🎯 面试怎么问
- Context 为什么会有性能问题？
- 如何减少不必要的 Context 更新？
- Context 能完全替代 Redux 吗？

## ⚠️ 易错点 / 高阶拓展
解决思路包括拆分 Provider、稳定 value 引用、状态与 dispatch 分离，或使用 selector 型状态库。


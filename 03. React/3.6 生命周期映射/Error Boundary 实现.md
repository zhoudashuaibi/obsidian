---
title: Error Boundary 实现
tags:
  - React
  - 生命周期映射
  - 面试
status: active
date: 2026-03-18
---

# Error Boundary 实现

## 📌 核心概念
Error Boundary 用于捕获其子树在渲染、生命周期、构造阶段抛出的错误，避免整棵应用白屏。当前稳定实现仍主要依赖类组件的 `getDerivedStateFromError` 和 `componentDidCatch`。

## 💻 代码示例
```jsx
class ErrorBoundary extends React.Component {
  state = { hasError: false };

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    console.error(error, info);
  }

  render() {
    if (this.state.hasError) {
      return <div>Something went wrong</div>;
    }
    return this.props.children;
  }
}
```

## 🛠 实战场景
页面级路由边界、复杂组件区域、第三方组件包装层都适合放 Error Boundary，提高故障隔离能力。

## 🎯 面试怎么问
- Error Boundary 能捕获哪些错误？
- 为什么函数组件不能直接完全替代 Error Boundary？
- 应该把边界放在什么粒度？

## ⚠️ 易错点 / 高阶拓展
它捕不到事件回调、异步任务、服务端渲染阶段的错误，这些仍需要额外的错误处理策略。


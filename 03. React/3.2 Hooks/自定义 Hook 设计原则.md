---
title: 自定义 Hook 设计原则
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# 自定义 Hook 设计原则

## 📌 核心概念
自定义 Hook 的价值是复用“状态 + 副作用 + 交互逻辑”，而不是单纯提取几行代码。好的 Hook 应该职责单一、命名清晰、输入输出稳定，并尽量隐藏内部实现细节。

## 💻 代码示例
```jsx
function useToggle(initialValue = false) {
  const [value, setValue] = useState(initialValue);
  const open = () => setValue(true);
  const close = () => setValue(false);
  const toggle = () => setValue((prev) => !prev);
  return { value, open, close, toggle };
}
```

## 🛠 实战场景
分页查询、弹窗开关、表单字段、滚动监听、请求状态都很适合抽成自定义 Hook，提升复用性和可测试性。

## 🎯 面试怎么问
- 什么逻辑适合抽成自定义 Hook？
- 自定义 Hook 和普通工具函数的区别是什么？
- 如何设计一个好用且稳定的 Hook API？

## ⚠️ 易错点 / 高阶拓展
不要把一整个业务页面塞进单个 Hook。Hook 抽象过度后会变成“黑盒”，难以调试和复用。


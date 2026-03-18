---
title: useLayoutEffect vs useEffect
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useLayoutEffect vs useEffect

## 📌 核心概念
`useLayoutEffect` 会在 DOM 变更后、浏览器绘制前同步执行，适合需要先测量或同步修正布局的场景；`useEffect` 则在绘制后异步执行，更适合大多数副作用。

## 💻 代码示例
```jsx
function Tooltip() {
  const ref = useRef(null);

  useLayoutEffect(() => {
    const rect = ref.current.getBoundingClientRect();
    console.log(rect.width);
  }, []);

  return <div ref={ref}>tip</div>;
}
```

## 🛠 实战场景
测量元素尺寸、防止闪烁定位、同步滚动位置时常需要 `useLayoutEffect`；而请求、订阅更适合 `useEffect`。

## 🎯 面试怎么问
- 两者最大的区别是什么？
- 什么情况下必须用 `useLayoutEffect`？
- 为什么滥用 `useLayoutEffect` 会影响性能？

## ⚠️ 易错点 / 高阶拓展
如果不是必须阻塞浏览器绘制，就优先 `useEffect`。服务端渲染环境下还要注意 `useLayoutEffect` 的警告问题。


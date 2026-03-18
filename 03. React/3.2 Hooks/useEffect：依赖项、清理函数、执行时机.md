---
title: useEffect：依赖项、清理函数、执行时机
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useEffect：依赖项、清理函数、执行时机

## 📌 核心概念
`useEffect` 用于处理副作用，如请求、订阅、定时器、手动操作 DOM。它会在渲染提交后执行，依赖数组决定何时重新运行，返回的清理函数会在下次 effect 执行前或组件卸载时调用。

## 💻 代码示例
```jsx
function User({ id }) {
  const [data, setData] = useState(null);

  useEffect(() => {
    let cancelled = false;
    fetch(`/api/user/${id}`)
      .then((res) => res.json())
      .then((res) => {
        if (!cancelled) setData(res);
      });

    return () => {
      cancelled = true;
    };
  }, [id]);

  return <pre>{JSON.stringify(data)}</pre>;
}
```

## 🛠 实战场景
接口请求、窗口事件监听、埋点上报、第三方库挂载都是典型的 effect 场景。

## 🎯 面试怎么问
- `useEffect` 的执行时机是什么？
- 为什么依赖项漏写会出 bug？
- 清理函数什么时候执行？

## ⚠️ 易错点 / 高阶拓展
不要把 `useEffect` 当生命周期拼图去硬套。它更像“渲染后同步外部系统”的声明。StrictMode 下开发环境会额外执行一次帮助发现副作用问题。


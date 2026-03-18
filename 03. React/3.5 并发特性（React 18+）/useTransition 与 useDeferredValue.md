---
title: useTransition 与 useDeferredValue
tags:
  - React
  - 并发特性
  - 面试
status: active
date: 2026-03-18
---

# useTransition 与 useDeferredValue

## 📌 核心概念
`useTransition` 用于把某些更新标记为低优先级，让紧急交互先响应；`useDeferredValue` 则延后消费某个值，常用于输入实时变化但结果渲染很重的场景。

## 💻 代码示例
```jsx
function Search() {
  const [keyword, setKeyword] = useState('');
  const deferredKeyword = useDeferredValue(keyword);
  const [isPending, startTransition] = useTransition();

  const onChange = (e) => {
    const value = e.target.value;
    setKeyword(value);
    startTransition(() => {
      setQuery(value);
    });
  };
}
```

## 🛠 实战场景
搜索框输入、复杂图表筛选、超大列表过滤是它们最典型的应用场景。

## 🎯 面试怎么问
- `useTransition` 和防抖有什么区别？
- `useDeferredValue` 适合解决什么问题？
- 为什么它们不能替代真正的数据层优化？

## ⚠️ 易错点 / 高阶拓展
并发 Hook 是“调度优化”不是“计算变少”。如果计算本身过重，仍需要拆分任务、虚拟化或后端支持。


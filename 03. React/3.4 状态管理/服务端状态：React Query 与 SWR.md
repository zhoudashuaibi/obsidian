---
title: 服务端状态：React Query 与 SWR
tags:
  - React
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# 服务端状态：React Query 与 SWR

## 📌 核心概念
服务端状态和本地 UI 状态不是一回事。React Query、SWR 这类库把请求缓存、失效重取、后台刷新、并发去重、错误重试抽象出来，专门解决“远端数据同步”问题。

## 💻 代码示例
```jsx
function User() {
  const { data, isLoading } = useQuery({
    queryKey: ['user'],
    queryFn: fetchUser,
  });

  if (isLoading) return <div>loading</div>;
  return <div>{data.name}</div>;
}
```

## 🛠 实战场景
列表查询、详情缓存、切页保留旧数据、焦点返回自动刷新等场景，用服务端状态库比手写 `useEffect + useState` 稳定得多。

## 🎯 面试怎么问
- 什么是服务端状态？
- React Query 和 Redux 分别解决什么问题？
- queryKey 为什么重要？

## ⚠️ 易错点 / 高阶拓展
不要把接口数据全塞进全局状态管理。服务端状态有自己的生命周期和缓存策略，更适合交给专门工具处理。


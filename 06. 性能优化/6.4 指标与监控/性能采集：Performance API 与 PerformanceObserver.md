---
title: 性能采集：Performance API 与 PerformanceObserver
tags:
  - 性能优化
  - 指标与监控
  - 面试
status: active
date: 2026-03-18
---

# 性能采集：Performance API 与 PerformanceObserver

## 📌 核心概念
浏览器提供了 Performance API 用于读取导航、资源、标记测量等性能信息，`PerformanceObserver` 则可以订阅性能条目，实时采集 LCP、CLS、资源耗时等指标。

## 💻 代码示例
```js
const observer = new PerformanceObserver((list) => {
  for (const entry of list.getEntries()) {
    console.log(entry.name, entry.startTime);
  }
});
observer.observe({ type: 'largest-contentful-paint', buffered: true });
```

## 🛠 实战场景
前端监控 SDK、性能面板埋点、关键路径分析都依赖这些原生能力。

## 🎯 面试怎么问
- Performance API 能拿到哪些信息？
- `PerformanceObserver` 适合解决什么问题？
- 自定义打点一般怎么做？

## ⚠️ 易错点 / 高阶拓展
不是所有指标都能通过同一种 API 拿到，且浏览器兼容和采样成本都要考虑。采集只是第一步，后续还要聚合分析。


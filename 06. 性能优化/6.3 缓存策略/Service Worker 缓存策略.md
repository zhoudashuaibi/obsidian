---
title: Service Worker 缓存策略
tags:
  - 性能优化
  - 缓存策略
  - 面试
status: active
date: 2026-03-18
---

# Service Worker 缓存策略

## 📌 核心概念
Service Worker 运行在浏览器独立线程，可拦截网络请求并自定义缓存命中策略，如 Cache First、Network First、Stale While Revalidate。它是 PWA 离线和资源缓存的重要基础。

## 💻 代码示例
```js
self.addEventListener('fetch', (event) => {
  event.respondWith(caches.match(event.request).then((res) => {
    return res || fetch(event.request);
  }));
});
```

## 🛠 实战场景
离线访问、弱网优化、静态资源缓存、请求兜底页面都常通过 Service Worker 实现更强控制力。

## 🎯 面试怎么问
- Service Worker 为什么能做缓存代理？
- 常见缓存策略有哪些？
- 更新 Service Worker 要注意什么？

## ⚠️ 易错点 / 高阶拓展
它能力很强，但更新模型和缓存失效处理也更复杂。回答时最好主动提到“版本更新”和“缓存污染”风险。


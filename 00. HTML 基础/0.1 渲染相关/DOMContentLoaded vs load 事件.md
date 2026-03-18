---
title: DOMContentLoaded vs load 事件
tags:
  - HTML
  - 渲染相关
  - 面试
status: active
date: 2026-03-18
---

# DOMContentLoaded vs load 事件

## 📌 核心概念
`DOMContentLoaded` 表示 HTML 已解析完成、DOM 树可用，但图片、样式等外部资源不一定全部加载完；`load` 则表示页面及其依赖资源基本都加载完成。

## 💻 代码示例
```html
document.addEventListener('DOMContentLoaded', () => {
  console.log('DOM ready');
});

window.addEventListener('load', () => {
  console.log('all resources loaded');
});
```

## 🛠 实战场景
初始化页面交互通常等 DOMContentLoaded 即可；依赖图片尺寸、全资源完整加载的逻辑才更适合放到 load。

## 🎯 面试怎么问
- 两个事件的触发时机有什么区别？
- 为什么大多数业务初始化不需要等到 `load`？
- `defer` 脚本和 DOMContentLoaded 有什么关系？

## ⚠️ 易错点 / 高阶拓展
很多人把“页面加载完成”说得过于模糊。面试里最好明确区分“DOM 可操作”和“所有资源完成”。


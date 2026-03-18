---
title: viewport meta 配置
tags:
  - CSS
  - 响应式设计
  - 面试
status: active
date: 2026-03-18
---

# viewport meta 配置

## 📌 核心概念
`viewport` meta 用于告诉移动浏览器页面如何映射到设备宽度。最常见配置是 `width=device-width, initial-scale=1.0`，它决定页面是否按设备逻辑宽度渲染，以及初始缩放比例。

## 💻 代码示例
```css
/* HTML 中常见配置 */
/* <meta name="viewport" content="width=device-width, initial-scale=1.0"> */

.page {
  width: 100%;
  min-height: 100vh;
}
```

## 🛠 实战场景
如果不正确配置 viewport，移动端页面可能按桌面宽度缩小显示，导致文字极小、布局怪异、媒体查询不符合预期。

## 🎯 面试怎么问
- viewport meta 的作用是什么？
- 为什么移动端通常写 `width=device-width`？
- `initial-scale` 对页面展示有什么影响？

## ⚠️ 易错点 / 高阶拓展
别随意关闭用户缩放，否则会影响可访问性。面试追问时可以补充 layout viewport、visual viewport 的区别。


---
title: Open Graph 与 Twitter Card
tags:
  - HTML
  - 语义化与 SEO
  - 面试
status: active
date: 2026-03-18
---

# Open Graph 与 Twitter Card

## 📌 核心概念
Open Graph 和 Twitter Card 用于定义页面在社交平台分享时的标题、描述、封面图等信息。它们主要影响分享卡片展示，而不是传统搜索排序。

## 💻 代码示例
```html
<meta property="og:title" content="前端知识地图">
<meta property="og:description" content="系统整理前端知识体系">
<meta property="og:image" content="https://example.com/cover.jpg">
<meta name="twitter:card" content="summary_large_image">
```

## 🛠 实战场景
文章页、活动页、产品页在微信、X、Slack、Discord 等分享场景中，都依赖这些标签来控制卡片质量。

## 🎯 面试怎么问
- Open Graph 是做什么的？
- Twitter Card 和 OG 标签有什么关系？
- 为什么分享出去的卡片图有时不更新？

## ⚠️ 易错点 / 高阶拓展
社交平台通常会缓存抓取结果，修改后可能不会立即生效。真实项目里经常还要处理图片尺寸和缓存刷新问题。


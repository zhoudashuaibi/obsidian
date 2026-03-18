---
title: 定位：absolute、relative、fixed、sticky 场景
tags:
  - CSS
  - 布局
  - 面试
status: active
date: 2026-03-18
---

# 定位：absolute、relative、fixed、sticky 场景

## 📌 核心概念
定位改变元素脱离普通文档流的方式。`relative` 常作参考系；`absolute` 相对最近定位祖先定位；`fixed` 相对视口固定；`sticky` 在滚动阈值前后在相对和固定之间切换。

## 💻 代码示例
```css
.parent {
  position: relative;
}

.badge {
  position: absolute;
  top: 8px;
  right: 8px;
}

.header {
  position: sticky;
  top: 0;
}
```

## 🛠 实战场景
悬浮按钮、吸顶导航、角标、弹层、回到顶部等都依赖定位。理解参考系比背定义更重要。

## 🎯 面试怎么问
- `absolute` 相对谁定位？
- `fixed` 一定相对视口吗？
- `sticky` 为什么有时不生效？

## ⚠️ 易错点 / 高阶拓展
`sticky` 常因父容器溢出裁剪、没有设置阈值、祖先高度不够而失效。追问通常会延伸到包含块和层叠上下文。


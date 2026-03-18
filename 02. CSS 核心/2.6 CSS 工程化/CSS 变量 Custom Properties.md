---
title: CSS 变量 Custom Properties
tags:
  - CSS
  - CSS 工程化
  - 面试
status: active
date: 2026-03-18
---

# CSS 变量 Custom Properties

## 📌 核心概念
CSS 自定义属性用 `--name` 定义，通过 `var(--name)` 读取。它们天然支持层级继承和运行时动态修改，非常适合主题系统、设计 Token 和组件参数化。

## 💻 代码示例
```css
:root {
  --color-primary: #0f766e;
  --radius-md: 12px;
}

.button {
  background: var(--color-primary);
  border-radius: var(--radius-md);
}
```

## 🛠 实战场景
亮暗主题、品牌换肤、统一间距字号体系都非常适合用 CSS 变量承载，能显著提升样式系统可维护性。

## 🎯 面试怎么问
- CSS 变量和 Sass 变量的区别是什么？
- 为什么说 CSS 变量更适合主题切换？
- `var()` 可以写默认值吗？

## ⚠️ 易错点 / 高阶拓展
CSS 变量是运行时生效的，能参与继承和级联；预处理器变量是编译期替换。面试答出这个区别就很关键。


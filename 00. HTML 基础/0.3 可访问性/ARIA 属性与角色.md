---
title: ARIA 属性与角色
tags:
  - HTML
  - 可访问性
  - 面试
status: active
date: 2026-03-18
---

# ARIA 属性与角色

## 📌 核心概念
ARIA 用于给辅助技术补充语义信息，帮助屏幕阅读器理解组件角色、状态和关系。它主要用于原生语义不足的自定义组件，而不是替代所有原生标签。

## 💻 代码示例
```html
<button aria-expanded="false" aria-controls="menu">菜单</button>
<ul id="menu" role="menu">
  <li role="menuitem">个人中心</li>
</ul>
```

## 🛠 实战场景
自定义下拉框、弹窗、Tabs、树组件、菜单组件如果只靠 div 拼出来，通常就需要 ARIA 才能让读屏工具正确理解。

## 🎯 面试怎么问
- ARIA 是用来解决什么问题的？
- 什么情况下才需要手动加 role？
- 为什么说“先用原生标签，再考虑 ARIA”？

## ⚠️ 易错点 / 高阶拓展
错误的 ARIA 可能比没有更糟。原生 button、input、dialog 自带大量语义，优先使用原生能力。


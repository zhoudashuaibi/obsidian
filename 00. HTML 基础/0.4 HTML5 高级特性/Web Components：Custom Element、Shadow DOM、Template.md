---
title: Web Components：Custom Element、Shadow DOM、Template
tags:
  - HTML
  - HTML5 高级特性
  - 面试
status: active
date: 2026-03-18
---

# Web Components：Custom Element、Shadow DOM、Template

## 📌 核心概念
Web Components 是浏览器原生组件化方案，核心由 Custom Elements、Shadow DOM 和 Template 等能力组成。它让你可以定义自定义标签并封装内部结构和样式。

## 💻 代码示例
```html
class MyCard extends HTMLElement {
  connectedCallback() {
    this.attachShadow({ mode: 'open' });
    this.shadowRoot.innerHTML = `<p>Hello Card</p>`;
  }
}
customElements.define('my-card', MyCard);
```

## 🛠 实战场景
设计系统、跨框架组件封装、浏览器原生组件复用时，Web Components 是很常被讨论的方向。

## 🎯 面试怎么问
- Web Components 包含哪几部分能力？
- Shadow DOM 解决了什么问题？
- 为什么它没有完全取代 React/Vue 组件体系？

## ⚠️ 易错点 / 高阶拓展
Web Components 强在标准化和跨框架，但状态管理、模板表达、生态开发体验未必比成熟框架更顺手。


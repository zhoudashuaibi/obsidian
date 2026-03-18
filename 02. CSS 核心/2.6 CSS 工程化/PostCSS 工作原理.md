---
title: PostCSS 工作原理
tags:
  - CSS
  - CSS 工程化
  - 面试
status: active
date: 2026-03-18
---

# PostCSS 工作原理

## 📌 核心概念
PostCSS 本身不是预处理器，而是一个基于 AST 的 CSS 转换平台。它先把 CSS 解析成语法树，再通过插件做转换，最后输出新的 CSS。自动补前缀、现代语法降级、lint 都能基于它完成。

## 💻 代码示例
```css
/* 输入 */
.example {
  user-select: none;
}

/* 经 autoprefixer 处理后可能输出 */
.example {
  -webkit-user-select: none;
  user-select: none;
}

```

## 🛠 实战场景
Vite、Webpack、Tailwind、autoprefixer 等现代前端工具链里几乎都能看到 PostCSS，它是 CSS 构建流水线的重要中间层。

## 🎯 面试怎么问
- PostCSS 和 Sass/Less 有什么区别？
- PostCSS 为什么说是“插件平台”？
- autoprefixer 是如何工作的？

## ⚠️ 易错点 / 高阶拓展
很多人把 PostCSS 当成某个具体语法，其实它更像“处理框架”。高阶会追问 AST、插件执行顺序和浏览器兼容目标配置。


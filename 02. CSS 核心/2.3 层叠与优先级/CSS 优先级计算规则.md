---
title: CSS 优先级计算规则
tags:
  - CSS
  - 层叠与优先级
  - 面试
status: active
date: 2026-03-18
---

# CSS 优先级计算规则

## 📌 核心概念
CSS 冲突时并不是只看选择器长短，而是按来源、`!important`、特异性和书写顺序综合决定。特异性通常可理解为：内联样式 > ID > 类/属性/伪类 > 标签/伪元素。

## 💻 代码示例
```css
#app .card {
  color: blue;
}

.card.active {
  color: red;
}

.card {
  color: green;
}

```

## 🛠 实战场景
多人协作项目里，样式覆盖失控经常来自优先级设计混乱。理解规则后才能避免一路叠 `!important`。

## 🎯 面试怎么问
- CSS 优先级是怎么比较的？
- `!important` 的优先级一定最高吗？
- 为什么同样是类选择器，后写的会生效？

## ⚠️ 易错点 / 高阶拓展
现代 CSS 还会遇到 `:where()`、`:is()`、层叠层 `@layer` 等新机制。面试基础先答经典规则，再补充新特性即可。


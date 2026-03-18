---
title: provide 与 inject 响应式传递
tags:
  - Vue
  - 组合式 API
  - 面试
status: active
date: 2026-03-18
---

# provide 与 inject 响应式传递

## 📌 核心概念
`provide/inject` 用于祖先向后代跨层传值。它本身只负责注入关系，是否响应式取决于你提供的值本身是不是 `ref`、`reactive` 或 `computed`。

## 💻 代码示例
```js
const theme = ref('dark');
provide('theme', theme);

const injectedTheme = inject('theme');
console.log(injectedTheme.value);
```

## 🛠 实战场景
组件库、表单容器、Tabs、主题系统很适合用 provide/inject，避免层层透传 props。

## 🎯 面试怎么问
- `provide/inject` 默认是响应式的吗？
- 它适合替代全局状态管理吗？
- 为什么常建议用 Symbol 作为 key？

## ⚠️ 易错点 / 高阶拓展
如果直接 provide 普通对象字面量，后续替换引用未必如你预期地响应。团队里更推荐封装成 composable 并约束注入键。


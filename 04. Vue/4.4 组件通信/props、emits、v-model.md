---
title: props、emits、v-model
tags:
  - Vue
  - 组件通信
  - 面试
status: active
date: 2026-03-18
---

# props、emits、v-model

## 📌 核心概念
Vue 组件通信的基础是父传子 `props`、子传父 `emits`。`v-model` 本质是“特定 prop + update 事件”的语法糖，在 Vue 3 中支持多个 model 和自定义参数。

## 💻 代码示例
```js
const props = defineProps({ modelValue: String });
const emit = defineEmits(['update:modelValue']);

function onInput(e) {
  emit('update:modelValue', e.target.value);
}
```

## 🛠 实战场景
表单组件、弹窗开关、分页器、搜索框几乎都要围绕 props 与 emit 设计数据流，`v-model` 让这类双向绑定场景更自然。

## 🎯 面试怎么问
- `v-model` 底层展开成什么？
- Vue 3 为什么推荐声明 `emits`？
- 一个组件可以有多个 `v-model` 吗？

## ⚠️ 易错点 / 高阶拓展
双向绑定不等于组件内部随意改 props。仍应遵守单向数据流，子组件通过事件通知父组件更新。


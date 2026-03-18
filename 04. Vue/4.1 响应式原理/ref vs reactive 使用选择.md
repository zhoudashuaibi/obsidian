---
title: ref vs reactive 使用选择
tags:
  - Vue
  - 响应式原理
  - 面试
status: active
date: 2026-03-18
---

# ref vs reactive 使用选择

## 📌 核心概念
`ref` 适合包装基础类型或单值引用，读取写入通过 `.value`；`reactive` 适合包装对象、数组、Map 等结构，直接代理原对象。两者都能做响应式，但语义和解包行为不同。

## 💻 代码示例
```js
const count = ref(0);
count.value += 1;

const form = reactive({
  name: '',
  age: 18,
});
form.age += 1;
```

## 🛠 实战场景
组合式 API 中几乎所有状态设计都会遇到这个选择题。选得合理，代码会更清晰，也更少踩解构丢响应式的坑。

## 🎯 面试怎么问
- `ref` 和 `reactive` 有什么区别？
- 为什么模板里能直接用 ref 而脚本里要 `.value`？
- 对象类型为什么有时仍会用 `ref` 包？

## ⚠️ 易错点 / 高阶拓展
`reactive` 解构后会丢失响应式，通常需要 `toRefs` / `storeToRefs`；`ref` 包对象时内部也会走响应式转换，这点很容易被忽略。


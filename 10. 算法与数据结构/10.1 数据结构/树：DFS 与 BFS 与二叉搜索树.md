---
title: 树：DFS 与 BFS 与二叉搜索树
tags:
  - 算法与数据结构
  - 10.1 数据结构
  - 面试
status: active
date: 2026-03-18
---

# 树：DFS 与 BFS 与二叉搜索树

## 📌 核心概念
树遍历常分深度优先 DFS 和广度优先 BFS；二叉搜索树 BST 则额外满足左子树小于根、右子树大于根的有序性质。

## 💻 代码示例
```js
function bfs(root) {
  const queue = [root]
  while (queue.length) {
const node = queue.shift()
if (!node) continue
console.log(node.val)
queue.push(node.left, node.right)
  }
}
```

## 🛠 实战场景
部门组织树、菜单树、评论树、路由树都能映射到这类题型。

## 🎯 面试怎么问
- DFS 和 BFS 的适用场景？
- BST 中序遍历为什么有序？
- 如何判断一棵树是否平衡？

## ⚠️ 易错点 / 高阶拓展
递归写 DFS 简洁，但树深很大时要考虑栈溢出风险。

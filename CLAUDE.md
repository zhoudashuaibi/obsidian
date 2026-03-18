# 前端知识库 - Claude 工作指南

## 项目说明

本 Obsidian Vault 用于系统整理 **5年前端开发面试知识体系**，目标覆盖大厂/中厂/初创公司面试。

- **技术栈**：React / Vue 为主，兼顾 Node.js 全栈与移动端/小程序
- **核心文件**：[[前端面试知识目录]]（知识地图入口）

---

## Obsidian Markdown 规范

> 本库所有 `.md` 文件使用 **Obsidian Flavored Markdown**，必须激活 `obsidian-cli`  `obsidian-markdown` skill 后再编辑。

### 激活方式

在 Claude Code 中执行：

```
/obsidian-markdown
/obsidian-cli
```

### 强制规范

1. **内部链接**：必须带文件夹前缀 `[[前段知识库/笔记名|显示文字]]`，否则点击时文件会创建到 Vault 根目录
2. **外部链接**：仅对外部 URL 使用 `[text](url)`
3. **Frontmatter**：每个新笔记必须包含以下属性：
   ```yaml
   ---
   title: 笔记标题
   tags:
     - 分类标签
   date: YYYY-MM-DD
   status: draft | active | archived
   ---
   ```
4. **Callout**：重要信息使用 `> [!type]` 语法，常用类型：
   - `> [!tip]` 提示
   - `> [!warning]` 警告
   - `> [!example]` 示例
   - `> [!note]` 备注
5. **标签规范**：
   - `#面试` `#前端` `#React` `#Vue` `#Node` `#算法` `#性能优化` `#工程化` `#网络` `#移动端`
   - 学习状态：`#已完成` `#进行中` `#待学习`

### 知识点笔记模板

每个知识点笔记使用以下固定结构：

```markdown
---
title: 知识点名称
tags:
  - 技术分类
  - 面试
status: active
date: YYYY-MM-DD
---

# 知识点名称

## 📌 核心概念
（200字以内，解释是什么、为什么重要）

## 💻 代码示例
（可直接运行的代码，含中文注释）

## 🛠 实战场景
（真实业务场景案例）

## 🎯 面试怎么问
（3~5个高频面试题 + 答题思路提示）

## ⚠️ 易错点 / 高阶拓展
（初中级开发者常踩的坑，大厂追问的深度问题）
```

---

## 工作流约定

### 生成新知识点笔记

1. 用户说「讲解 [知识点名称]」
2. Claude 用固定模板输出内容
3. 保存为 `前段知识库/知识点名称.md`
4. 在 [[前端面试知识目录]] 中对应条目添加 wikilink

### 文件命名规则

- 使用中文文件名，与知识目录中的 wikilink 完全一致
- 示例：`Fiber 架构：为什么引入与核心数据结构.md`

---

## 语言约定

- Claude 回答：**中文**
- 代码注释：**中文**
- 文件名/wikilink：**与目录完全一致**

---

## 相关技能

| Skill               | 用途                                                         |
| ------------------- | ------------------------------------------------------------ |
| `obsidian-markdown` | 创建/编辑符合 Obsidian 规范的 Markdown                         |
| `obsidian-cli`      | 通过 CLI 与运行中的 Obsidian 交互：读写笔记、追加内容、全文搜索、管理属性/标签、查看反向链接、插件开发调试等 |

### obsidian-cli 常用命令速查

> [!tip] 前提条件
> 需在 Obsidian 中开启 CLI：**Settings → General → Advanced → Command line interface**

```bash
# 读取笔记
obsidian read file="笔记名"

# 创建笔记（silent 不自动打开）
obsidian create name="新笔记" content="# 标题\n内容" silent

# 追加内容
obsidian append file="笔记名" content="新增内容"

# 全文搜索
obsidian search query="关键词" limit=10

# 修改 frontmatter 属性
obsidian property:set name="status" value="active" file="笔记名"

# 查看标签列表（按数量排序）
obsidian tags sort=count counts

# 查看反向链接
obsidian backlinks file="笔记名"

# 每日笔记追加任务
obsidian daily:append content="- [ ] 新任务"
```

---

*最后更新：2026-03-18*

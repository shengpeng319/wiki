---
title: LLM Wiki
created: 2026-04-18
updated: 2026-04-18
type: concept
tags: [concept, knowledge-base, rag-alternative, ai-agent]
sources: [raw/articles/karpathy-llm-wiki-zhihu.md]
---

# LLM Wiki

由 Andrej Karpathy 提出的知识库设计模式，将知识管理类比为代码开发：LLM 是"程序员"，Obsidian 是"IDE"，Wiki 是"代码库"。

## 核心思想

知识库的核心价值不在于"检索"，而在于"积累"和"复用"。传统 RAG 每次查询从零开始重新检索和合成，效率低下且无知识积累。LLM Wiki 主张在[[Ingest]]时就让 LLM 消化知识，固化到结构化 Markdown 文件，实现知识的复利增长。

## 三层架构

| 层级 | 名称 | 说明 |
|------|------|------|
| Layer 1 | [[Raw Sources]] | 原始资料，只读，LLM 只读不写 |
| Layer 2 | [[The Wiki]] | LLM 生成的 Wiki 页面，完全由 LLM 维护 |
| Layer 3 | [[Schema]] | SCHEMA.md + CLAUDE.md，控制 LLM 行为 |

## 三种核心操作

- **[[Ingest]]** — 把信息变成资产，摄入源文件并生成 wiki 条目
- **[[Query]]** — 复利式的知识探索，已编译的知识直接回答
- **[[Lint]]** — 健康检查，孤儿页面、断链、矛盾检测

## 优势

- ✅ 知识复用：一次编译，多次使用
- ✅ 双向链接：知识之间自动建立连接
- ✅ 持续演进：新旧知识碰撞融合
- ✅ 版本可控：配合 Git 实现版本管理

## 相关

- [[RAG 对比]] — LLM Wiki vs 传统 RAG
- [[Andrej Karpathy]] — 提出者
- [[Obsidian]] — 推荐工具

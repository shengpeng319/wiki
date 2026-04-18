---
title: RAG 对比
created: 2026-04-18
updated: 2026-04-18
type: comparison
tags: [comparison, rag, knowledge-base, llm-wiki]
sources: [raw/articles/karpathy-llm-wiki-zhihu.md]
---

# RAG vs LLM Wiki 对比

## 传统 RAG 的局限性

1. **重复查询和计算** — 每次查询都从零开始重新检索和合成，效率低下
2. **无知识积累** — 知识之间没有建立连接，属于孤岛
3. **无知识演进** — 知识始终是静态的，新旧知识无法碰撞融合

## 核心区别

| 维度 | RAG | LLM Wiki |
|------|-----|----------|
| 检索时机 | 每次查询时动态检索 | 知识预先编译，随时可用 |
| 知识积累 | 孤岛式，无连接 | 网状，双向链接 |
| 知识演进 | 静态，新知识不更新旧知识 | 持续演进，自动更新 |
| 效率 | 每次查询重新计算 | 一次编译，多次使用 |
| 可溯源性 | 依赖向量数据库 | 原始文件在 raw/，完全可溯源 |
| 幻觉风险 | 动态生成，可能 hallucinate | Wiki 页面已固化，风险较低 |

## 适用场景

- **RAG**：数据量极大、实时性要求高的场景（如实时文档问答）
- **LLM Wiki**：个人知识管理、长期研究、深度学习场景

## 相关

- [[LLM Wiki]] — 核心概念
- [[Raw Sources]] — Layer 1

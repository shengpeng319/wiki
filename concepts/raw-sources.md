---
title: Raw Sources
created: 2026-04-18
updated: 2026-04-18
type: concept
tags: [concept, knowledge-base, raw-layer]
sources: [raw/articles/karpathy-llm-wiki-zhihu.md]
---

# Raw Sources（原始资料层）

LLM Wiki 三层架构的第一层。存放未经处理的原始文档，LLM 只读不写。

## 特点

- **不可变（Immutable）** — LLM 只读不写，确保可溯源验证
- **真实来源（Source of Truth）** — 随时可溯源验证 LLM 是否产生幻觉
- **格式多样** — 论文（PDF）、网页文章、图片、数据文件

## 目录结构（建议）

```
raw/
├── articles/       ← 网页文章、博客
├── papers/         ← 学术论文
├── transcripts/    ← 会议记录、访谈
├── assets/        ← 图片、图表
├── pdfs/          ← PDF 文件
├── clippings/     ← 网页剪藏
├── screenshots/   ← 截图
└── data/          ← 数据文件
```

## 使用原则

- 绝不修改 raw/ 下的任何文件
- 纠正在 wiki 页面进行，不是在源文件上修改
- 定期整理，删除已迁移到 wiki 的过时原文

## 相关

- [[LLM Wiki]] — 所属的三层架构
- [[The Wiki]] — 第二层，LLM 编译输出
- [[Schema]] — 第三层，控制 LLM 行为

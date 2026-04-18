---
title: Wiki Schema
created: 2026-04-18
updated: 2026-04-18
type: meta
tags: [meta, schema]
---

# Wiki Schema

## Domain
AI/ML 研究、量化交易、自动化交易平台、AI 底层架构与新技术学习

## Conventions
- 文件名：小写、连字符、无空格（如 `transformer-architecture.md`）
- 每个页面以 YAML frontmatter 开头
- 使用 `[[wikilinks]]` 建立页面间链接（每页至少 2 个外链）
- 更新页面时必须更新 `updated` 日期
- 每个新页面必须添加到 `index.md` 对应 section
- 所有操作必须追加到 `log.md`

## Frontmatter 格式
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary | raw
tags: [tag1, tag2]
sources: [raw/articles/source-name.md]
---
```

## Tag Taxonomy

### AI/ML
- `model` — 模型架构、模型发布
- `architecture` — 神经网络架构、Transformer、CNN 等
- `training` — 训练方法、RLHF、DPO、GRPO
- `fine-tuning` — 微调技术、LoRA、QLoRA
- `inference` — 推理优化、量化、加速
- `alignment` — 对齐技术、安全
- `benchmark` — 评测基准、MMLU、HumanEval
- `multimodal` — 多模态模型、视觉、语言
- `reasoning` — 推理能力、CoT、工具调用
- `agent` — AI Agent、自动化工作流

### 量化交易
- `strategy` — 交易策略、因子
- `indicator` — 技术指标、信号
- `backtest` — 回测框架、绩效分析
- `risk-management` — 风险管理、仓位管理
- `execution` — 订单执行、API 对接
- `market-structure` — 市场结构、订单簿
- `data` — 数据源、数据处理

### 平台与自动化
- `platform` — 交易平台、Broker
- `workflow` — 工作流自动化
- `api` — API 设计、接口
- `infrastructure` — 基础设施、部署
- `trading-bot` — 交易机器人开发

### 人物/机构
- `person` — 人物页面
- `company` — 公司、研究机构
- `lab` — 实验室、AI 组织
- `open-source` — 开源项目

### 元标签
- `comparison` — 对比分析
- `timeline` — 时间线、进展
- `controversy` — 争议、讨论
- `prediction` — 预测、判断
- `draft` — 草稿、未完成
- `literature` — 文献、论文
- `resource` — 资源、工具推荐

## Page Thresholds
- **创建页面**：实体/概念在 2+ 来源中出现，或在单一来源中处于核心地位
- **更新现有页面**：新来源提到了已覆盖的内容
- **不创建页面**：一次性提及、次要细节、领域外内容
- **拆分页面**：超过 200 行时拆分为子主题
- **归档页面**：内容完全被取代时移至 `_archive/`

## Entity Pages
每个 notable 实体一页，包括：
- 概述/是什么
- 关键事实和日期
- 与其他实体的关系 ([[wikilinks]])
- 来源引用

## Concept Pages
每个概念/主题一页，包括：
- 定义/解释
- 当前知识状态
- 开放问题或争议
- 相关概念 ([[wikilinks]])

## Comparison Pages
并排分析，包括：
- 比较的对象和原因
- 比较维度（尽量用表格）
- 结论或综合判断
- 来源

## Update Policy
新信息与现有内容冲突时：
1. 看日期 — 新来源一般取代旧来源
2. 真正矛盾时，两种观点都保留并标注日期和来源
3. 在 frontmatter 标记：`contradictions: [page-name]`
4. 在 lint 报告中标记，供用户审阅

## Raw Layer Policy
- `raw/` 目录下所有内容不可修改
- 原文存放，纠正在 wiki 页面进行
- 定期整理，删除已迁移到 wiki 的过时原文

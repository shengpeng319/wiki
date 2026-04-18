# Wiki Log

> 所有 wiki 操作的 chronological record。Append-only。
> Format: `## [YYYY-MM-DD] action | subject`
> Actions: ingest, update, query, lint, create, archive, delete
> 此文件超过 500 条时轮换：重命名为 `log-YYYY.md`，新建空白 log.md。

## [2026-04-18] create | Wiki initialized
- Domain: AI/ML 研究、量化交易、自动化交易平台、AI 底层架构与新技术
- Structure created: SCHEMA.md, index.md, log.md
- Subdirectories: raw/articles/, raw/papers/, raw/transcripts/, raw/assets/, entities/, concepts/, comparisons/, queries/, _archive/
- Tag taxonomy: 25 tags across AI/ML, Quant, Platform, People/Orgs, Meta

## [2026-04-18] update | 根据 ima 文章补充 wiki 规范
- 新增 raw/ 子目录细分：pdfs/, clippings/, screenshots/, data/
- 新增 CLAUDE.md（LLM 行为指令层）
- 补充 Obsidian 插件推荐：Git、Custom Attach Location、Obsidian Web Clipper、Graphify
- 明确每页至少 2 个 wikilinks 外链规则

## [2026-04-18] ingest | 摄入首批文章
- 来源：raw/articles/karpathy-llm-wiki-zhihu.md（知乎文章）
- 来源：raw/articles/vibecoding-pro-code-bilibili.md（B站视频笔记）
- 新建 entities/andrew-karpathy.md
- 新建 concepts/llm-wiki.md
- 新建 concepts/raw-sources.md
- 新建 concepts/vibecoding.md
- 新建 comparisons/rag-comparison.md
- 更新 index.md（Total pages: 7）

## [2026-04-18] ingest | 摄入笔记同步助手剩余文章
- 来源：raw/articles/tradingview-12-agents.md
- 来源：raw/articles/investment-consensus-10-funds.md
- 来源：raw/articles/llm-quant-trading.md
- 来源：raw/articles/content-creation-skills.md
- 新建 entities/tradingview-12-agents.md
- 新建 concepts/investment-consensus.md
- 新建 concepts/llm-quant-trading.md
- 新建 concepts/quant-toolchain.md
- 新建 concepts/content-creation-skills.md
- 更新 index.md（Total pages: 15）

## [2026-04-18] ingest | 摄入最后一批文章（9篇全量摄入完成）
- 来源：笔记同步助手/2026-04-18/告别裸奔！搞定 Hermes Agent 后强烈建议尝试的 10 件事.md
- 来源：笔记同步助手/2026-04-18/聊聊LLM如何破解传统量化策略的致命困境，复盘派大星-星大派.md
- 来源：笔记同步助手/2026-04-18/冠军开发者开源 Vibecoding 工作流，GitHub 获得 11 万星标.md
- 新建 concepts/hermes-agent-best-practices.md（Hermes十大配置）
- 新建 concepts/llm-vs-traditional-quant.md（LLM vs 传统量化5层对比）
- 更新 vibecoding.md（补充 Pro Code 10.9万星标数据）
- 更新 index.md（Total pages: 17）
- 注：llm-quant-trading.md 原文即松鼠Quant文章，与 llm-vs-traditional-quant.md 合并处理

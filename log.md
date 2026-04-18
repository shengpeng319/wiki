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

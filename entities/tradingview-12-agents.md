---
title: tradingview
created: 2026-04-18
updated: 2026-04-18
type: entity
tags: [entity, trading-bot, open-source, tradingview, ai-agent]
sources: [raw/articles/tradingview-12-agents.md]
---

# tradingview (iamrichardD/tradingview)

GitHub 项目：TradingView Pine Script v6 深度集成 + 12 个专业 AI Agent 协作的量化策略开发系统。

## 核心数据

- **BTC MACD 策略胜率：85.71%**（Profit Factor 2.687）
- **测试框架：35+**，通过率 95%+
- **Phase 1-4 已完成**，Phase 5 进行中

## 12 Agent 架构

### 战略管理层（Strategic Management Tier）
- **Fletcher** — Context Manager，仓库状态分析、Agent 协调（所有工作流必须从 Fletcher 开始）
- **Seldon** — Project Manager，Epic 规划、资源分配
- **Herbie** — Agile Coach，流程优化、质量把控

### 技术专家层（Technical Excellence Specialists）
- **Vex** — Pine Script v6 专家，语法合规、优化
- **Maxwell** — 量化性能分析师，回测验证、统计分析

### 风险与时间完整性层（Risk & Temporal Integrity Specialists）
- **Chronos** — 前瞻偏差检测，时间完整性、历史准确性
- **Atlas** — 动态风险管理，ATR 仓位控制、多层风控

### 市场动态层（Market Dynamics Specialists）
- **Mercury** — 加密市场专家，BTC 参数优化、波动模式
- **Titan** — 市场结构分析师，CHoCH/BOS/IDM 检测

## Agent 协调流程

```
Fletcher（Context Manager）
    ↓
Seldon（Project Manager）
    ↓
Herbie（Agile Coach）
    ↓
Specialized Agent 部署：
├── Technical: Vex + Maxwell
├── Risk: Chronos + Atlas
└── Market: Mercury + Titan
```

## BTC MACD 策略性能

| 指标 | TradingAgents | 行业基准 | AI 优势 |
|------|--------------|----------|---------|
| 胜率 | 85.71% | 50-60% | +43% |
| Profit Factor | 2.687 | 1.2-1.5 | +79% |
| 风险调整收益 | +$32.36 | 基本持平 | 持续盈利 |
| 交易选择性 | 21 笔精选 | 300+ 笔 | 14× 更精准 |

## 相关

- [[trading-bot]] — 交易机器人
- [[ai-agent]] — AI Agent 相关
- [[risk-management]] — 风险管理（Atlas）

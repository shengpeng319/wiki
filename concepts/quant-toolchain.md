---
title: 量化交易工具链
created: 2026-04-18
updated: 2026-04-18
type: concept
tags: [concept, platform, trading-bot, backtest, strategy]
sources: [raw/articles/tradingview-12-agents.md, raw/articles/llm-quant-trading.md]
---

# 量化交易工具链

本文从两篇笔记中整理出的量化交易工具链，从策略开发到执行的完整技术栈。

## 策略开发平台

### TradingView + Pine Script v6
- 策略编写和回测
- [[tradingview-12-agents]] 扩展：12 个 AI Agent 协作开发

### ssquant（松鼠Quant 开源框架）
- 全自动交易智能体框架
- 框架开源，策略代码可定制
- 支持派大星（趋势追踪）、星大派（均值回归/反向）

## 回测框架

- TradingView 内置回测
- 35+ 测试框架，通过率 95%+
- Maxwell Agent：量化性能分析，回测验证、统计分析
- Chronos Agent：前瞻偏差检测，确保时间完整性

## 订单执行

- 支持主流 Broker API
- 执行层需对接交易所
- 核心指标：滑点、手续费（高频交易最大敌人）

## AI Agent 工具链

- **Fletcher**：上下文管理，Agent 协调
- **Vex**：Pine Script v6 合规性
- **Atlas**：ATR 仓位控制、多层风控
- **Mercury**：BTC 参数优化
- **Titan**：CHoCH/BOS/IDM 市场结构检测

## 相关

- [[trading-bot]] — 交易机器人
- [[strategy]] — 交易策略
- [[risk-management]] — 风险管理
- [[backtest]] — 回测框架

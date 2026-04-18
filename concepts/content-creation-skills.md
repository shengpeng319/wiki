---
title: 内容创作技能包
created: 2026-04-18
updated: 2026-04-18
type: concept
tags: [concept, workflow, content-creation, ai-agent, automation]
sources: [raw/articles/content-creation-skills.md]
---

# 内容创作技能包

5 个把内容创作从写作到排版全流程自动化的 Agent 技能包。

## 技能包列表

### 1. Jia-style-writing
解决"怎么快速写完"的问题。
- 消化历史文章，抽取风格规范（开场、论证、语言、自审）
- 标准化作业流程：拆 brief → ToDo → outline → 分段写作 → Review → final.md
- 技术栈：MiniMax 驱动 + Claude Code

### 2. infocard
解决"内容好看、能传播"的问题。
- 分析内容密度（Low/Medium/High），决定卡片"呼吸节奏"
- 感知内容情绪，自动选配色方案
- 选择版式骨架（对比型/流程型/并列型/放射型），生成 HTML
- 输出直接嵌在 Markdown 里，Obsidian 打开即可渲染

### 3. excalidraw-diagram
解决"配图跟不上"的问题。
- 支持三种输出：Obsidian .md（Mermaid 语法）、标准 .excalidraw、动画版
- 边写边画，图表作为对话输出而非单独任务
- 推荐优先使用 .md 格式（Mermaid 语法），最稳定

### 4. html-ppt-skill
解决"PPT 作为配图工具"的问题。
- 36 种主题（小红书白底、暗色技术风、VC 路演等）
- 14 套完整 deck 模板
- 键盘操控：T 切换主题，A 切动画
- 纯 HTML 静态文件，任何浏览器打开

### 5. wechat-to-markdown
解决"公众号文章无法直接用"的问题。
- 一行命令：`wechat-article-to-markdown "url" -o ./output`
- 使用 Camoufox 浏览器获取文章
- 提取元数据 + 下载图片到本地 + 替换 Markdown 路径
- 并发下载图片，速度快
- 本质：把"微信文章"变成知识库里可搜索、可引用的结构化条目

## 开源项目地址

1. excalidraw-diagram：github.com/coleam00/excalidraw-diagram-skill
2. html-ppt-skill：github.com/lewislulu/html-ppt-skill
3. infocard：github.com/markdown-viewer/skills
4. wechat-to-markdown：github.com/jackwener/wechat-article-to-markdown

## 相关

- [[workflow]] — 工作流
- [[ai-agent]] — AI Agent

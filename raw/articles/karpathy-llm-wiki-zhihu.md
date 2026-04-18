---
author: 关于作者菩提墨公众号"菩提老鹰"，努力生活，乐观向前！回答文章关注者​关注​发私信
source: zhuanlan.zhihu.com
url: https://zhuanlan.zhihu.com/p/2025163875935428908?share_code=1jFSa9AMoljlL&utm_psn=2025247451599095067&utm_source=wechat_session&utm_medium=social&s_r=0
saved: 2026-04-18 22:25:15
tags:
id: 54952e92-1d29-4ad9-b2b3-9992178ba31a
---

> _💡 **前言**：你有没有这样的困扰——用 ChatGPT、NotebookLM 等工具上传文档后，每次问问题都是临时检索，知识之间没有连接，越用越散乱？最近 AI 大神 Andrej Karpathy 分享了一个颠覆性的设计方案 —— **LLM Wiki**，让 LLM 不再是临时检索工具，而是你的"知识库维护者"，知识像代码一样可以被持续构建和维护！_

**核心洞察：** 知识库的价值不在于"检索"，而在于"积累"和"复用"！

---

## **📋 目录**

1.  1\. [传统 RAG 的局限性](https://link.zhihu.com/?target=https%3A//doocs.gitee.io/md/%25E4%25B8%25BA%25E4%25BB%2580%25E4%25B9%2588%25E4%25BC%25A0%25E7%25BB%259F-rag-%25E4%25B8%258D%25E5%25A4%259F%25E5%25A5%25BD)
2.  2\. [LLM Wiki 核心思想](https://link.zhihu.com/?target=https%3A//doocs.gitee.io/md/llm-wiki-%25E6%2598%25AF%25E4%25BB%2580%25E4%25B9%2588)
3.  3\. [如何落地LLM Wiki](https://link.zhihu.com/?target=https%3A//doocs.gitee.io/md/%25E5%25A6%2582%25E4%25BD%2595%25E8%2590%25BD%25E5%259C%25B0LLM-Wiki)
4.  4\. [如何使用LLM Wiki](https://link.zhihu.com/?target=https%3A//doocs.gitee.io/md/%25E5%25A6%2582%25E4%25BD%2595%25E4%25BD%25BF%25E7%2594%25A8)
5.  5\. [知识扩展](https://link.zhihu.com/?target=https%3A//doocs.gitee.io/md/%25E7%259F%25A5%25E8%25AF%2586-%25E6%2589%25A9%25E5%25B1%2595)

## **为什么传统 RAG 不够好？**

用户上传各类文档之后，进行向量化存储，然后用户进行提问，通过把用户的问题转成向量查询，检索相关的

文档片段

, 然后把这些相关片段交给 LLM大模型进行

临时合成答案

，最终把答案返回给用户。

传统 RAG 知识库有自己固有的缺点

1、重复查询和计算  
每次查询都从零开始重新检索和合成 ，效率相对比较低下

2、无知识积累  
知识之间没有建立连接的，属于孤岛

3、无知识演进  
知识始终是静态的，新旧知识无法碰撞而融合

> _Tip_  
> _它是一种实现个人知识库的思路，一种设计模式_

LLM Wiki 采用三层架构和三种核心操作 ，外加一个导航文件。

三层架构  
\- Raw Sources  
\- Wiki  
\- Schema  
三种核心操作

-   • Ingest
-   • Query
-   • Lint  
    导航文件
-   • index.md

> _对于三层架构是如何工作的，三种核心操作的逻辑又是什么，这些概念性知识点我们放到后面，感兴趣的可以去详细阅读_

## **如何落地LLM Wiki**

对于普通的用户我们如何使用LLM Wiki呢，如果自己去阅读大佬的设计思路（[原文链接 https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f](https://link.zhihu.com/?target=https%3A//gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) ），对于普通人来说难度挺大的。

**核心工具：**

✅ Obsidian（推荐）
   - 本地 Markdown 编辑器
   - 支持双向链接
   - 图形视图展示知识网络
   - 丰富的插件生态

✅ LLM Agent
   - Claude Code（推荐）
   - OpenAI Codex
   - 其他支持文件操作的 LLM

✅ 可选工具
   - Obsidian Web Clipper（网页剪藏）
   - Obsidian Graph View（知识图谱）
   - Dataview 插件（动态查询）

现在我们借助于AI Agent来实现。具体如下

### **初始化 obsidian**

> _Tip_  
> _为何选obsidian 天然的知识双向连接，好用的 Obsidian web clippers 可以把网页内容转变成Markdown保存到obsidian中_

1、下载安装 \[Obsdian 软件 [https://obsidian.md/](https://link.zhihu.com/?target=https%3A//obsidian.md/)\]\[[https://obsidian.md/](https://link.zhihu.com/?target=https%3A//obsidian.md/)\]  
2、初始化一个 Vaut ，就是基于Obsidian创建一个知识库，是个本地目录  
3、进入这个本地目录打开

Claude Code

(这里选择你用的AI Agent就行，比如Qwen Code、Opencode等)

### **LLM Wiki初始化**

在打开的AI Agent对话中给AI如下提示词 （最快的方式）

https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
请阅读这篇设计模式，并以此为规范，帮我在这个文件夹里初始化我的 LLM-Wiki，我们现在开始录入第一篇文章。

然后等一段时间之后会有如下结果

LLM Wiki 已初始化完成！当前结构：

myainotes/
├── wiki/                  # Wiki 主目录
│   ├── CLAUDE.md         # Schema 规范（本文件）
│   ├── index.md          # 内容索引
│   ├── log.md            # 操作日志
│   ├── entities/         # 实体页
│   ├── concepts/         # 概念页
│   ├── sources/          # 来源摘要
│   └── summaries/        # 综合分析
└── raw/                  # 原始资料库（不可变）

Wiki 核心文件：
- wiki/CLAUDE.md - 告诉 LLM 如何维护 Wiki 的规范
- wiki/index.md - 按类别列出所有页面
- wiki/log.md - 操作时间线

---
现在录入第一篇文章。请提供：

1. 来源：是一个 URL（网页文章），还是本地文件？
2. 主题方向：关于什么的知识？（例如：机器学习、个人成长、产品设计等）

如果你有具体的文章链接或文件，可以直接给我，我来帮你摄取并建立第一组 Wiki 页面。

-   • wiki/CLAUDE.md 中详细LLM如何维护Wiki页面，包括我们上面提到的三层架构、三个核心操作是什么、每个页面的格式、索引页如何建立、log如何记录等
-   • wiki/index.md 就是索引页就是个人知识库的入口，我们自己查看和AI读取都是基于此入口
-   • 这里raw目录就是存放我们自己的原始文档的目录，这个目录AI没有帮我们初始化是因为我们每个人存放整理笔记的思路是不一样的，这里我们就按照自己的历史习惯来就行

比如我这里如下

├── raw
│   ├── AI前言
│   ├── 技术类
│   │   ├── 运维
│   │   └── 数据库
│   │       └── Elasticsearch
│   │       └── TiDB
│   │       └── MySQL
│   ├── 个人成长
│   │   ├── 心理学
│   │   └── 读书笔记
│   ├── 家庭成长
│   └── 营养与健康

---

## **如何使用**

正如上面的提示

来源：是一个 URL（网页文章），还是本地文件？

我们可以把自己感兴趣的文章链接直接喂给AI，或者自己把文件保存到

raw

目录下对应的位置，然后告诉AI文件位置即可

> _Tip_  
> _案例介绍_

这里我们尝试下大佬

Dan Koe

前段时间很火的

如何在一天内修复你的人生

原文地址 [https://x.com/thedankoe/status/2010751592346030461](https://link.zhihu.com/?target=https%3A//x.com/thedankoe/status/2010751592346030461)

> _因为是外网访问的，我这里先通过浏览器打开之后使用
> 
> Obsidian web clipper
> 
> 保存网页内容到本地raw目录下_

然后给AI如下提示

我使用obsidian web clipper 保存这个连接的内容到 @raw/How to fix your entire life in 1 day.md

然后就看到AI帮我们进行整理了

最终的整理结果如下

⏺ 第一篇文章摄取完成！Wiki 现在包含：

  wiki/
  ├── CLAUDE.md                    # Schema 规范
  ├── index.md                     # 索引
  ├── log.md                       # 操作日志
  ├── entities/
  │   ├── Dan-Koe.md              # 作者
  │   ├── Naval-Ravikant.md       # 引用来源
  │   ├── Alfred-Adler.md         # 引用来源
  │   ├── Maxwell-Maltz.md        # 引用来源
  │   └── Mihaly-Csikszentmihalyi.md  # 引用来源
  ├── concepts/
  │   ├── 行为改变.md
  │   ├── 身份.md
  │   ├── 目标导向.md
  │   ├── 心理发展阶段.md
  │   ├── 智能.md
  │   ├── 心理挖掘.md
  │   ├── 反愿景.md
  │   └── 愿景.md
  └── sources/
      └── How-to-fix-your-entire-life-in-1-day.md

  本次操作：
  - 1 个来源摘要
  - 5 个实体页面
  - 8 个概念页面
  - 已更新 index.md 和 log.md

  Wiki 已就绪，可以继续摄取下一篇文章或向我提问。

> _Tip_  
> _LLM Wiki会在 wiki/sources 目录下提取一份原始文件的核心内容到这里这里，所以
> 
> raw
> 
> 就只是存放原始文件，至于后续你变更了文件位置等都不影响已经生成的内容_

你可以打开index.md 查看具体的内容。

-   • 后续问答的时候，你就在Claude中进行正常的提问就行， 他会先读 index.md 找到相关页面，再读取具体内容回答
-   • 后续更新知识到知识库时，如果是关联性内容，LLM WIki会自动帮你更新index.md及相关知识的双向连接 （你可以通过Obsdian “关系图谱” 来查看双向连接情况）

---

## **知识扩展**

### **三层架构**

### **第一层：Raw Sources（原始源文件）**

**定义：** 你精心挑选的原始文档集合。

**特点：**

-   • ✅ 不可变（Immutable）—— LLM 只读不写
-   • ✅ 真实来源（Source of Truth）
-   • ✅ 格式多样——论文、文章、图片、数据文件

---

### **第二层：The Wiki（LLM 生成的知识库）**

**定义：** 由 LLM 完全拥有和维护的 Markdown 文件集合。

**特点：**

-   • ✅ LLM 完全控制——人只读不写
-   • ✅ 持久化存储——文件保存在本地
-   • ✅ 结构化组织——自动建立目录和链接
-   • ✅ 持续更新——新源到来时自动维护

---

### **第三层：The Schema（配置文件）**

**定义：** 告诉 LLM 如何维护 Wiki 的元配置文件。

**作用：**

-   • 📋 定义 Wiki 结构规范
-   • 📋 规定页面格式约定
-   • 📋 指定工作流程
-   • 📋 配置维护规则

### **工作流程**

### **Ingest 流程**

1.  1\. 读取源文件
2.  2\. 提取关键信息
3.  3\. 与用户讨论要点
4.  4\. 创建/更新摘要页
5.  5\. 更新相关实体页
6.  6\. 更新相关概念页
7.  7\. 更新 index.md
8.  8\. 在 log.md 记录操作

### **Query 流程**

1.  1\. 读取 index.md 找到相关页面
2.  2\. 读取相关页面
3.  3\. 合成答案
4.  4\. 提供引用
5.  5\. 询问是否将答案存回 Wiki

### **Lint 流程**

1.  1\. 检查页面间的矛盾
2.  2\. 查找孤立页面
3.  3\. 识别缺失的概念页
4.  4\. 检查过时声明
5.  5\. 生成修复建议

---

如果这个系列对你有帮助，欢迎：

1.  1\. **收藏** - 方便以后查找
2.  2\. **分享、点赞** - 让更多人知道

**有问题？** 欢迎在评论区留言，看到后会第一时间回复！
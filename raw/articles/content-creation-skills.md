---
author: 张佳
source: 微信公众号
url: https://mp.weixin.qq.com/s?__biz=MjM5OTEwNjI2MA==&mid=2651926483&idx=2&sn=f52bafd0e824fed147c4764d0b751a22&chksm=bc5aac98800cac068acdde798a4e77c148579ee33c7bddb0992af9bbb22dfbe39369fe896dd8&mpshare=1&scene=1&srcid=0418sAT17LWvk6te45RBQ62S&sharer_shareinfo=f01b8f99179c650921906be508a3b6bf&sharer_shareinfo_first=f01b8f99179c650921906be508a3b6bf#rd
saved: 2026-04-18 23:03:48
tags:
id: 175231aa-e23b-4a14-9f41-b5fe7dac9a26
---

公众号名称：人人都是产品经理

作者名称：张佳

发布时间：2026-04-18 10:06

---

如果你不能时时处处把 Agent 用起来，那是没机会把一人公司跑通的。

一人公司确实只有“一个人”，但​**不是只有一个人干活。**

能凭一人之力撑起一家公司的业务运转，不把活分给 Agent 去做，要么累\* 、要么赔\* 。

这篇文章为大家分享 5 个把你从写作、营销场景里彻底解放出来的技能包。

其中 3 个在写这篇文章的时候已经用上了。

![[笔记同步助手/images/a377b9c036b2696a0c9828b514707500_MD5.png]]

## 技能包 1：Jia-style-writing

你现在看到的这篇文章，就是 MiniMax 驱动的 Claude Code 使用 ​`Jia-style-writing` 的技能写出来的。

![[笔记同步助手/images/08d8fe852caa298b67ccc33d054f066b_MD5.png]]

下面是开发这个 Skill 的提示词：

![[笔记同步助手/images/1e02d122015bb1fd0caeba19a37a9e0d_MD5.png]]

Claude 会把我折腾过的几十篇文章消化进去，抽出来一套风格规范文档，包括：

-   `STYLE::OPENING`：我怎么开场
-   `STYLE::BODY`：我怎么展开论证
-   `STYLE::LANG`：我的口语指纹（什么词、什么句式）
-   `STYLE::SELF-REVIEW`：写完自审什么

之后 Agent 在使用这个技能写作时，不是“看一下以前的文章，借鉴一下风格”，而是非常标准化的作业。

它会先拆 bref、做 ToDo、写 outline，之后才开始一段一段的写作，合并成“终稿”前，或做一次 Review，才输出​`final.md`。

![[笔记同步助手/images/9c7f17a594d2db50337e3142b7d0591c_MD5.png]]

这个技能的开发过程中用到了一个非常实用的技能​`wechat-to-markdown`，它可以把公众号文章导出为非常干净的 Markdown + 图片。

我对这个能力做了改造，后面再展开。

​

## 技能包 2：infocard

Jia-style-writing 解决的是"怎么快速写完"的问题。

但内容营销最头疼的是：​**写出来了，怎么让它好看、能传播？**

“好看”有两层意思：

1.  视觉体验好：赏心悦目。
2.  阅读体验好：在投入精力阅读之前先提纲挈领的知道大概，避免浪费时间。

这篇文章开头的信息图，是不是就起到这个作用了？

它由​`infocard`这个技能实现。

Agent 写完这篇稿子后，我反手把它丢给 Agent，让它用​`infocard`技能整个信息图出来。

Agent 自动做了三件事：

1.  分析内容密度（Low/Medium/High），决定卡片的"呼吸节奏"
2.  感知内容情绪（技术/文学/商业/创意），自动选配色方案
3.  选择版式骨架（对比型/流程型/并列型/放射型），生成 HTML

输出是直接嵌在 Markdown 里的 HTML，不需要你去导出图片，打开 Obsidian 或 Markdown Viewer 就能渲染成卡片。

**这个技能牛在哪？**

-   不是模板填充，是"内容理解 → 版式决策 → 排版输出"的完整链路
-   每张卡片都有明确的视觉层次，不会出现"AI 感"满满的平庸排版
-   直接复制 HTML，公众号、飞书文档、个人网站全能用

换句话说，你只要把内容说清楚，排版的活全交出去。

![[笔记同步助手/images/7fd24a57bc0c1a018aa367a4fd7556bf_MD5.png]]

## 技能包 3：excalidraw-diagram

内容写出来了，摘要卡片有了，可文章里还有一个高频空洞：配图。

Agent 写作最大的问题就是配图跟不上，基本只能写完稿子后再单独调用配图插件或者技能。

画出来的图因为受到其他不相关内容的影响，总是会各式各样的问题，尤其是文本生成图片模型，扭曲到不行。

可以试试​`excalidraw-diagram` 这个技能。

配合我前面第一个写作技能的范式，你可以实现：

1.  Agent 写一段内容
2.  调用这个画图技能，把写完的那一段内容绘制成可视化图表

![[笔记同步助手/images/cc2e5c6e53817df3460818abcd9dafec_MD5.png]]

excalidraw-diagram

它支持三种输出模式：

| 触发词 | 输出格式 | 用途 |
| --- | --- | --- |
| 画图/流程图/思维导图 | Obsidian ​`.md` | 直接在 Obsidian 打开渲染 |
| 标准 Excalidraw | `.excalidraw` | excalidraw.com 打开/分享 |
| Excalidraw 动画 | `.excalidraw`（带动画顺序） | 生成演示动画 |

图自动保存到当前工作目录，不需要手动粘贴 JSON，不需要任何额外操作。

如果你使用 Obsidian 写作，一定要试试这个技能。

我之前在 Obsidian 里写稿时，用这个技能最频繁的场景是​**边写边梳理框架**——

1.  跟 Agent 聊完一个话题（内嵌在 Obsidian 那个）
2.  说一句"帮我把刚才聊的画成思维导图"
3.  图出来了，拖进文章

本质上，它把"图表 = 另一个工具里的一个任务"

变成了

"图表 = 当前对话的一个输出"。

对话不断，图也就不断。

推荐优先使用​`.md`格式那个用 Mermaid 语法写的，比较稳定。

![[笔记同步助手/images/9b038136d20e3a55d0f1a315cd47acba_MD5.png]]

## 技能包 4：html-ppt-skill

PPT 不只可以用来汇报，它还是最好的配图工具！

这篇稿子中，原本应该由​`excalidraw-diagram`完成的配图工作，现在直接替换成​`html-ppt-skill`了。

没办法，太好用了。

这个技能的库存有多夸张：

-   **36 种主题**：从 ​`xiaohongshu-white`（小红书白底）到 ​`tokyo-night`（暗色技术风），从 ​`pitch-deck-vc`（VC 路演）到 ​`magazine-bold`（杂志封面感），基本覆盖所有使用场景
-   **14 套完整 deck 模板**：​`tech-sharing`（技术分享）、​`product-launch`（产品发布）、​`pitch-deck`（路演稿）、​`xhs-post`（小红书图文）——直接打底，改内容就行
-   **键盘操控**：按 T 切换主题，按 A 切动画，纯 HTML 静态文件，任何浏览器打开

使用流程也就 3 步：

1.  写完文章，加一句“为文章每一个小节做一页 PPT 总结”
2.  Agent 推荐 2-3 个主题候选，你选一个
3.  截图、贴进文章里

![[笔记同步助手/images/307c0c0c275be6b926877eebfbde6c2a_MD5.png]]

## 技能包 5：wechat-to-markdown

前面说的四个技能，解决的都是内容输出端。但内容生产还有另一半成本——输入端，也就是​**搜集和整理素材**。

问题在于：微信公众号文章没法直接用。

除了谁家那小谁，没有谁能让自己的 AI 稳定阅读公众号文章。

`wechat-to-markdown` 就是一专门解决这问题的“硬茬”。

直接让你的 Agent 帮你安装：

​

```
uv tool install wechat-article-to-markdown
# 或：pipx install wechat-article-to-markdown
```

用起来就一行命令：

​

```
wechat-article-to-markdown "https://mp.weixin.qq.com/s/xxxx" -o ./output
```

它会：

-   使用 Camoufox 浏览器获取文章内容
-   提取元数据（标题、公众号名、发布时间、原始链接）
-   把图片下载到本地，Markdown 里替换成本地路径
-   代码块提取为围栏代码，不是截图
-   并发下载图片，速度贼快

![[笔记同步助手/images/dfa14e132d149cab4a8bf49440c36be8_MD5.png]]

wechat-to-markdown

本质上，它的价值是把"微信文章"这个信息孤岛，变成了你知识库里的一条可搜索、可引用、可喂给 AI 的结构化条目。

我专门把这个工具开发成了一个技能：看到好文章，随手转发给 Agent 的微信通道。

它会：

1.  导出文章
2.  使用​`infocard`概述文章
3.  使用​`lark-cli`转成 概要画板 + 原文保存到飞书文档

![[笔记同步助手/images/23fe63b961d9b2736d85cbfcbcd119ee_MD5.png]]

---

这 5 个技能包，不是"功能"，是你在内容战场上的"兵器谱"。

一人公司的护城河，不是你比别人更努力，而是你的 Agent 比别人的更能干。

你现在每周花多少时间在排版、做 PPT、抄微信文章、调整 AI 写出来的文风？

这些时间，装上技能包之后，还需要花吗？

你的 Agent 现在能调用几个技能？能照着你的风格写文章吗？

如果还不行，那你用的，还不是 Agent——那只是一个很贵的 Token Plan 消耗器。

以上五个技能的四个均为开源项目，我微调后的版本已经打包到 AI 学习行动圈知识星球了，已经加入星球的小伙伴可以移步星球下载参考。

![[笔记同步助手/images/50e592c66d734dc8e207c3ff846313db_MD5.png]]

扫码加入星球

想要使用原版的，项目地址我放在文末了。

​

## 关于AI学习行动圈

这是我 23 年底开始，和人人都是产品经理社区共同运营的一个圈子，截止目前已经持续运营、维护超过 700 天了，已有超过 5000+圈友！

我的各种 AI 研究心得、发现的好应用、开发的小项目都会在里面分享，目前圈子有核心三个交流学习平台。

​

### 8 个微信群，早报和日常交流

微信群里每天一早有 AI 早报，上下午还有“读报时间”，以及我每天不定期刷屏级的各种 AI 工具体验、提示词编排思考、行业新闻解读同步。

![[笔记同步助手/images/ec2dd8915627269d46085f9cdae32e6d_MD5.png]]

以及，你可以在群里讨论任何与 AI 相关的工具、应用问题，几乎都能找到答案。

![[笔记同步助手/images/82f69e093ca3fce586f1bd2fa880d6fc_MD5.png]]

### 腾讯文档-圈友空间

用来沉淀体系化、深度的 AI 文章和超长的工程化提示词，不定期更新。

当前包括：​`Claude code`、​`Cursor`、​`Manus`等顶级产品的系统提示词和工具列表，各种深度的 Agent 白皮书和实践指南

![[笔记同步助手/images/473f482205da45c111caadd9a249a5a7_MD5.png]]

### 知识星球-每日报告、工具和实战经验分享

我在星球里主要维护「实战分享」「工具箱」和「情报局」三个标签

![[笔记同步助手/images/82078d6e39c9d60d4a2da92fdc9b2112_MD5.png]]

实战分享是可以在日常工作和生活中直接应用的提示词和效率工具。上面截图里的 Step-Back 提示词就非常好用，堪比 o4。在公众号、直播中演示的所有 AI 实战应用的提示词也都在这个标签下。

AI 工具和鲜知道就是好用的、热门的 AI 工具、资讯分享，我把那些太技术、太浮夸的都筛选了，放进这个标签的都是可以直接用来的好玩儿！

加入圈子，跟 5000+ 行动派一起玩 AI、聊 AI，精进起飞～

![[笔记同步助手/images/eae8694f5b743dbea4d0e6b8db4b200c_MD5.png]]

技能开源项目地址：

1.  excalidraw-diagram：https://github.com/coleam00/excalidraw-diagram-skill
2.  html-ppt-skill：https://github.com/lewislulu/html-ppt-skill
3.  infocard：https://github.com/markdown-viewer/skills
4.  wechat-to-markdown：https://github.com/jackwener/wechat-article-to-markdown

---

![[笔记同步助手/images/afe08fd6fcfdba555430fecbf60a0633_MD5.jpg|cover_image]]

张佳 人人都是产品经理
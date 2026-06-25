---
name: knowledge-base-management
description: "Jeffery 的 Obsidian/GitHub 知识库写入与维护 Skill：基于 Personal-OS、LLM Wiki、专题研究库，完成输入入库、Daily/Weekly/Monthly 沉淀、Wiki 编译、MOC 更新、内容资产与企业 AI 培训材料归档。"
triggers:
  - "写入知识库"
  - "记录到知识库"
  - "整理到 Obsidian"
  - "同步到 GitHub"
  - "沉淀成笔记"
  - "更新知识库"
  - "今天内容入库"
  - "Daily Note"
  - "Weekly Review"
  - "Monthly Strategy Review"
  - "知识库管理"
  - "知识库架构"
  - "素材入库"
  - "知识库健康检查"
  - "整理知识库"
  - "企业 AI 培训素材"
  - "内容选题入库"
version: 2.0
updated: 2026-06-25
tags: [knowledge-base, obsidian, github, personal-os, llm-wiki, moc, content-bank, training-delivery]
---

# Knowledge Base Management — Jeffery 知识库写入与维护 Skill

## 0. Skill 定位

本 Skill 用于维护 Jeffery 的 Obsidian/GitHub 知识库。

它不是简单的“保存笔记”工具，而是一套 **AI 可维护的 Personal-OS + LLM Wiki + 专题研究库** 工作流。

核心目标：

1. 把每天的聊天、灵感、工作、文章、播客、工具实验、内容选题、企业 AI 培训素材保存下来。
2. 把原始输入编译成稳定知识，而不是堆成资料仓库。
3. 让知识库同时服务 4 件事：个人认知复利、内容创作、AI 解决方案咨询、企业 AI 培训交付。
4. 让 ChatGPT、Codex、Claude Code、Trae 等 Agent 都能按同一套规则写入和维护知识库。

底层借鉴：

- LLM Wiki 思想：原始资料只读，结构化 Wiki 由 LLM 维护。
- Personal-OS 思想：日常、项目、内容、交付、复盘统一进入一个操作系统。
- 专题研究库思想：重要主题必须有 MOC 入口页、双链路径、原子笔记和可输出资产。

---

## 1. 总体架构

推荐知识库目录：

```text
00-Home/
01-Inbox-Raw/
10-Timeline/
20-Wiki/
30-MOC/
40-Projects/
50-Workflows/
60-Content-Bank/
70-Training-Delivery/
80-Archives/
90-System/
```

### 1.1 各层职责

| 目录 | 定位 | 写入原则 |
|---|---|---|
| `00-Home/` | 总入口、当前工作现场、Personal-OS 首页 | 少量核心导航页 |
| `01-Inbox-Raw/` | 原始输入层 | 只追加，不重写 |
| `10-Timeline/` | Daily / Weekly / Monthly 时间线 | 保留阶段轨迹 |
| `20-Wiki/` | 稳定知识层 | LLM 编译、可复用、可溯源 |
| `30-MOC/` | 主题入口层 | 组织知识路径，不堆资料 |
| `40-Projects/` | 当前项目层 | 有目标、有状态、有下一步 |
| `50-Workflows/` | 工作流与提示词层 | 可重复调用的方法 |
| `60-Content-Bank/` | 内容资产层 | 公众号、小红书、博客、随笔、选题 |
| `70-Training-Delivery/` | 商业交付层 | 企业 AI 培训、咨询、PPT、Demo、课程材料 |
| `80-Archives/` | 归档层 | 旧结构、废弃方向、历史版本 |
| `90-System/` | 系统规则层 | Schema、AGENTS、index、log、lint 报告 |

### 1.2 核心生产链路

```text
原始输入
→ Daily Note
→ Wiki 稳定知识
→ MOC 主题路径
→ 内容选题
→ 公众号 / 小红书 / 博客
→ 企业 AI 培训材料
→ 咨询方案 / 产品化交付
→ Weekly / Monthly 反向复盘
```

判断一条输入有没有价值，不看它是否“完整”，而看它能否进入这条链路中的某一环。

---

## 2. 三个基础动作：Ingest / Query / Lint

### 2.1 Ingest：输入入库

当用户说以下类似指令时，启动 Ingest：

- “记录到知识库”
- “写入 Obsidian”
- “同步到 GitHub”
- “今天这些整理入库”
- “把这段对话沉淀成笔记”
- “这个可以作为素材/选题/培训材料”

执行顺序：

```text
1. 判断输入类型
2. 保存原始输入到 01-Inbox-Raw/
3. 更新当天 Daily Note
4. 判断是否需要更新 20-Wiki/
5. 判断是否需要更新 30-MOC/
6. 判断是否可进入 60-Content-Bank/
7. 判断是否可进入 70-Training-Delivery/
8. 更新 20-Wiki/log.md 或 90-System/changelog.md
```

### 2.2 Query：从知识库提取输出

当用户要生成文章、方案、课程、复盘、PPT 大纲、咨询材料时，启动 Query。

执行顺序：

```text
1. 先读相关 MOC
2. 再读相关 Wiki 页面
3. 再读 Content Bank 或 Training Delivery
4. 生成目标产物
5. 判断新产物是否反向更新知识库
```

优先路径示例：

- 写企业 AI 培训文章：`30-MOC/企业 AI 培训.md` → `20-Wiki/concepts/` → `20-Wiki/cases/` → `60-Content-Bank/公众号/`
- 写小红书：`30-MOC/内容创作.md` → `60-Content-Bank/小红书/模板/` → `60-Content-Bank/选题库/`
- 做培训材料：`30-MOC/企业 AI 培训.md` → `70-Training-Delivery/课程大纲/` → `70-Training-Delivery/Demo案例/`

### 2.3 Lint：知识库健康检查

当用户说“检查知识库”“整理目录”“周复盘”“知识库分层沉淀”时，启动 Lint。

每周至少检查：

1. 哪些 Daily Note 没有沉淀？
2. 哪些页面是孤立页面？
3. 哪些页面重复或应该合并？
4. 哪些旧方向应该归档？
5. 哪些选题可以变成内容？
6. 哪些知识可以变成企业 AI 培训材料？
7. 哪些页面缺少双链？
8. 哪些页面缺少来源？
9. 哪些 MOC 没有更新？
10. 哪些项目没有下一步动作？

Lint 输出：

- `10-Timeline/Weekly/YYYY-MM-DD-Weekly-Review.md`
- 更新 `20-Wiki/index.md`
- 更新重点 MOC
- 更新 `60-Content-Bank/选题库/`
- 更新 `70-Training-Delivery/`
- 更新 `20-Wiki/log.md` 或 `90-System/changelog.md`

---

## 3. 输入类型判定规则

### 3.1 聊天 / 灵感 / 随手想法

默认写入：

```text
01-Inbox-Raw/chats/YYYY-MM-DD_主题.md
10-Timeline/Daily/YYYY-MM-DD.md
```

如果有长期价值，再写入：

```text
20-Wiki/concepts/
20-Wiki/overviews/
30-MOC/
50-Workflows/
60-Content-Bank/选题库/
70-Training-Delivery/
```

处理原则：

- 原话和判断分开。
- 不把一时情绪直接写成长期结论。
- 能沉淀为方法、选题、案例、行动的内容才进入 Wiki 或资产库。

### 3.2 文章 / 播客 / 视频 / 外部链接

默认写入：

```text
01-Inbox-Raw/articles/
01-Inbox-Raw/podcasts/
01-Inbox-Raw/videos/
20-Wiki/sources/
```

Source Summary 模板：

```markdown
---
type: source
source_type: article | podcast | video | repo | report
created: YYYY-MM-DD
updated: YYYY-MM-DD
source_url:
tags: []
related_moc: []
---

# 来源标题

## 一句话摘要

## 核心观点

## 对 Jeffery 的价值
- 内容选题：
- 企业 AI 培训：
- 咨询机会：
- 工具/工作流：

## 可沉淀页面
- [[概念页]]
- [[案例页]]
- [[选题页]]

## 原始来源

```

### 3.3 工具实验 / GitHub 项目 / Codex 工作现场

默认写入：

```text
01-Inbox-Raw/tools/
40-Projects/
50-Workflows/
20-Wiki/entities/
20-Wiki/comparisons/
```

必须回答：

1. 这个工具解决什么问题？
2. 它适合 Jeffery 当前哪个主线？
3. 它是否能变成公众号/小红书内容？
4. 它是否能变成企业 AI 培训案例？
5. 它是否要进入长期工具链？

### 3.4 内容创作素材

默认写入：

```text
60-Content-Bank/选题库/
60-Content-Bank/公众号/
60-Content-Bank/小红书/
60-Content-Bank/博客/
60-Content-Bank/随笔/
```

内容素材必须标注：

```yaml
type: content_idea
channel: 公众号 | 小红书 | 博客 | 随笔 | 视频
status: idea | draft | published | archived
source:
related_moc:
created:
updated:
```

### 3.5 企业 AI 培训 / 咨询素材

默认写入：

```text
70-Training-Delivery/企业AI培训/
70-Training-Delivery/课程大纲/
70-Training-Delivery/PPT素材/
70-Training-Delivery/Demo案例/
70-Training-Delivery/练习题/
70-Training-Delivery/讲解词/
70-Training-Delivery/客户FAQ/
70-Training-Delivery/报价与交付边界/
```

培训材料必须标注：

```yaml
type: training_asset
asset_type: outline | slide | demo | exercise | script | faq | pricing
status: seed | draft | usable | delivered | archived
related_moc: [企业 AI 培训]
created:
updated:
```

---

## 4. Daily / Weekly / Monthly 写入规范

### 4.1 Daily Note 模板

路径：

```text
10-Timeline/Daily/YYYY-MM-DD.md
```

模板：

```markdown
# YYYY-MM-DD Daily Note

## 今日事实
- 

## 今日输入
- 

## 今日思考
- 

## 可沉淀知识
- 概念：
- 案例：
- 选题：
- 工作流：
- 培训素材：

## 今日行动
- 

## 需要更新的页面
- [[企业 AI 培训]]
- [[AI 工具链]]
- [[内容创作]]
- [[个人知识库]]

## 明日推进
- 
```

### 4.2 Weekly Review 模板

路径：

```text
10-Timeline/Weekly/YYYY-MM-DD-Weekly-Review.md
```

模板：

```markdown
# YYYY-MM-DD Weekly Review

## 本周主线

## 本周重要输入

## 本周沉淀的 Wiki 页面

## 本周新增内容选题

## 本周新增培训/咨询素材

## 本周工具实验

## 本周卡点

## 下周行动

## 需要归档/暂停/合并的方向
```

### 4.3 Monthly Strategy Review 模板

路径：

```text
10-Timeline/Monthly/YYYY-MM-Monthly-Strategy-Review.md
```

模板：

```markdown
# YYYY-MM Monthly Strategy Review

## 本月事业主线判断

## 哪些方向继续

## 哪些方向暂停

## 哪些方向合并

## 哪些方向放弃

## 内容增长情况

## 企业 AI 培训 / 咨询机会

## 能力补课

## 下月关键动作
```

---

## 5. Wiki 页面类型与模板

### 5.1 Concept Page

路径：

```text
20-Wiki/concepts/概念名.md
```

模板：

```markdown
---
type: concept
status: evergreen
created:
updated:
tags: []
source: []
related_moc: []
---

# 概念名

## 一句话定义

## 通俗解释

## 它解决什么问题

## 典型场景

## 常见误区

## 和其他概念的关系
- [[相关概念1]]
- [[相关概念2]]

## 对 Jeffery 的价值
- 内容选题：
- 培训价值：
- 咨询价值：

## 参考来源
- 
```

### 5.2 Entity Page

路径：

```text
20-Wiki/entities/实体名.md
```

适用对象：工具、公司、项目、账号、人物、平台。

```markdown
---
type: entity
entity_type: tool | company | project | account | person | platform
created:
updated:
tags: []
source: []
related_moc: []
---

# 实体名

## 它是什么

## 核心能力 / 特征

## 适合场景

## 局限

## 对 Jeffery 的价值

## 相关页面
- 
```

### 5.3 Comparison Page

路径：

```text
20-Wiki/comparisons/A-vs-B.md
```

```markdown
---
type: comparison
created:
updated:
tags: []
source: []
related_moc: []
---

# A vs B

## 一句话结论

## 对比表

## 分场景选择

## 对 Jeffery 的使用建议

## 相关页面
- 
```

### 5.4 Overview Page

路径：

```text
20-Wiki/overviews/主题综述.md
```

```markdown
---
type: overview
created:
updated:
tags: []
source: []
related_moc: []
---

# 主题综述

## 当前结论

## 背景

## 核心问题

## 关键概念

## 关键案例

## 趋势判断

## 对 Jeffery 的行动建议

## 相关页面
- 
```

### 5.5 Case Page

路径：

```text
20-Wiki/cases/案例名.md
```

```markdown
---
type: case
created:
updated:
tags: []
source: []
related_moc: []
---

# 案例名

## 背景

## 痛点

## 解决方案

## 工具/流程

## 效果

## 可复用模板

## 可输出内容
- 公众号：
- 小红书：
- 培训：

## 相关页面
- 
```

---

## 6. MOC 主题入口规范

MOC 不是文件列表，而是主题路径。

优先维护这些 MOC：

```text
30-MOC/企业 AI 培训.md
30-MOC/AI 工具链.md
30-MOC/个人知识库.md
30-MOC/内容创作.md
30-MOC/AI 创业探索.md
30-MOC/数据仓库与企业 AI.md
30-MOC/个人成长与认知.md
```

### 6.1 MOC 模板

```markdown
# 主题名

## 这个主题解决什么问题

## 从这里开始
- [[入门页面1]]
- [[入门页面2]]

## 基础认知路径
- 

## 场景/案例路径
- 

## 工具/方法路径
- 

## 内容输出路径
- 

## 商业化/交付路径
- 

## 当前关键问题
- 

## 下一步行动
- 
```

### 6.2 专题研究库九维框架

对重点主题，按 9 个维度组织：

```text
01-基础概念
02-真实痛点
03-工具与方法
04-案例与场景
05-竞品与市场
06-商业化路径
07-内容选题
08-交付材料
09-人物账号与事件
```

这 9 个维度可以体现为文件夹，也可以体现在 MOC 的章节中。优先使用 MOC 章节组织，不必过早创建大量空目录。

---

## 7. Jeffery 当前优先主线

写入知识库时，优先判断内容是否服务这些主线：

1. 企业 AI 培训
2. AI 解决方案咨询
3. AI 工具链实践：ChatGPT、Codex、Claude Code、Trae、cc-switch、Obsidian、GitHub
4. 个人知识库 / Personal-OS
5. 内容创作：公众号、小红书、博客、随笔
6. AI 创业探索：真实痛点、工作流 Demo、产品化服务
7. 数据仓库与企业 AI 结合
8. 个人成长与认知复盘

如果内容不能服务任何主线，但有生活、人情味、随笔价值，可放入：

```text
60-Content-Bank/随笔/
10-Timeline/Daily/
```

---

## 8. 双链与索引规则

### 8.1 每篇稳定页面至少连接 3 类对象

1. 连接到一个 MOC：如 `[[企业 AI 培训]]`
2. 连接到一个相关概念/案例/工具：如 `[[RAG 是什么]]`
3. 连接到一个输出资产或行动：如 `[[小红书企业AI选题库]]`

### 8.2 必须维护的索引

```text
00-Home/知识库总入口.md
20-Wiki/index.md
20-Wiki/log.md
90-System/changelog.md
```

### 8.3 log 写法

每次重要写入后追加：

```markdown
## YYYY-MM-DD

### 新增
- 

### 更新
- 

### 归档
- 

### 说明
- 
```

---

## 9. GitHub / Obsidian 写入规则

### 9.1 写入前

1. 先判断目标仓库是否为知识库仓库，而不是 skill 仓库。
2. 如果用户明确指定仓库，以用户指定为准。
3. 如果没有指定，优先使用 Jeffery 的 Obsidian/GitHub 主知识库。
4. 大规模迁移前必须先给出变更计划。
5. 小规模新增/更新可以直接执行。

### 9.2 写入时

1. 不覆盖原始输入。
2. 不删除旧内容，除非用户明确要求。
3. 迁移旧内容时，优先保留迁移提示或归档说明。
4. 新页面必须有清晰标题、类型、来源、相关 MOC。
5. 更新内容资产时，标注渠道和状态。
6. 更新培训材料时，标注适用课程、状态和用途。

### 9.3 写入后

必须说明：

1. 更新了哪些文件。
2. 每个文件的用途。
3. 是否还有未完成项。
4. 后续建议的下一步。

---

## 10. 反模式

不要这样做：

1. 不要把所有内容直接塞进一个 Daily Note。
2. 不要把原始输入和稳定知识混在一起。
3. 不要创建没有 MOC 入口的孤立页面。
4. 不要为了目录整齐，一次性创建大量空目录。
5. 不要把未验证信息写成确定事实。
6. 不要把个人生活随笔直接放进商业交付目录。
7. 不要把公众号/小红书草稿放进 Wiki 概念层。
8. 不要把企业 AI 培训材料和普通内容选题混在一起。
9. 不要重复写已有页面，优先更新和双链。
10. 不要在没有来源的情况下虚构案例、数据、引用。

---

## 11. 最小落地文件清单

如果知识库还没有新架构，先创建这 10 个骨架文件：

```text
00-Home/知识库总入口.md
00-Home/Jeffery Personal-OS.md
90-System/Jeffery-Knowledge-Schema.md
20-Wiki/index.md
20-Wiki/log.md
30-MOC/企业 AI 培训.md
30-MOC/AI 工具链.md
30-MOC/内容创作.md
50-Workflows/Daily-Ingest 工作流.md
50-Workflows/Weekly-Lint 工作流.md
```

不要先做全库搬家。先让新骨架跑起来，再逐步迁移旧内容。

---

## 12. 默认执行策略

当用户说“把今天内容写入知识库”时，默认执行：

```text
1. 生成或更新当天 Daily Note
2. 抽取可沉淀知识
3. 更新相关 MOC
4. 更新选题库
5. 更新企业 AI 培训材料库（如相关）
6. 更新 log
```

当用户说“把这个做成知识库笔记”时，默认执行：

```text
1. 判断它是 source / concept / entity / comparison / overview / case
2. 写入 20-Wiki 对应目录
3. 添加 related_moc
4. 添加 source
5. 添加相关双链
6. 更新 index/log
```

当用户说“这个可以作为公众号/小红书选题”时，默认执行：

```text
1. 写入 60-Content-Bank/选题库/
2. 标注渠道、角度、目标读者、状态
3. 关联相关 Wiki 页面和 MOC
4. 如能用于企业 AI 培训，同步添加到 70-Training-Delivery/素材池
```

当用户说“这个可以作为企业 AI 培训素材”时，默认执行：

```text
1. 写入 70-Training-Delivery/对应目录
2. 判断是课程大纲、Demo、练习题、讲解词、FAQ 还是案例
3. 关联 30-MOC/企业 AI 培训.md
4. 关联相关 Wiki 概念页
5. 更新培训素材索引
```

---

## 13. 相关 Skill 协作

本 Skill 负责知识库写入与维护。其他 Skill 的输出应按本 Skill 规则入库：

- `wechat-article-ingest`：公众号文章采集后，先进入 `01-Inbox-Raw/articles/`，再生成 `20-Wiki/sources/`。
- `xiaohongshu-ingest`：小红书内容采集后，优先进入 `60-Content-Bank/小红书/` 和选题库。
- `podcast-transcribe`：播客转录后，先进入 `01-Inbox-Raw/podcasts/`，再做 source summary。
- `content-enrich`：负责摘要、要点、标签增强，但不能替代 Wiki 编译。
- `industry-intelligence-radar`：每日情报进入 Daily Note、选题库和相关 MOC。
- `learning-notes-automation`：学习内容进入 `20-Wiki/concepts/`、`20-Wiki/overviews/` 和复习材料。

---

## 14. 一句话原则

**原始输入不丢失，稳定知识可复利，主题资产可输出，商业材料可交付。**

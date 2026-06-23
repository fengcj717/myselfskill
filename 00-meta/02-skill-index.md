# Skill Index

## 说明

这是 `myselfskill` 的总索引，用于让 ChatGPT、Codex、Claude Code 在遇到复杂任务时快速判断应该调用哪个 Skill。

本文件不负责具体执行，只负责索引、标签、触发词和适用场景。

## 使用顺序

复杂任务先调用：

1. `00-meta/00-skill-router/SKILL.md`
2. 再根据本索引匹配具体 Skill
3. 如果没有命中，按 Skill Router 规则检索个人知识库和开源 Skill

## Meta Skills

| Skill | 路径 | 作用 | 触发词 |
|---|---|---|---|
| Skill Router | `00-meta/00-skill-router/SKILL.md` | 复杂任务入口调度，先检索已有 Skill，再执行任务 | 复杂问题、skill、按之前流程、沉淀、GitHub、Obsidian、工作流 |
| Skill 写作规范 | `00-meta/01-skill-writing-standard.md` | 规范以后所有 Skill 的写法 | 新增 Skill、更新 Skill、写 Skill、规范 Skill |
| Skill Index | `00-meta/02-skill-index.md` | 维护 Skill 目录和触发词 | skill 索引、有哪些 skill、查找 skill |
| 开源 Skill 来源白名单 | `00-meta/03-open-source-skill-sources.md` | 管理可信开源 Skill 来源和安全边界 | 开源 skill、GitHub skill、外部 skill、白名单 |

## 已有业务 Skill

| Skill | 路径 | 作用 | 触发词 |
|---|---|---|---|
| 知识库管理 | `knowledge-base-management/SKILL.md` | 管理 Obsidian / GitHub 知识库结构、素材入库、健康检查 | 知识库、Obsidian、GitHub、入库、整理、归档、沉淀 |

## 待补充 Skill 建议

下面是根据 Jeffery 当前长期方向建议补齐的 Skill。

### 内容生产类

| 建议 Skill | 建议路径 | 用途 |
|---|---|---|
| 公众号文章生产 | `content-creation/wechat-article-writing/SKILL.md` | 生成公众号文章、标题、结构、排版和发布前质检 |
| 小红书企业 AI 培训内容 | `content-creation/xiaohongshu-enterprise-ai/SKILL.md` | 生成小红书选题、图文、短视频脚本、主页内容矩阵 |
| 发布前质检 | `content-creation/content-quality-check/SKILL.md` | 发布公众号、小红书、博客前进行结构、表达、节奏、转化检查 |
| 文章深度阅读训练卡 | `content-creation/deep-reading-card/SKILL.md` | 对文章做概念图谱、核心论点、问题链、应用练习 |

### 创业和产品化类

| 建议 Skill | 建议路径 | 用途 |
|---|---|---|
| AI 创业机会分析 | `startup-analysis/ai-opportunity-analysis/SKILL.md` | 分析真实痛点、产品化切口、验证路径、交付方式 |
| 企业 AI 培训产品化 | `enterprise-ai-training/training-productization/SKILL.md` | 设计企业 AI 培训课程、交付材料、商单承接流程 |
| 真实痛点观察库 | `startup-analysis/pain-point-observation/SKILL.md` | 记录行业、岗位、场景、痛点、替代方案、付费意愿 |

### 知识库和工作流类

| 建议 Skill | 建议路径 | 用途 |
|---|---|---|
| Obsidian/GitHub 写回 | `github-obsidian-workflow/writeback/SKILL.md` | 把对话、素材、文章、行动计划写回知识库 |
| 每日复盘整理 | `personal-os/daily-review/SKILL.md` | 将当天对话、行动、想法整理成复盘笔记 |
| Codex/ChatGPT 上下文桥接 | `github-obsidian-workflow/codex-chatgpt-bridge/SKILL.md` | 管理 ChatGPT、Codex、Claude Code 的上下文分工 |

## 检索关键词建议

当任务不明确时，优先用以下关键词在仓库内检索：

```text
skill
SKILL.md
小红书
公众号
内容质检
企业 AI
AI 培训
创业机会
痛点观察
知识库
Obsidian
GitHub
Codex
ChatGPT
复盘
深度阅读
```

## 维护规则

1. 每新增一个 Skill，必须更新本索引。
2. 每个 Skill 必须有清晰触发词。
3. 索引只写摘要，不复制完整流程。
4. 废弃 Skill 不直接删除，先标记为“已废弃”并说明原因。
5. 开源 Skill 不直接进入业务索引，必须先本地化改写后再登记。

## 更新记录

- 2026-06-23：创建初版，加入 Skill Router、写作规范、开源来源白名单和知识库管理 Skill。

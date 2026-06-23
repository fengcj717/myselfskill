# Jeffery's Myself Skills

这是 Jeffery 的个人 Skill 工作台，用来沉淀 ChatGPT、Codex、Claude Code 等 AI 工具可复用的工作流、Prompt、SOP 和任务执行规范。

这个仓库不是普通知识库，也不是单纯 Prompt 收藏夹。

它的目标是：

> 遇到复杂问题时，先检索已有 Skill，再执行任务，最后把新的经验反向沉淀回来。

## 仓库定位

`myselfskill` 主要放“可重复执行的方法”。

适合放进这里的内容：

- 稳定工作流
- 复杂任务 SOP
- 可复用 Prompt
- 发布前质检流程
- 知识库写回流程
- 企业 AI 培训交付流程
- 小红书 / 公众号 / 博客内容生产流程
- AI 创业机会分析框架
- Codex / ChatGPT / Claude Code 协作规则

不适合放进这里的内容：

- 单篇文章摘录
- 临时想法
- 普通素材
- 未验证案例
- 日记原文
- 只用于阅读、不用于执行的知识笔记

这些更适合进入 `aiknow-vault`。

## 核心使用方式

以后遇到复杂任务，默认遵循：

```text
复杂问题
↓
调用 Skill Router
↓
先检索 myselfskill
↓
没有则检索 aiknow-vault / codex-context-bridge
↓
再参考可信开源 Skill
↓
必要时 GitHub 全局搜索
↓
提取方法，不直接执行不可信代码
↓
执行任务
↓
把新经验沉淀回 Skill
```

## 入口 Skill

优先读取：

```text
00-meta/00-skill-router/SKILL.md
```

它负责判断：

- 当前任务是否复杂；
- 应该检索哪个 Skill；
- 是否需要参考个人知识库；
- 是否需要参考开源 Skill；
- 是否值得新增或更新 Skill。

## 目录结构

```text
00-meta/
  00-skill-router/
    SKILL.md
  01-skill-writing-standard.md
  02-skill-index.md
  03-open-source-skill-sources.md

knowledge-base-management/
  SKILL.md
```

后续建议逐步扩展：

```text
content-creation/
  wechat-article-writing/
  xiaohongshu-enterprise-ai/
  content-quality-check/
  deep-reading-card/

enterprise-ai-training/
  training-productization/

startup-analysis/
  ai-opportunity-analysis/
  pain-point-observation/

github-obsidian-workflow/
  writeback/
  codex-chatgpt-bridge/

personal-os/
  daily-review/
```

## 当前已有 Skill

| Skill | 路径 | 用途 |
|---|---|---|
| Skill Router | `00-meta/00-skill-router/SKILL.md` | 复杂任务入口调度，先检索已有 Skill 再执行 |
| Skill 写作规范 | `00-meta/01-skill-writing-standard.md` | 规范以后所有 Skill 的写法 |
| Skill Index | `00-meta/02-skill-index.md` | 维护所有 Skill 的目录、触发词和适用场景 |
| 开源 Skill 来源白名单 | `00-meta/03-open-source-skill-sources.md` | 管理可信开源 Skill 来源和安全边界 |
| 知识库管理 | `knowledge-base-management/SKILL.md` | 管理 Obsidian / GitHub 知识库入库、整理和健康检查 |

## 如何在对话中使用

你可以直接对 ChatGPT / Codex / Claude Code 说：

```text
这是一个复杂任务，先按 myselfskill 的 Skill Router 检索有没有对应 Skill。
```

或者：

```text
先查 fengcj717/myselfskill 里有没有可用 Skill，如果没有，再查 aiknow-vault 和可信开源 Skill。
```

或者：

```text
按我的 Skill Router 流程处理这个问题，执行完后判断是否需要新增或更新 Skill。
```

## 开源 Skill 的使用原则

开源 Skill 可以参考，但不能直接信任。

默认规则：

1. 先查自己的 Skill。
2. 再查自己的知识库。
3. 再查可信开源 Skill 白名单。
4. 最后才 GitHub 全局搜索。
5. 开源 Skill 只提取方法、结构、Prompt、SOP。
6. 不直接运行脚本、不直接安装依赖、不粘贴密钥、不执行不明命令。
7. 有价值的开源方法，必须改写成 Jeffery 版本后再进入本仓库。

详见：

```text
00-meta/03-open-source-skill-sources.md
```

## Skill 和知识库的分工

### `myselfskill`

保存“怎么做”。

例子：

- 怎么写公众号文章；
- 怎么做发布前质检；
- 怎么整理小红书选题；
- 怎么把对话写回 Obsidian；
- 怎么分析一个 AI 创业机会。

### `aiknow-vault`

保存“知道了什么”。

例子：

- 文章摘录；
- 案例素材；
- 日记复盘；
- 行业观察；
- 个人思考；
- 项目过程记录。

## 新增 Skill 的标准

一个内容值得变成 Skill，必须满足至少 3 条：

- 高频出现；
- 有明确触发条件；
- 有稳定执行步骤；
- 能减少下次沟通成本；
- 能形成标准输出；
- 属于 Jeffery 的长期主线；
- 能被 ChatGPT / Codex / Claude Code 复用。

写法参考：

```text
00-meta/01-skill-writing-standard.md
```

## 当前优先补齐的 Skill

下一阶段建议优先补齐：

1. `content-creation/content-quality-check/SKILL.md`
2. `content-creation/xiaohongshu-enterprise-ai/SKILL.md`
3. `content-creation/wechat-article-writing/SKILL.md`
4. `enterprise-ai-training/training-productization/SKILL.md`
5. `startup-analysis/ai-opportunity-analysis/SKILL.md`
6. `github-obsidian-workflow/writeback/SKILL.md`
7. `personal-os/daily-review/SKILL.md`

这些对应 Jeffery 当前最重要的长期方向：企业 AI 培训、小红书获客、公众号沉淀、知识库写回、AI 创业机会验证。

## 工作原则

复杂问题不要凭空开始。

先找已有沉淀，再执行。

执行后再反向补充 Skill。

最终目标不是让 AI 每次都重新思考，而是让 AI 逐步复用 Jeffery 自己的方法库。

## 更新记录

- 2026-06-23：将仓库 README 更新为 Jeffery 个人 Skill 工作台说明；新增 Skill Router、写作规范、索引和开源 Skill 来源白名单。

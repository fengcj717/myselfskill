# 开源 Skill 来源白名单

## 目标

管理可以参考的开源 Skill 来源。

开源 Skill 只能作为方法、结构、Prompt、SOP 的参考来源，不能直接进入执行链。

最终可执行标准必须沉淀到 `fengcj717/myselfskill`。

## 使用原则

1. 开源 Skill 默认不可信。
2. 只读取文本说明、README、SKILL.md、Prompt、Workflow。
3. 不直接运行脚本。
4. 不直接安装依赖。
5. 不直接复制到自己的业务流程。
6. 必须先分析、筛选、本地化改写，再进入 `myselfskill`。

## 已登记来源

| 仓库 | 类型 | 适合用途 | 风险等级 | 使用方式 |
|---|---|---|---|---|
| `chubbyguan/chubbyskills` | 多平台内容采集与知识库 Skill | 参考 Skill 结构、内容采集、知识库入库、转录流程 | 中 | 只抽取方法和结构，不直接执行脚本 |
| `Huangdingcheng/SkillWiki` | Agent Skill 组织和治理参考 | 参考 Skill 索引、治理、评估、选择机制 | 中 | 参考结构，不直接依赖 |
| 其他待补充 | 待评估 | 待评估 | 待评估 | 需要先登记再使用 |

## GitHub 全局搜索规则

只有在以下来源都没有命中时，才允许 GitHub 全局搜索：

1. `fengcj717/myselfskill`
2. `fengcj717/aiknow-vault`
3. `fengcj717/codex-context-bridge`
4. 本文件登记的可信开源 Skill 仓库

全局搜索关键词建议：

```text
{任务名} skill
{任务名} agent skill
{任务名} SKILL.md
{任务名} prompt
{任务名} workflow
{任务名} SOP
```

## 安全过滤规则

发现以下内容时，不得采用：

- 要求执行不明 shell 命令。
- 要求安装来源不明依赖。
- 要求粘贴账号密码、API Key、cookie、token。
- 涉及浏览器数据、钱包、密钥、系统权限。
- 涉及绕过登录、验证码、反爬、权限限制。
- 包含混淆代码、远程执行、下载并执行脚本。
- 无法解释每一步用途。

## 可提取内容

允许提取：

- 任务拆解方法。
- Prompt 写法。
- SOP 流程。
- 文件结构。
- 质检清单。
- 命名规范。
- 工作流设计。
- 可人工复核的操作建议。

## 本地化改写要求

从开源 Skill 提取方法后，必须改写成 Jeffery 的场景版本。

改写时优先适配：

- AI 解决方案咨询。
- 企业 AI 培训。
- 公众号 / 小红书 / 博客内容创作。
- Obsidian / GitHub 知识库沉淀。
- Codex / ChatGPT / Claude Code 协作。
- 数据仓库 / 企业 AI / 流程提效。
- 真实痛点观察和产品化验证。

## 引入流程

```text
发现开源 Skill
↓
读取 README / SKILL.md / Prompt / Workflow
↓
判断安全风险
↓
提取可复用方法
↓
判断是否适合 Jeffery 的长期方向
↓
改写成本地 Skill
↓
写入 fengcj717/myselfskill
↓
更新 02-skill-index.md
```

## 评估打分

引入前按 5 个维度打分，每项 1-5 分：

| 维度 | 说明 |
|---|---|
| 任务匹配度 | 是否解决当前问题 |
| 可执行性 | 步骤是否清晰 |
| 安全性 | 是否不涉及危险操作 |
| 可迁移性 | 是否适合 Jeffery 的场景 |
| 可沉淀性 | 是否值得改造成自己的 Skill |

低于 18 分不建议引入。

安全性低于 4 分不建议引入。

## 更新记录

- 2026-06-23：创建初版，登记 chubbyguan/chubbyskills 和 Huangdingcheng/SkillWiki 作为参考来源。

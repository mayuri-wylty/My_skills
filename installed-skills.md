# Codex 已安装技能清单

更新时间：2026-08-14

本清单记录本次对话中安装到本机 Codex 的 29 个技能。系统预装目录 `C:\Users\20323\.codex\skills\.system` 不计入本表。

## 模式说明

- **自动触发**：技能未设置 `policy.allow_implicit_invocation: false`。当用户请求符合技能描述的任务时，Codex 可以自动选择它。
- **手动启用**：技能设置了 `policy.allow_implicit_invocation: false`，需要用户显式调用。
- 自动技能仍可显式调用，例如 `$skill-name`；“自动”表示允许隐式触发，并不禁止手动调用。

本次安装的 28 个既有技能为 **自动触发**；新增的 `agentic-dev-docs` 为 **手动启用**。

安装根目录：`C:\Users\20323\.codex\skills`

## Superpowers

来源：[obra/superpowers](https://github.com/obra/superpowers)

| 技能 | 模式 | 自动触发条件 / 用途 | 本地目录 |
|---|---|---|---|
| `brainstorming` | 自动 | 创建设计、功能、组件或修改行为前，先澄清需求和设计。 | `C:\Users\20323\.codex\skills\brainstorming` |
| `dispatching-parallel-agents` | 自动 | 存在两个或以上可并行、互不共享状态的独立任务时。 | `C:\Users\20323\.codex\skills\dispatching-parallel-agents` |
| `executing-plans` | 自动 | 已有书面实现计划，需要分阶段执行并设置评审节点时。 | `C:\Users\20323\.codex\skills\executing-plans` |
| `finishing-a-development-branch` | 自动 | 实现完成、测试通过，需要决定如何合并或交付分支时。 | `C:\Users\20323\.codex\skills\finishing-a-development-branch` |
| `receiving-code-review` | 自动 | 收到代码评审意见，准备判断和实现建议前。 | `C:\Users\20323\.codex\skills\receiving-code-review` |
| `requesting-code-review` | 自动 | 完成任务、重大功能或合并前，需要请求代码评审时。 | `C:\Users\20323\.codex\skills\requesting-code-review` |
| `subagent-driven-development` | 自动 | 按计划执行多个独立实现任务，并为任务派生实现 agent 时。 | `C:\Users\20323\.codex\skills\subagent-driven-development` |
| `systematic-debugging` | 自动 | 遇到 bug、测试失败、构建失败或其他异常行为，在提出修复前。 | `C:\Users\20323\.codex\skills\systematic-debugging` |
| `test-driven-development` | 自动 | 实现功能、修复 bug 或改变行为，准备写实现代码前。 | `C:\Users\20323\.codex\skills\test-driven-development` |
| `using-git-worktrees` | 自动 | 开始需要隔离的功能开发，或执行实现计划前。 | `C:\Users\20323\.codex\skills\using-git-worktrees` |
| `using-superpowers` | 自动 | 每次新对话开始时，负责识别并调用适用技能。 | `C:\Users\20323\.codex\skills\using-superpowers` |
| `verification-before-completion` | 自动 | 准备声称完成、修复成功或测试通过前。 | `C:\Users\20323\.codex\skills\verification-before-completion` |
| `writing-plans` | 自动 | 已有规格或多步骤需求，准备接触代码前。 | `C:\Users\20323\.codex\skills\writing-plans` |
| `writing-skills` | 自动 | 创建、编辑或部署前验证技能时。 | `C:\Users\20323\.codex\skills\writing-skills` |

## 其他已安装技能

| 技能 | 来源 | 模式 | 自动触发条件 / 用途 | 本地目录 |
|---|---|---|---|---|
| `hallmark` | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) | 自动 | 创建新页面、Landing Page、改版页面，或进行设计审计、重设计、截图/URL 设计提取时。 | `C:\Users\20323\.codex\skills\hallmark` |
| `archify` | [tt-a1i/archify](https://github.com/tt-a1i/archify) | 自动 | 需要架构图、工作流、时序图、数据流图、生命周期图，或美化 Mermaid 图时。 | `C:\Users\20323\.codex\skills\archify` |
| `karpathy-guidelines` | [Jing-Fu/karpathy-guidelines-skill](https://github.com/Jing-Fu/karpathy-guidelines-skill) | 自动 | 编写、调试、评审或重构代码，并需要简单方案、明确假设、最小改动和可验证结果时。 | `C:\Users\20323\.codex\skills\karpathy-guidelines` |
| `caveman` | [Radzievskyi/caveman-codex](https://github.com/Radzievskyi/caveman-codex) | 自动 | 用户要求简短、少 token、Caveman mode，或使用 `/caveman` 时。 | `C:\Users\20323\.codex\skills\caveman` |
| `caveman-commit` | [Radzievskyi/caveman-codex](https://github.com/Radzievskyi/caveman-codex) | 自动 | 用户要求提交信息、Conventional Commit，或使用 `/commit`、`/caveman-commit` 时。 | `C:\Users\20323\.codex\skills\caveman-commit` |
| `caveman-review` | [Radzievskyi/caveman-codex](https://github.com/Radzievskyi/caveman-codex) | 自动 | 用户要求代码、PR 或 diff 评审，或使用 `/review`、`/caveman-review` 时。 | `C:\Users\20323\.codex\skills\caveman-review` |
| `caveman-compress` | [Radzievskyi/caveman-codex](https://github.com/Radzievskyi/caveman-codex) | 自动 | 用户要求压缩 prose、项目文档或 memory 文件，或使用 `/caveman-compress` 时。 | `C:\Users\20323\.codex\skills\caveman-compress` |
| `vibehub` | [oil-oil/vibe-hub-skill](https://github.com/oil-oil/vibe-hub-skill) | 自动 | Vibe Coding 任务中识别准确术语、改写模糊需求并补充术语解释时。 | `C:\Users\20323\.codex\skills\vibehub` |

## Matt Pocock 精选技能

来源：[mattpocock/skills](https://github.com/mattpocock/skills)，安装版本为审查时锁定的提交 `8b78b531ab965735c5dc74f6f7a219e1e37326df`。

| 技能 | 模式 | 自动触发条件 / 用途 | 本地目录 |
|---|---|---|---|
| `prototype` | 自动 | 需要用一次性原型验证状态模型、逻辑或 UI 方案时。 | `C:\Users\20323\.codex\skills\prototype` |
| `research` | 自动 | 需要基于一手资料研究主题、官方文档或 API，并将结果写入带引用的 Markdown 时。 | `C:\Users\20323\.codex\skills\research` |
| `domain-modeling` | 自动 | 讨论代码库术语、编辑 `CONTEXT.md` 或记录/编辑 ADR 时。 | `C:\Users\20323\.codex\skills\domain-modeling` |
| `codebase-design` | 自动 | 设计深模块、接口、测试 seam，或改善模块可维护性和 AI 可导航性时。 | `C:\Users\20323\.codex\skills\codebase-design` |
| `resolving-merge-conflicts` | 自动 | 存在进行中的 Git merge 或 rebase 冲突，需要逐个 hunk 解析时。 | `C:\Users\20323\.codex\skills\resolving-merge-conflicts` |
| `wizard` | 自动 | 配置基础设施、凭据、CI secret、第三方后台，或执行需要人工操作的一次性迁移时。 | `C:\Users\20323\.codex\skills\wizard` |

## Agentic Dev Docs

来源：[mayuri-wylty/agentic-dev-docs](https://github.com/mayuri-wylty/agentic-dev-docs)

| 技能 | 模式 | 自动触发条件 / 用途 | 本地目录 |
|---|---|---|---|
| `agentic-dev-docs` | 手动启用 | 仅在用户显式指定 `agentic-dev-docs`、`$agentic-dev-docs` 或要求运行该精确 Skill 时使用；用于生成文档优先的 agentic 软件开发控制文档包。 | `C:\Users\20323\.codex\skills\agentic-dev-docs` |

## 维护说明

- 本文只记录本次对话实际安装的技能，不包含 `.system` 预装技能。
- 技能目录已写入用户级 Codex 技能路径；新建任务或新会话即可使用。
- “自动触发”依赖技能描述和 Codex 元数据匹配。触发条件不满足时，仍可显式调用对应技能。

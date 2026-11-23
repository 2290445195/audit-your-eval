# Audit Your Eval

**Who grades the grader? / 谁来给评分器打分？**

[English](#english) · [简体中文](#简体中文)

## English

An English-language skill for auditing how agents are evaluated. It helps test whether an evaluation measures what it claims, find false accepts and false rejects, and verify fixes with independent evidence. It covers documentation audits, offline scoring, and end-to-end experiments.

### Use with your agent

- **Recommended: install from the command line.** With [Node.js 22.20+](https://nodejs.org/) installed, run this from your project directory. The [Skills CLI](https://skills.sh/docs/cli) detects supported agents and prompts you to choose where to install the skill:

  ```bash
  npx skills add 2290445195/audit-your-eval --skill audit-your-eval
  ```

  Add `-g` to install for your user instead of just the current project.
- **Other Agent Skills-compatible clients.** Install the [`audit-your-eval`](skills/audit-your-eval/) directory using your client's skill installation or discovery mechanism. Ask the agent to use `audit-your-eval` by name. [Agent Skills specification](https://agentskills.io/specification)
- **Any agent that accepts text instructions.** Paste the Markdown body of [`SKILL.md`](skills/audit-your-eval/SKILL.md) into a chat, project instruction field, or system prompt. Then provide your audit request and available evidence. Everything needed to follow the workflow is in that one file.

```text
Use audit-your-eval to audit this agent evaluation. Check whether the grader
can pass a failed task based on the final answer alone. Give a minimal case
family and an independent way to verify each outcome.
```

The skill has no bundled scripts, runtime dependencies, or provider-specific tool requirements. A text-only agent can reconstruct the method and design tests. Running an offline or end-to-end experiment requires access to the relevant grader, evidence, and, for end-to-end tests, an executable agent and environment.

## 简体中文

**Audit Your Eval** 是一个评测 Agent 评测方法的 Skill。它帮助你检验评测是否完备，找出误放和误拒，并用独立证据验证修复。支持方法评测、离线评分实验和端到端实验。

### 使用方式

- **推荐：命令行安装。** 安装 [Node.js 22.20+](https://nodejs.org/) 后，在项目目录运行下面的命令。[Skills CLI](https://skills.sh/docs/cli) 会检测支持的 Agent，并让你选择安装位置：

  ```bash
  npx skills add 2290445195/audit-your-eval --skill audit-your-eval
  ```

  添加 `-g` 可改为安装到用户级目录，而非仅当前项目。
- **其他支持 Agent Skills 的客户端。** 按客户端的安装或发现机制添加 [`audit-your-eval`](skills/audit-your-eval/) 目录，然后按名称调用 `audit-your-eval`。[Agent Skills 规范](https://agentskills.io/specification)
- **接受文本指令的 Agent。** 把 [`SKILL.md`](skills/audit-your-eval/SKILL.md) 的 Markdown 正文粘贴到对话、项目指令或系统提示词中，然后附上审计请求和已有证据。只需这一个文件即可使用。

```text
使用 audit-your-eval 审计这套 Agent 评测。检查评分器仅看最终答复时，
是否会把失败任务判为通过。请给出一组最小对照，以及各案例的独立判据。
```

Skill 无需安装脚本、运行时依赖或特定平台的工具。纯文本 Agent 可以重建评测方法并设计实验。执行离线评分需要可访问的评分器和证据，运行端到端实验还需要可执行的 Agent 和环境。

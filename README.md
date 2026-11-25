# Audit Your Eval

**Who grades the grader? / 谁来给评分器打分？**

[English](#english) · [简体中文](#简体中文)

## English

An English-language skill for auditing how agents are evaluated. It helps test whether an evaluation measures what it claims, find false accepts and false rejects, and verify fixes with independent evidence. It covers documentation audits, offline scoring, and end-to-end experiments.

### Case study and background

The Chinese article explains the audit workflow through a τ-bench reference-replay case. It covers a no-op receiving full database credit after reference actions fail, and a recovery case that exposes the cost of a blanket abstention rule. [Read the article — agent自进化之我的进化是否有点问题](https://blog.csdn.net/Masterki/article/details/171312105)

The article reports paired environment rescoring of 100 frozen trajectories. Pass/fail/abstain counts change from 85/15/0 to 82/12/6, with 94% scoring coverage and unchanged scores on the 94 commonly scored records. These results concern environment scoring. The model judge and official overall score were not recomputed.

### Use with your agent

- **Let your agent install it.** Copy this instruction into an agent that has internet and file access. It will install the skill for the current agent; if it cannot, it should tell you what blocked it rather than claim success:

  ```text
  Install the audit-your-eval skill from
  https://github.com/2290445195/audit-your-eval/tree/main/skills/audit-your-eval
  for the agent we are using in this project. Use the Skills CLI if available;
  otherwise download its SKILL.md from
  https://raw.githubusercontent.com/2290445195/audit-your-eval/main/skills/audit-your-eval/SKILL.md
  and install it in this agent's documented project-level skills directory.
  Check for an existing installation before changing anything. Afterward,
  verify the installed file and tell me its location and how to invoke it.
  ```

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

### 案例与背景文章

文章用 τ-bench 的参考动作回放案例展开这套审计流程，分析参考执行失败后空操作仍获数据库满分的问题，以及一刀切暂缓评分对合法恢复案例的影响。[阅读《agent自进化之我的进化是否有点问题》](https://blog.csdn.net/Masterki/article/details/171312105)

文章报告对同一批 100 条冻结轨迹配对重评，通过／失败／暂缓评分从 85／15／0 变为 82／12／6，评分覆盖率为 94%，两版共同可评分的 94 条记录分数逐条一致。这里的结果仅涉及环境评分，未重跑模型裁判或重算官方总分。

### 使用方式

- **让 Agent 自动安装。** 将下面这段指令复制给支持联网和文件操作的 Agent，它会为当前 Agent 安装 Skill；如果无法完成，应说明受阻原因，而不是声称已安装：

  ```text
  请为当前项目使用的 Agent 安装 audit-your-eval。
  Skill 来源：
  https://github.com/2290445195/audit-your-eval/tree/main/skills/audit-your-eval
  如果可用，请使用 Skills CLI；否则从
  https://raw.githubusercontent.com/2290445195/audit-your-eval/main/skills/audit-your-eval/SKILL.md
  下载 SKILL.md，并安装到该 Agent 文档规定的项目级 skills 目录。
  操作前先检查是否已安装，不要覆盖已有内容。完成后验证文件，并告诉我安装路径和调用方式。
  ```

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


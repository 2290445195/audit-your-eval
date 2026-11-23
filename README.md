# eval for eval

一个中文 Codex Skill，用于审计 Agent 评测方法的有效性、评分盲区以及比较和发布结论。它支持方法审计、离线评分和端到端实验，并给出从假设、最小对照到修复与留出验证的工作流。

## 使用

把 [eval-for-eval](skills/eval-for-eval/) 目录完整复制到 Codex 能发现的项目或个人技能目录，例如项目的 `.agents/skills/`。在 Codex 里输入以下请求，并附上已有的评测材料。

```text
用 $eval-for-eval 审计这套 Agent 评测方法。重点检查只依赖最终答复的评分是否会误放行，给出最小对照和独立判据。
```

只有方法说明时，Skill 会输出方法卡、待验证假设、案例和协议。提供可运行评分器与固定轨迹后，可核对实际误判。需要分析真实 Agent 的行为时，再提供可运行 Agent 和隔离环境。

## 文件

- [SKILL.md](skills/eval-for-eval/SKILL.md) 定义适用范围、证据要求和九段报告格式。
- [假设与案例设计](skills/eval-for-eval/references/audit-design.md) 包含方法卡、假设字段和最小对照示例。
- [实验与归因](skills/eval-for-eval/references/experiments.md) 包含实验协议、运行证据和盲区状态。
- [测量与迭代](skills/eval-for-eval/references/measurement-and-revisions.md) 包含指标口径、修复和留出验证。

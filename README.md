<div align="center">
  <h1>🧬 Micro-Harness</h1>
  <p><strong>A lightweight, self-evolving project harness for AI coding agents</strong></p>
  <p><strong>轻量级、自进化的 AI 编码项目骨架</strong></p>
  <p>Zero dependencies · Pure Markdown · Works with any AI agent</p>
  <p>零依赖 · 纯 Markdown · 任何 AI 智能体都能用</p>
  <br>
</div>

---

## 📖 Story / 来历

> **English:** This project started as a personal experiment. I was using [Trellis](https://github.com/mindfold-ai/Trellis) for my projects — a fantastic harness framework — but I found it too heavy for small, personal tasks like software installation scripts or tiny code projects. I wanted something I could bootstrap in 10 seconds, that any AI agent could read and follow without needing npm or Python.
>
> At the same time, I was fascinated by the concept of **self-evolving skills** — an idea explored in Microsoft's research on AI agent evolution, where agents analyze past experiences and improve their own tools. I thought: what if a project harness could get smarter with every project it runs?
>
> So I stripped Trellis down to its essence (Markdown files an agent can read), added a self-evolution loop, and Micro-Harness was born. It's been battle-tested in my daily workflow — installing CUDA + llama.cpp on remote servers, writing small scripts, tracking deployment steps. Every project taught the templates something new.
>
> This is the public release. It's minimal by design. I hope it helps you keep your AI agents on track, one `.harness/` at a time.
>
> **中文：** 这个项目源于个人实践。我一直在用 [Trellis](https://github.com/mindfold-ai/Trellis) 做项目 —— 一个非常优秀的 Harness 框架 —— 但对于小任务（比如装个软件、写个小脚本）来说太重了。我想要一个 10 秒就能初始化、任何 AI 智能体都能直接读懂、不需要装 npm 或 Python 的东西。
>
> 同时，我对 **技能自进化** 的概念很着迷 —— 微软在 AI Agent 进化研究里探讨过这个方向：智能体分析历史经验，然后改进自己的工具。我想：如果一个项目骨架能越用越聪明，那不是很好吗？
>
> 于是我把 Trellis 精简到本质（Agent 能读的 Markdown 文件），加上了自进化循环，就有了 Micro-Harness。它在我的日常工作流中经过实战检验 —— 在远程服务器上装 CUDA + llama.cpp、写小脚本、跟踪部署步骤。每个项目都让模板学到了新东西。
>
> 这是公开版。它刻意保持极简。希望能让你的 AI 智能体保持方向感，一次一个 `.harness/`。

---

## 🎯 What / 是什么

**English:** Micro-Harness is a **minimal project harness** for AI-assisted development. It provides a structured workflow framework through a simple `.harness/` directory of Markdown files — no npm, no Python scripts, no dependencies.

**The problem it solves:** AI agents have no memory between sessions. Every new conversation starts from scratch. Micro-Harness persists project state, task progress, bugs, and learnings into the project directory itself, so your AI agent always has context.

**The superpower:** It **self-evolves** — after each project, the agent analyzes what went wrong, identifies patterns, and updates the templates to avoid repeating mistakes.

---

**中文：** Micro-Harness 是一个 **极简项目骨架**，专为 AI 辅助开发设计。通过一个 `.harness/` 目录里的 Markdown 文件，提供结构化的工作流框架 —— 不需要 npm、不需要 Python 脚本、零依赖。

**解决的问题：** AI 智能体在会话之间没有记忆。每次新对话都从零开始。Micro-Harness 把项目状态、任务进度、Bug 和经验沉淀到项目目录本身，让 AI 智能体始终有上下文。

**超能力：** 它会 **自进化** —— 每个项目完成后，智能体分析踩过的坑，识别模式，更新模板，避免重复犯错。

---

## ✨ Features / 特性

| English | 中文 |
|:--------|:-----|
| ✅ **Zero dependencies** — Just Markdown, works with any AI agent | ✅ **零依赖** —— 纯 Markdown，任何 AI 智能体都能用 |
| ✅ **6-phase workflow** — Requirements → Planning → Execution → Verification → Wrap-up → Self-Evolution | ✅ **6 阶段工作流** —— 需求→规划→执行→验证→收尾→自进化 |
| ✅ **Safety boundaries** — Retry limits, human intervention triggers | ✅ **安全边界** —— 重试上限、人工介入条件 |
| ✅ **Task tracking** — Simple todo/done format | ✅ **任务追踪** —— 简单的待办/完成格式 |
| ✅ **Restore points** — Checkpoint snapshots for session resumption | ✅ **还原点** —— 断点续传 |
| ✅ **Self-evolving** — Templates get smarter with each project | ✅ **自进化** —— 每个项目让模板更聪明 |
| ✅ **Progressive** — No upfront paperwork, fill as you go | ✅ **渐进式** —— 无需先填表，边做边写 |

---

## 🚀 Quick Start / 快速开始

### Initialize / 初始化

Tell your AI agent / 对你的 AI 智能体说：

> **"Initialize micro-harness for this project"**
>
> **"用 micro-harness 初始化当前项目"**

The agent will create / 智能体会创建：

```
.harness/
├── workflow.md          Workflow definition / 流程定义
├── boundaries.md        Safety rules / 边界规则
├── tasks/current.md     Task tracking / 任务追踪
├── bugs.md              Issue collection / 问题收集
├── checkpoints/         Restore points / 还原点
└── journal.md           Work journal / 工作日志
```

### 6 Phases / 6 个阶段

| Phase | Name | What Happens / 做什么 |
|:----:|:----|:---------------------|
| 1 | 🎯 Requirements / 需求 | Clarify goals, inputs, acceptance criteria / 明确目标 |
| 2 | 📋 Planning / 规划 | Break tasks into actionable steps / 拆解步骤 |
| 3 | ⚡ Execution / 执行 | Execute step by step, update progress / 逐步执行 |
| 4 | ✅ Verification / 验证 | Check results against criteria / 对照验收 |
| 5 | 🏁 Wrap-up / 收尾 | Log, cleanup, summarize / 记录、清理 |
| 6 | 🧬 Self-Evolution / 自进化 | Analyze patterns, improve templates / 反哺技能 |

### Resume / 续接

When you come back to the project, just start a new session and the agent reads `.harness/` to pick up where it left off.

下次回来，新会话的智能体自动读 `.harness/` 接续进度。

---

## 🧬 Self-Evolution / 自进化

**English:** This is what makes Micro-Harness different. After each project completes, the agent:

1. **Collects data** — scans bugs.md, checkpoints/, journal.md
2. **Finds patterns** — recurring issues (2+ times) get codified
3. **Updates templates** — improves workflow.md, boundaries.md etc.
4. **Logs evolution** — records in evolution-log.md

**中文：** 这是 Micro-Harness 的特色。每个项目完成后，智能体会：

1. **收集数据** —— 扫描 bugs.md、checkpoints/、journal.md
2. **发现模式** —— 重复出现 2 次以上的问题被固化
3. **更新模板** —— 改进 workflow.md、boundaries.md 等
4. **记录进化** —— 写入 evolution-log.md

---

## 📋 Comparison / 对比

| Harness | Dependencies | Learning Curve | Best For |
|:--------|:------------:|:--------------:|:---------|
| **Micro-Harness** 🧬 | **None** | **Low** 🟢 | Small projects, personal use / 个人小项目 |
| [Trellis](https://github.com/mindfold-ai/Trellis) | npm + Python | Medium | Teams, long-term projects / 团队长期项目 |
| Superpowers | Platform-specific | Medium-High | Workflow-heavy development |
| OpenSpec | Python | Medium | Spec-first development |

---

## 📄 License / 许可证

MIT — use it, modify it, share it. No restrictions.
MIT 许可证 —— 随意使用、修改、分享。

---

## 🙏 Credits / 致谢

- [Trellis](https://github.com/mindfold-ai/Trellis) — The best agent harness that inspired this project / 本项目灵感的源泉
- Microsoft Research — Self-evolving AI systems research / 自进化 AI 系统研究
- [LINUX DO](https://linux.do) community — Discussion and feedback / 社区的讨论与反馈

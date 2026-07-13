# Micro-Harness — A Lightweight Project Harness for AI Agents

> Inspired by Trellis + Microsoft Skill Self-Evolution theory. Zero dependencies — no npm, no Python scripts. Just Markdown files that any AI agent can read and follow.

> **Core evolution logic**: after each project completes, the AI agent analyzes project data, extracts reusable patterns, and feeds them back into the skill templates. The more you use it, the smarter it gets.

---

## When to Use

- Software installation/deployment procedures
- Small code projects (a few files to dozens of files)
- Experimental projects needing progress tracking
- Any scenario where you want to keep your AI agent on track

## Quick Start

### 1. Initialize a Project

Tell any AI coding agent (Claude Code, Codex, Cursor, Hermes, OpenCode, etc.):

> "Initialize micro-harness for this project"

Or just say: "Initialize .harness in this project following micro-harness"

### 2. Generated Structure

```
.harness/
├── workflow.md        ← Workflow definition (6 phases)
├── boundaries.md      ← Safety rules (retry limits, human intervention)
├── tasks/
│   └── current.md     ← Task tracking (todo/in_progress/done)
├── bugs.md            ← Bug/issue collection
├── checkpoints/       ← Restore points and decision snapshots
└── journal.md         ← Work journal (auto-maintained by agent)
```

### 3. How It Works

The AI agent reads `.harness/workflow.md` to know which phase it's in and what to do next. It updates the files as it progresses through the workflow.

---

## File Reference

### workflow.md — Workflow Definition

6 phases the agent walks through:

| Phase | Name | Goal |
|:----:|:----|:-----|
| 1 | Requirements Clarification 🎯 | Understand what to do, confirm I/O |
| 2 | Planning 📋 | Break down into actionable steps |
| 3 | Execution ⚡ | Execute step by step |
| 4 | Verification ✅ | Check results against acceptance criteria |
| 5 | Wrap-up 🏁 | Log, cleanup, summarize |
| 6 | Self-Evolution 🧬 | Analyze & feed back experience into templates |

### boundaries.md — Safety Boundaries

Prevents infinite loops and unsafe behavior:

- **Retry limit**: 3 attempts per step, then notify user
- **Human intervention triggers**: credential needs, architecture decisions, data deletion risks, persistent failures
- **Agent behavior constraints**: don't delete unrelated files, check boundaries before each action, ask when uncertain

### tasks/current.md — Task Tracking

Simple todo list format:

```markdown
## Todo
- [ ] Step 1: ...
- [ ] Step 2: ...

## In Progress
- [ ] Current step

## Done
- [x] Completed step ✓
```

### bugs.md — Issue Collection

Structured bug reporting with status tracking:

- BUG-001: Timestamp, step, symptom, cause, solution, status
- Status: ✅ Fixed / ⏳ In Progress / ❌ Needs Confirmation

### checkpoints/ — Restore Points

Created before major decisions or when hitting a milestone. The agent reads the latest checkpoint to resume work after a session interruption.

### journal.md — Work Journal

Session-based log recording what was done, problems encountered, next steps, and decisions made.

---

## Self-Evolution Mechanism 🧬

### When Evolution Triggers

After Phase 5 (Wrap-up) completes, the agent automatically enters Phase 6 (Self-Evolution).

### Evolution Process

1. **Collect data** — read bugs.md, checkpoints/, journal.md from the completed project
2. **Pattern recognition** — identify recurring issues (same problem ≥ 2 times), optimization opportunities, boundary gaps
3. **Skill update** — if patterns have general value, update the template files
4. **Log evolution** — record changes in `evolution-log.md`

### Evolution Principles

- **Don't break existing structure** — append only, never delete
- **2-occurrence rule** — only codify after seeing a pattern 2+ times (avoid noise)
- **User confirmation** — ask user before changing safety boundaries (retry limits, intervention conditions)
- **Lightweight changes** — keep template changes to ±5 lines, no large rewrites

### Evolution Log Format

```markdown
# Evolution Log

## v2 — 2026-07-13
- Added self-evolution phase (Phase 6)
- workflow.md: added pip mirror switching step for install-type projects
- boundaries.md: added network timeout as intervention condition

## v1 — 2026-07-01
- Initial version
```

---

## Agent Execution Instructions

When a user says "initialize micro-harness" or similar, follow these steps:

### Initialization

1. Determine the project directory (current working directory, or as specified by user)
2. Create `.harness/` directory
3. Create initial files from the templates (replace `{{project_name}}` with actual name)
4. Tell the user: ".harness/ initialized, currently in Phase 1: Requirements Clarification"

### Per-Session Workflow

**At the start of each session/task:**
1. Read `.harness/workflow.md` — know the current phase
2. Read `.harness/boundaries.md` — know the safety rules
3. Read `.harness/tasks/current.md` — know the progress
4. Read `.harness/bugs.md` — know pending issues
5. Advance through workflow phases, updating tasks/current.md after each step

**When encountering problems:**
1. Attempt to resolve (max 3 retries per boundaries.md)
2. After 3 failures → log to bugs.md → notify user
3. If the issue is recurring, flag it for evolution

**When completing a phase:**
1. Update workflow.md's "current phase"
2. Write to journal.md
3. Notify user of progress

---

## Design Principles

1. **Pure Markdown** — zero dependencies, any AI agent can read and write
2. **Agent-driven** — the agent self-advances through the workflow
3. **Progressive** — fill files as you go, no upfront paperwork
4. **Fail-safe** — boundaries.md prevents infinite loops
5. **Self-evolving** — each project makes the templates smarter

---

## Comparison with Trellis

| Dimension | Trellis | Micro-Harness |
|:----------|:--------|:-------------|
| Dependencies | npm + Python | ❌ None |
| Init | `trellis init` CLI | Agent reads files & creates structure |
| Task tracking | task.py scripts | Manual Markdown updates |
| Spec system | Multi-directory spec/ | Single workflow.md |
| Learning curve | Medium-High | Low |
| Best for | Long-term projects / Teams | Personal small projects |

---

## License

MIT

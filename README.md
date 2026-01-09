# Planning with Files

Manus-style file-based planning templates for Claude Code.

## The Pattern

```
Context Window = RAM (volatile, limited)
Filesystem = Disk (persistent, unlimited)

→ Anything important gets written to disk.
```

## Files

| File | Purpose | When to Update |
|------|---------|----------------|
| `task_plan.md` | Phases, progress, decisions | After each phase |
| `findings.md` | Research, discoveries | After ANY discovery |
| `progress.md` | Session log, test results | Throughout session |

## Usage

Copy these templates to any project directory when starting complex multi-step tasks.

## When to Use

**Use for:**
- Multi-step tasks (3+ steps)
- Research projects
- Building/creating projects
- Tasks spanning many tool calls

**Skip for:**
- Simple questions
- Single-file edits
- Quick lookups

## Source

Based on [planning-with-files](https://github.com/OthmanAdi/planning-with-files) skill for Claude Code.

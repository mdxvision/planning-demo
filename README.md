# Planning with Files

Manus-style file-based planning templates for Claude Code and other AI assistants.

## Quick Start

```bash
# Clone this repo
git clone https://github.com/mdxvision/planning-demo.git

# Initialize planning files in any project
cd your-project
../planning-demo/scripts/init.sh
```

This creates three files in your project:
- `task_plan.md` - Track phases and progress
- `findings.md` - Store research and discoveries
- `progress.md` - Log session actions and test results

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

## Examples

See the [examples/](examples/) folder for filled-out planning files showing how to use this system on a real project (building user authentication).

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

## Critical Rules

1. **Create plan first** - Never start complex work without `task_plan.md`
2. **Read before decide** - Re-read the plan before major decisions
3. **Update after act** - Mark phases complete, log errors
4. **Never repeat failures** - Track what you tried, mutate the approach

## Source

Based on [planning-with-files](https://github.com/OthmanAdi/planning-with-files) skill for Claude Code.

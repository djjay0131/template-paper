# {{PROJECT_NAME}}

## Project Overview

{{PROJECT_DESCRIPTION}}

## Documentation System

This project uses a **memory-bank** documentation approach:

- `memory-bank/` — Living documentation (project context, decisions, progress)
- `construction/` — Design-first development workspace (designs, requirements, sprints)
- `.claude/agents/` — Specialized agent configurations

## Quick Start

1. Read `memory-bank/activeContext.md` for current status
2. Read `memory-bank/projectbrief.md` for core objectives
3. Read `memory-bank/progress.md` for task tracking
4. Check `construction/` for active design work

## Paper Type

<!-- Uncomment the paper type you are writing -->
<!-- type: proposal -->
<!-- type: research-paper -->
<!-- type: position-paper -->

## Key Deadlines

| Date | Milestone |
|------|-----------|
| {{DATE}} | {{MILESTONE}} |

## Submission Requirements

- **Venue/Target**: {{VENUE_NAME}}
- **Page Limit**: {{PAGE_LIMIT}}
- **Format**: {{FORMAT}} (e.g., ACM, IEEE, custom LaTeX template)
- **Submission Portal**: {{URL}}
- **Additional Requirements**: {{REQUIREMENTS}}

## Key Locations

| Path | Description |
|------|-------------|
| `files/` | Reference materials, CFP docs, venue guidelines |
| `memory-bank/` | Living project documentation |
| `construction/` | Design workspace |
| `.claude/agents/` | Agent configurations |

## Agent Reference

| Agent | Purpose |
|-------|---------|
| `latex-agent` | LaTeX compilation, formatting, bibliography management |
| `proposal-agent` | Research proposal / CFP workflow (design → validate) |
| `paper-agent` | Research paper workflow (outline → draft → revise) |
| `position-paper-agent` | Position/vision paper workflow |
| `memory-agent` | Memory-bank documentation maintenance |
| `review-agent` | Quality gate: citations, compilation, content checks |

Choose the agent matching your paper type. The `latex-agent` and `review-agent` are used by all paper types.

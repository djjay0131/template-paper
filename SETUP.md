# Setup Guide — template-paper

This is a reusable template for writing academic papers and research proposals with Claude agent assistance.

## Quick Start

### 1. Copy this template

```bash
cp -r template-paper my-new-paper
cd my-new-paper
git init
```

### 2. Choose your paper type

This template supports three paper types. Pick the one that matches your project:

| Paper Type | Agent | Use For |
|-----------|-------|---------|
| **Proposal** | `proposal-agent` | Funding proposals, CFP responses, grant applications |
| **Research Paper** | `paper-agent` | Conference papers, journal articles, technical reports |
| **Position Paper** | `position-paper-agent` | Position papers, vision papers, opinion pieces |

Uncomment the matching line in `CLAUDE.md` under "Paper Type":
```markdown
<!-- type: proposal -->
<!-- type: research-paper -->
<!-- type: position-paper -->
```

### 3. Fill in placeholders

Search for `{{` across all files and replace with your project details:

```bash
grep -r "{{" --include="*.md" .
```

Key files to update:
- `CLAUDE.md` — Project name, description, deadlines, submission requirements
- `memory-bank/projectbrief.md` — Objectives, venue, research questions, scope
- `memory-bank/productContext.md` — Problem statement, approach, audience
- `memory-bank/techContext.md` — Methodology, tools

### 4. Add venue materials

Place CFP documents, venue guidelines, and LaTeX templates in `files/`.

### 5. Initialize LaTeX (optional)

If using LaTeX, ask the latex-agent to set up your document:
```
@latex-agent init <template>
```
Supported templates: `acm-sigconf`, `ieee-conference`, `ieee-journal`, `springer-lncs`, `arxiv`, `custom`

### 6. Start working

Depending on your paper type:

- **Proposal**: `@proposal-agent analyze-cfp files/<your-cfp.pdf>`
- **Research Paper**: `@paper-agent outline "Your Paper Title"`
- **Position Paper**: `@position-paper-agent thesis "Your thesis statement"`

## Project Structure

```
.
├── CLAUDE.md                          # Project config (edit this first)
├── SETUP.md                           # This file (delete after setup)
├── .claude/agents/
│   ├── latex-agent.md                 # LaTeX compilation & formatting
│   ├── proposal-agent.md             # Research proposal workflow
│   ├── paper-agent.md                # Research paper workflow
│   ├── position-paper-agent.md       # Position/vision paper workflow
│   ├── memory-agent.md               # Memory-bank maintenance
│   └── review-agent.md               # Quality gate (citations, compile, content)
├── memory-bank/                       # Living documentation
│   ├── projectbrief.md               # Core objectives
│   ├── productContext.md             # Problem & approach
│   ├── techContext.md                # Technical details
│   ├── systemPatterns.md            # Patterns & conventions
│   ├── activeContext.md             # Current focus
│   ├── progress.md                  # Task tracking
│   ├── phases.md                    # Phase coordination
│   ├── architecturalDecisions.md    # Decision log
│   └── archive/                     # Completed phases
├── construction/                      # Design-first workspace
│   ├── spec_builder.md              # Design document template
│   ├── design/                      # Design docs (before writing)
│   ├── requirements/                # Submission requirements
│   │   ├── submission-checklist.md
│   │   └── citation-matrix.md
│   └── sprints/                     # Sprint plans
└── files/                            # Reference materials & venue docs
```

## Agent Architecture

```
┌─────────────────────────────────────────────┐
│              Paper-Type Agent                │
│   (proposal / paper / position-paper)        │
│   Manages workflow, design, sprints          │
├──────────────┬──────────────┬───────────────┤
│ latex-agent  │ memory-agent │ review-agent  │
│ Compile,     │ Track        │ Quality gate, │
│ format, bib  │ progress     │ citations     │
└──────────────┴──────────────┴───────────────┘
```

- **Paper-type agent** drives the workflow and delegates to the others
- **latex-agent** handles all LaTeX compilation and formatting
- **memory-agent** keeps the memory-bank in sync
- **review-agent** runs quality checks before merging/submitting

## Tips

- Always design before writing — create a doc in `construction/design/` first
- Keep the citation matrix updated as you add references
- Run `@review-agent validate` before any PR or submission
- Use sprints to break large writing tasks into manageable pieces
- Delete this `SETUP.md` file once you've completed setup

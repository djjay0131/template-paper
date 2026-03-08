# Construction — Design-First Workspace

This folder manages the design-before-writing workflow for your paper or proposal.

## Structure

```
construction/
├── README.md            # This file
├── spec_builder.md      # Design document template
├── design/              # Design documents (created before writing)
├── requirements/        # Submission requirements and checklists
└── sprints/             # Sprint plans for executing designs
```

## Workflow

1. **Design** — Create a design doc in `design/` using `spec_builder.md` template
2. **Requirements** — Validate against submission requirements in `requirements/`
3. **Sprint** — Break design into tasks in `sprints/`
4. **Execute** — Write content per sprint plan
5. **Validate** — Check against submission requirements

## Rules

- No content is drafted without an approved design document
- Sprint tasks have clear acceptance criteria
- Completed sprints are archived to `memory-bank/archive/`

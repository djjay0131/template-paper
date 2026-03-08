# Paper

LaTeX source files for the paper/proposal.

## Files

- `main.tex` — Main document (edit this)
- `references.bib` — Bibliography
- `figures/` — Figures directory (create as needed)

## Building

```bash
# Full build
pdflatex main && bibtex main && pdflatex main && pdflatex main

# Or with latexmk (recommended)
latexmk -pdf main.tex

# Clean build artifacts
latexmk -C
```

## Venue Template

Replace the `\documentclass` in `main.tex` with your venue's template. Common options:

| Venue | Document Class |
|-------|---------------|
| ACM | `\documentclass[sigconf]{acmart}` |
| IEEE Conference | `\documentclass[conference]{IEEEtran}` |
| IEEE Journal | `\documentclass[journal]{IEEEtran}` |
| Springer LNCS | `\documentclass[runningheads]{llncs}` |
| arXiv / Generic | `\documentclass{article}` |

Place venue `.cls` and `.sty` files in this directory.

# Presentation

Beamer (LaTeX) slides for presenting your paper/proposal.

## Files

- `main.tex` — Slide deck (edit this)
- `figures/` — Figures directory (create as needed)

## Building

```bash
pdflatex main.tex && pdflatex main.tex

# Or with latexmk
latexmk -pdf main.tex
```

## Customization

Change the theme in `main.tex`:

| Theme | Style |
|-------|-------|
| `default` | Minimal, clean |
| `metropolis` | Modern (install `beamertheme-metropolis`) |
| `Madrid` | Classic with navigation bar |
| `Berlin` | Sidebar navigation |

Aspect ratio is set to 16:9. Change to 4:3 with `\documentclass[aspectratio=43]{beamer}`.

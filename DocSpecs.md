# DocSpecs — Hydrological Twin LaTeX White Book

## Objective
This specification describes how to reproduce the current documentation repository layout and build behavior for the Hydrological Twin White Book project.

## Repository structure to reproduce
```text
/
├── MASTER.tex
├── HTAS_user_guide.tex
├── HTAS_FR.tex
├── .gitignore
├── Setup/
│   ├── Packages.tex
│   ├── Shortcuts.tex
│   └── Messages_pkg/
├── Backmatter/
├── Mainmatter/
├── Bibliography/
└── Figures/
```

### Structure rules
- `MASTER.tex` is the main book entry point.
- `Setup/Packages.tex` centralizes package imports and rendering configuration.
- `Setup/Shortcuts.tex` centralizes reusable LaTeX commands/macros.
- `Backmatter/`, `Mainmatter/`, and `Bibliography/` are included from entry points using `\include{...}` or `\input{...}`.
- `Figures/` stores image assets referenced by LaTeX sources.

## .gitignore (must be preserved)
The repository ignores LaTeX build artifacts and generated PDF outputs:

```gitignore
*.aux
*.log
*.out
*.toc
*.bbl
*.blg
*.fls
*.fdb_latexmk
*.synctex.gz
*.run.xml
build/
*.brf
*.mtc*
*.lof
*.lot
*.maf
*.lol
*.nlo
*.pdf
```

This reflects the current repository policy: generated PDFs are treated as build artifacts and are not tracked.

## LaTeX style and conventions
- Document classes in use:
  - `book` for `MASTER.tex`
  - `article` for standalone documents (`HTAS_user_guide.tex`, `HTAS_FR.tex`)
- `MASTER.tex` language is configured through `Setup/Packages.tex` (`babel`, UTF-8, and T1 encoding). Standalone `.tex` files may define their own language setup.
- Shared typography/layout conventions are defined in `Setup/Packages.tex`:
  - `mathpazo`, `microtype`, `geometry`, `fancyhdr`, `fncychap`, `minitoc`, `listings`, `minted`.
- Shared semantic shortcuts are defined in `Setup/Shortcuts.tex` (for example `\hydrot`, `\cw`, `\cwv`, `\script{}`).
- Keep chapter/section hierarchy and formal white-book tone.

## Compiler and build requirements
- Use `pdflatex` as baseline compiler.
- Because `minted` is used in shared packages, compilation should support shell escape (`minted` calls the external Pygments process for syntax highlighting).

### Required commands
```bash
# Main white book
pdflatex -shell-escape -interaction=nonstopmode MASTER.tex
pdflatex -shell-escape -interaction=nonstopmode MASTER.tex

# Standalone guides
pdflatex -shell-escape -interaction=nonstopmode HTAS_user_guide.tex
pdflatex -shell-escape -interaction=nonstopmode HTAS_FR.tex
```

> Notes:
> - Run twice for references/table-of-contents stabilization.
> - If bibliography is enabled in `MASTER.tex`, run BibTeX in between LaTeX passes.

## Multiple `.tex` entry-point support
The project supports compiling multiple independent entry files:
- `MASTER.tex` (full White Book),
- `HTAS_user_guide.tex` (standalone user guide),
- `HTAS_FR.tex` (standalone French-language technical strategy summary for HydrologicalTwin and its multi-scale roadmap).

An agent reproducing this repository must keep these entry points independent and compilable separately.

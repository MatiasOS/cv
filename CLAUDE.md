# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build

Compile the CV PDF from the `eng/` directory using LuaLaTeX:

```bash
cd eng && lualatex matias_oveja_smith.tex
```

The compiled PDF (`eng/matias_oveja_smith.pdf`) is committed to the repo. Always rebuild and include the updated PDF when making content changes.

## Architecture

This is a LaTeX CV built on the [Awesome-CV](http://www.intridea.com/blog/2011/5/13/starting-your-awesome-resume-with-latex) template.

- **`eng/matias_oveja_smith.tex`** — Main entry point. Defines personal info, page geometry, color scheme, and imports section files via `\input{}`.
- **`eng/awesome-cv.cls`** — Custom document class providing all CV macros and styling. Uses Roboto (headers) and Source Sans Pro (body) fonts from `eng/fonts/`.
- **`eng/cv-sections/`** — Modular content files:
  - `skills.tex` — Technical skills grid
  - `experience.tex` — Work history entries
  - `education.tex` — Education entries
  - `extras.tex` — Talks, workshops, hackathons (currently commented out in main .tex)
  - `writing.tex` — Technical writing (currently commented out in main .tex)
- **`eng/cover_letter.tex`** — Separate cover letter document using the same class.

## Key Macros (from awesome-cv.cls)

| Macro | Usage |
|---|---|
| `\cvsection{Title}` | Major section heading with underline |
| `\cventry{Position}{Company}{Location}{Dates}{Description}` | Job/education entry (used inside `cventries` environment) |
| `\cvskill{Category}{Skills}` | Skill row (used inside `cvskills` environment) |
| `\cvhonor{Award}{Title}{Location}{Date}` | Honor/event entry (used inside `cvhonors` environment) |

## Color Schemes

Set in the main .tex file via `\colorlet{awesome}{<color>}`. Available options: `awesome-emerald`, `awesome-skyblue` (current), `awesome-red`, `awesome-pink`, `awesome-orange`, `awesome-nephritis`, `awesome-concrete`, `awesome-darknight`.

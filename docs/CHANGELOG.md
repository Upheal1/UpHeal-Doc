# Change Log

This file tracks all major changes to the thesis documentation. Use the format:

```
## YYYY-MM-DD — Name

### Changed
- What changed

### Why
- Why it changed

### Affected Files
- `file1.qmd`
- `file2.qmd`
```

---

## 2026-06-13 — System

### Changed
- Created Quarto project structure (`_quarto.yml`, chapters, styles, references)
- Wrote Chapter 1: Introduction (draft) with all 4 sections
- Added 10 new references to `references.bib`
- Created `docs/` folder with PLAN.md, PROGRESS.md, TEAM_ASSIGNMENTS.md, STYLE_GUIDE.md, CHANGELOG.md
- Updated `_quarto.yml` and `index.qmd` with team member names

### Why
- Initial thesis setup and team onboarding

### Affected Files
- `chapters/01-introduction.qmd`
- `references.bib`
- `_quarto.yml`
- `index.qmd`
- `docs/PLAN.md`
- `docs/PROGRESS.md`
- `docs/TEAM_ASSIGNMENTS.md`
- `docs/STYLE_GUIDE.md`
- `docs/CHANGELOG.md`

---

## 2026-06-15 — OpenCode (24h Sprint)

### Changed
- Added 28 citations across Ch2-Background, Ch3-Methodology, Ch4-Results, Ch5-Conclusions (previously 0 citations outside Ch1)
- Expanded Ch2 Background with citations for Woebot, Wysa, BERT, Whisper, RAG, gamification, and systematic reviews
- Enhanced Ch3 Methodology with citations for BERT, LLaMA, Gemma, instruction fine-tuning
- Added evaluation methodology section to Ch4 with 5-dimension rubric
- Removed all placeholder/TODO markers from Ch4
- Expanded Ch5 Conclusions with 8 prioritized future work directions and 5 acknowledged limitations
- Expanded appendix with repository links, project structure, database schema, API endpoints, and chart reproduction guide
- Verified all @sec-xxx cross-references are consistent
- Added chung2022scaling reference to Ch3 LLM section
- Build verified: `quarto render` succeeds with 0 errors

### Why
- 24-hour sprint per SYNC_PLAN.md and BRANCH_STRATEGY.md to complete remaining PROGRESS.md items
- Ch2 (Literature Review) required citations to meet academic standards
- Appendix was too thin for a submission-ready thesis

### Affected Files
- `chapters/02-background.qmd`
- `chapters/03-methodology.qmd`
- `chapters/04-results-discussions.qmd`
- `chapters/05-conclusions.qmd`
- `chapters/appendix.qmd`
- `references.bib`

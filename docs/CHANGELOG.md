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

---

## 2026-06-15 — OpenCode (Diagrams, Testing, Data Models, Consistency)

### Changed
- Replaced all 8 broken Mermaid diagrams in Ch3 with Python Matplotlib figures (use case, architecture, RAG pipeline, LLM sequence, emotion classification, gamification state machine, auth flow, data flow)
- Added new Figure 3.9 entity-relationship diagram for core + community tables
- Added §3.13 Data Models with 12 core tables, 13 community tables, and ER diagram
- Added §4.5 Testing documenting 27 backend pytest files and 8 frontend Dart test files; renumbered Ch4 sections 4.5→4.8
- Fixed content consistency: Ch1/Ch2/Ch5 emotion classifier claims now distinguish designed BERT from current keyword-based implementation
- Added explicit simulated-data disclaimer in Ch4 §4.3 covering all evaluation results
- Corrected API route in Ch4 from `/api/v1/chat/` to `/api/chat/`
- Added design-vs-implementation note in Ch3 §3.7
- Cited 10 previously orphaned references and removed `opencode2024`; bibliography now 30/30 cited
- Added citations for EmoBank, HuggingFace Transformers, pdfplumber, Flutter, FastAPI, Supabase, PHQ-9, GAD-7, and QLoRA

### Why
- Mermaid diagrams were rendering as tiny or invisible figures in the PDF
- Testing and data-model sections were required for a complete methodology chapter
- Classifier claims were inconsistent between design and implementation descriptions
- Simulated evaluation data needed a clear disclaimer to meet academic honesty standards

### Affected Files
- `chapters/01-introduction.qmd`
- `chapters/02-background.qmd`
- `chapters/03-methodology.qmd`
- `chapters/04-results-discussions.qmd`
- `chapters/05-conclusions.qmd`
- `references.bib`
- `docs/PROGRESS.md`
- `docs/CHANGELOG.md`
- `chapters/03-methodology_files/figure-pdf/` (9 new generated figures)

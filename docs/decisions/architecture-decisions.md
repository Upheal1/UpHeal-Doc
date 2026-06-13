# Architecture Decisions

This document records the rationale behind key architecture and tooling decisions.

## ADR-001: Quarto vs. LaTeX for Thesis Writing

**Status:** ✅ Accepted

**Context:**
The team considered Overleaf (LaTeX), Microsoft Word, and Quarto for the thesis. Overleaf was attempted but proved too complex for collaborative editing with 7 team members. Word lacks version control and automation for code-generated charts.

**Decision:**
Use Quarto (Markdown + LaTeX backend) with VS Code, Zotero, and GitHub.

**Consequences:**
- ✅ Easy to write in readable Markdown
- ✅ Supports code execution (Python charts, Mermaid diagrams)
- ✅ Git-versioned, AI-friendly
- ✅ Exports to PDF (submission) and DOCX (supervisor review)
- ⚠️ Requires Quarto + TinyTeX installation
- ⚠️ Initial setup complexity

**Date:** 2026-06-13

---

## ADR-002: 5 Chapters vs. 9 Chapters

**Status:** ✅ Accepted

**Context:**
The UpHeal project documentation recommended a 9-chapter structure (Introduction, Literature Review, Requirements, System Design, AI Architecture, Implementation, Testing, Results, Conclusion). However, the Pharos University thesis template mandates exactly 5 chapters.

**Decision:**
Map the 9 UpHeal chapters to the 5 university chapters:
- Ch1: Introduction (background + problem + solution)
- Ch2: Literature Review (all related work)
- Ch3: System Design (requirements + design + AI architecture + security)
- Ch4: Implementation & Results (implementation + testing + evaluation)
- Ch5: Conclusion (summary + future work + ethics)

**Consequences:**
- ✅ Matches university requirements
- ✅ Allows section-level granularity within chapters
- ✅ Easier to manage for a single thesis document
- ⚠️ Ch3 becomes the heaviest chapter
- ⚠️ Ch4 combines multiple topics

**Date:** 2026-06-13

---

## ADR-003: Quarto Book Format

**Status:** ✅ Accepted

**Context:**
Quarto supports multiple project types (website, book, manuscript). The thesis requires a single linear document with cover page, abstract, table of contents, chapters, and appendices.

**Decision:**
Use Quarto `project: type: book` with `documentclass: report` and `classoption: [12pt, a4paper]`.

**Consequences:**
- ✅ Generates professional academic PDF
- ✅ Supports TOC, LOF, LOT, numbered sections
- ✅ IEEE citation style via CSL
- ✅ Appendices in back matter
- ⚠️ Requires `xelatex` engine for some Unicode characters

**Date:** 2026-06-13

---

## ADR-004: GitHub for Collaboration

**Status:** ✅ Accepted

**Context:**
The team needs a shared workspace where all 7 members can contribute to the thesis asynchronously.

**Decision:**
Use GitHub repository `Upheal1/UpHeal-Doc` with branch-based editing.

**Consequences:**
- ✅ Full version history
- ✅ Git diffs show exactly what changed
- ✅ GitHub Issues for tracking feedback
- ✅ Pull Requests for peer review
- ⚠️ Team members must learn Git basics
- ⚠️ Merge conflicts possible if multiple edit same chapter

**Date:** 2026-06-13

---

## ADR-005: Mermaid for Diagrams

**Status:** ✅ Accepted

**Context:**
The thesis requires use case diagrams, sequence diagrams, and functional flow diagrams. draw.io is also an option for polished visuals.

**Decision:**
Use **Mermaid** for text-based diagrams (use case, sequence, flow) that render inline in `.qmd`. Use **draw.io** for polished architecture diagrams exported as SVG.

**Consequences:**
- ✅ Mermaid diagrams version-controlled in text
- ✅ AI assistants can edit Mermaid code directly
- ✅ draw.io for final visual polish
- ⚠️ Mermaid diagrams have limited styling
- ⚠️ draw.io requires manual export updates

**Date:** 2026-06-13

---

## ADR-006: Python for Charts

**Status:** ✅ Accepted

**Context:**
The thesis requires experimental results charts (emotion classification accuracy, retention curves, latency breakdowns). Options: Excel, Python, or manual drawing.

**Decision:**
Use **Python + Matplotlib + Pandas** in Quarto code blocks or standalone scripts (`scripts/generate_charts.py`).

**Consequences:**
- ✅ Reproducible charts from real data
- ✅ Code-executable during document rendering
- ✅ Easy to update when data changes
- ⚠️ Requires `matplotlib`, `pandas`, `jupyter` dependencies
- ⚠️ Chart generation can slow PDF rendering

**Date:** 2026-06-13

---

## Next Decision

**ADR-XXX: [Title]**

**Status:** [Proposed / Accepted / Rejected / Deprecated]

**Context:**
[Describe the context]

**Decision:**
[Describe the decision]

**Consequences:**
- [Positive consequence]
- [Negative consequence]

**Date:** [Date]

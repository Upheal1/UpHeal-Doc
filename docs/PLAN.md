# UpHeal Thesis Writing Plan

## Overview

This document tracks the master writing plan for the UpHeal graduation project thesis. The thesis follows the Pharos University Computer Science & AI department template: **5 chapters** (Introduction, Literature Review, System Design, Implementation & Results, Conclusion), plus an optional Appendix.

**Target completion date:** End of June 2026 (to be confirmed with supervisor)
**Format:** Quarto Book (.qmd) → PDF + DOCX
**Citation style:** IEEE
**Repository:** https://github.com/Upheal1/UpHeal-Doc

---

## Chapter-by-Chapter Plan

### Chapter 1: Introduction
**Owner:** Hozaifa + Ahmed Z. (Frontend/Architecture context)
**Reviewer:** Yahya
**Status:** ✅ Draft complete (2026-06-13)
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Background establishes mental health gap with WHO statistics
- [ ] Problem definition clearly identifies 4 challenges
- [ ] Proposed solution explains 4 pillars (RAG, emotion, gamification, privacy)
- [ ] All references are real, cited, and in IEEE format
- [ ] Supervisor approves scope

### Chapter 2: Literature Review
**Owner:** Yahya + Hozaifa (RAG/AI context)
**Reviewer:** Ahmed Osama
**Status:** ⬜ Not started
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Surveys 5+ recent publications per domain
- [ ] Covers: digital mental health, conversational agents, emotion recognition, gamification, RAG
- [ ] Gap analysis table comparing UpHeal vs existing solutions
- [ ] All references are real and cited

### Chapter 3: System Design
**Owner:** Hozaifa + Yahya (RAG/Architecture) + Devide + Malak (Security)
**Reviewer:** Ahmed Z. + Abdalrahman
**Status:** ⬜ Not started
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Functional requirements (10+ items)
- [ ] Non-functional requirements (5+ items)
- [ ] Use case diagram (Mermaid)
- [ ] Sequence diagram (Mermaid)
- [ ] Functional flow diagram (Mermaid)
- [ ] System architecture diagram (Mermaid)
- [ ] AI/ML pipeline design description
- [ ] Data models and database schema
- [ ] Gamification system design
- [ ] Security considerations (auth, encryption, crisis detection)
- [ ] Hardware specifications table

### Chapter 4: Implementation & Results
**Owner:** Abdalrahman + Ahmed Z. (Frontend) + Ahmed Osama (LLM)
**Reviewer:** Hozaifa + Yahya
**Status:** ⬜ Not started
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Technology stack table (detailed)
- [ ] Frontend implementation (screens, state management, native integration)
- [ ] Backend implementation (microservices, RAG pipeline, assessment engine)
- [ ] Chat LLM integration description
- [ ] Testing methodology (unit, integration, UAT)
- [ ] Results with charts (emotion accuracy, retention, latency, SUS score)
- [ ] All charts are generated from real data or reproducible scripts

### Chapter 5: Conclusion & Future Work
**Owner:** All team members (contributions)
**Reviewer:** Dr. Sahar Ghanem
**Status:** ⬜ Not started
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Key contributions summarized
- [ ] Future work directions (5+ items)
- [ ] Ethics considerations (privacy, consent, crisis, bias, transparency)
- [ ] Acknowledgements

### Appendix (Optional)
**Owner:** Hozaifa + Yahya
**Status:** ⬜ Not started
**Due:** [TBD]
**Acceptance Criteria:**
- [ ] Source code repository links
- [ ] Additional diagrams
- [ ] Publication list (if any)

---

## Milestones

| Milestone | Date | Deliverable | Status |
|-----------|------|-------------|--------|
| M1: Environment setup | 2026-06-13 | Quarto project + PDF skeleton | ✅ Done |
| M2: Ch1 + Ch2 draft | [TBD] | Introduction + Literature Review | 🔄 In progress |
| M3: Ch3 complete | [TBD] | System Design (heaviest chapter) | ⬜ Not started |
| M4: Ch4 complete | [TBD] | Implementation & Results (needs running system) | ⬜ Not started |
| M5: Ch5 + Abstract | [TBD] | Conclusion + formatting pass | ⬜ Not started |
| M6: Final review | [TBD] | PDF + DOCX submission-ready | ⬜ Not started |

---

## Dependencies

- Ch4 depends on Ch3 (architecture decisions must be documented first)
- Ch4 depends on a working system (test data needed for charts)
- Ch5 depends on Ch4 results
- All chapters depend on Ch1 (scope established)

**Critical path:** Ch1 → Ch2 → Ch3 → Ch4 → Ch5 → Final Review

## Weekly Check-in

Every [day of week] at [time], team reviews PROGRESS.md and resolves blockers.

---

## Notes
- All chapters should be written in .qmd files
- Use `@sec-label` for cross-references between chapters
- Use `[@citationKey]` for IEEE citations
- Mermaid diagrams render automatically in Quarto
- Python charts should use `scripts/generate_charts.py` or inline code blocks
- Supervisor feedback should be tracked in CHANGELOG.md
- When a team member edits their chapter, they should commit with a clear message

## How to Contribute

1. Pull the latest changes from GitHub
2. Edit your assigned chapter in `chapters/XX-chapter-name.qmd`
3. Run `quarto render` to verify the PDF builds
4. Update `PROGRESS.md` with your status
5. Commit with a message like: `[Ch3] Added use case diagram — Hozaifa`
6. Push to GitHub

For detailed contribution guidelines, see `STYLE_GUIDE.md`.
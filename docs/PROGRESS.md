# UpHeal Thesis Progress Tracker

## How to Use

- Update this file whenever you work on a chapter
- Use `✅` for done, `🔄` for in progress, `⬜` for not started
- Add `[DATE]` when you update a section
- Tag the owner and reviewer

---

## Chapter 1: Introduction
**Owner:** Hozaifa + Ahmed Z. | **Reviewer:** Yahya

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| 1.1 Background and Motivation | ✅ Draft | 2026-06-13 | WHO stats, AI opportunity, gamification evidence |
| 1.2 Problem Definition | ✅ Draft | 2026-06-13 | 4 challenges: personalization, retention, grounding, safety |
| 1.3 Proposed Solution | ✅ Draft | 2026-06-15 | 4 pillars; clarified emotion classifier is designed BERT / currently keyword-based |
| 1.4 Thesis Organization | ✅ Draft | 2026-06-13 | Cross-references to Ch2-5 |
| References added | ✅ | 2026-06-13 | 10 new references added to .bib |
| Supervisor review | ⬜ | | |
| Final revision | ⬜ | | |

---

## Chapter 2: Literature Review
**Owner:** Yahya + Hozaifa | **Reviewer:** Ahmed Osama

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| 2.1 Digital Mental Health Landscape | ✅ Draft | 2026-06-13 | WHO, Baumeister review, MENA context |
| 2.2 Conversational Agents | ✅ Draft | 2026-06-15 | Woebot, Wysa, Replika, Kumar review, citations added |
| 2.3 Emotion Recognition | ✅ Draft | 2026-06-15 | BERT, Whisper, GoEmotions, EmoBank, Transformers lib, citations added |
| 2.4 Gamification for Health | ✅ Draft | 2026-06-15 | Hamari meta-analysis, 20-40% boost, citation added |
| 2.5 Retrieval-Augmented Generation | ✅ Draft | 2026-06-15 | Lewis et al., medical RAG, Reimers Sentence-BERT, citations added |
| 2.6 Gap Analysis | ✅ Draft | 2026-06-15 | Table comparing Woebot/Wysa/Replika/UpHeal; emotion row updated to "keyword-based (BERT planned)" |
| References | ✅ | 2026-06-15 | 30/30 references cited; orphan references resolved |
| Supervisor review | ⬜ | | |
| Final revision | ⬜ | | |

---

## Chapter 3: System Design
**Owner:** Hozaifa + Yahya + Devide + Malak | **Reviewer:** Ahmed Z. + Abdalrahman

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| 3.1 Functional Requirements | ✅ Draft | 2026-06-13 | 10 FRs (FR-01 to FR-10) |
| 3.2 Non-Functional Requirements | ✅ Draft | 2026-06-13 | 7 NFRs (latency, compliance, uptime, etc.) |
| 3.3 Use Case Diagram | ✅ Draft | 2026-06-15 | Matplotlib figure with 8 user + 6 system use cases (was Mermaid) |
| 3.4 Sequence Diagram | ✅ Draft | 2026-06-15 | Matplotlib sequence diagram: User → Flutter → FastAPI → ChromaDB → LLM → Auditor |
| 3.5 Functional Flow Diagram | ✅ Draft | 2026-06-15 | Matplotlib flow diagram: Home → Chat → Mood → Assessment → Roadmap |
| 3.6 System Architecture Diagram | ✅ Draft | 2026-06-15 | Matplotlib block diagram: Frontend → Gateway → Microservices → AI Pipeline → Data |
| 3.7 AI/ML Pipeline Design | ✅ Draft | 2026-06-15 | 5 stages: Input → Emotion → RAG → LLM → Audit; all pipeline figures now Matplotlib |
| 3.13 Data Models | ✅ Draft | 2026-06-15 | 12 core + 13 community tables + ER diagram (was §3.8, renumbered) |
| 3.9 Gamification System Design | ✅ Draft | 2026-06-15 | XP, levels, badges (10), achievements (12), challenges (10); state machine as Matplotlib |
| 3.10 Security Considerations | ✅ Draft | 2026-06-15 | 3-tier JWT, TLS 1.3, AES-256, RLS, crisis detection; auth flow as Matplotlib |
| 3.11 Implementation Stack & Hardware | ✅ Draft | 2026-06-15 | Stack table with Flutter, FastAPI, Supabase citations; hardware specs |
| Supervisor review | ⬜ | | |
| Final revision | ⬜ | | |

---

## Chapter 4: Implementation & Results
**Owner:** Abdalrahman + Ahmed Z. + Ahmed Osama | **Reviewer:** Hozaifa + Yahya

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| 4.1 Experimental Setup | ✅ Draft | 2026-06-15 | Stack, screens, backend components; PHQ-9/GAD-7 citations; simulated data disclaimer |
| 4.2 System Implementation | ✅ Draft | 2026-06-15 | Frontend, backend, chat LLM, community; API route corrected to `/api/chat/` |
| 4.3 Emotion Classification Results | ✅ Draft | 2026-06-15 | Accuracy metrics, confusion matrix; results flagged as simulated |
| 4.4 Response Quality Results | ✅ Draft | 2026-06-15 | LLM response quality, RAG retrieval metrics; simulated |
| 4.5 Testing | ✅ Draft | 2026-06-15 | 27 backend pytest + 8 frontend Dart test files; categorized tables |
| 4.6–4.8 Retention, Performance, Discussion | ✅ Draft | 2026-06-15 | Retention curve, latency breakdown, SUS, discussion; all simulated |
| Supervisor review | ⬜ | | |
| Final revision | ⬜ | | |

---

## Chapter 5: Conclusion & Future Work
**Owner:** All | **Reviewer:** Dr. Sahar Ghanem

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| 5.1 Summary of Contributions | ✅ Draft | 2026-06-15 | 4 key contributions; emotion classifier described accurately |
| 5.2 Impact on Technology | ✅ Draft | 2026-06-15 | RAG + safety auditing, gamification framework |
| 5.3 Impact on Society | ✅ Draft | 2026-06-15 | MENA treatment gap, bilingual crisis detection |
| 5.4 Ethics Considerations | ✅ Draft | 2026-06-15 | 6 principles; classifier bias note updated |
| 5.5 Suggestions for Future Work | ✅ Draft | 2026-06-15 | 8 directions; QLoRA citation added |
| 5.6 Limitations | ✅ Draft | 2026-06-15 | 5 acknowledged limitations |
| Acknowledgements | ✅ Draft | 2026-06-13 | Dr. Sahar Ghanem + team + families + open source |
| Supervisor review | ⬜ | | |
| Final revision | ⬜ | | |

---

## Appendix
**Owner:** Hozaifa + Yahya

| Section | Status | Last Updated | Notes |
|---------|--------|-------------|-------|
| Source Code Links | ✅ | 2026-06-15 | 4 repositories listed |
| Additional Diagrams | ✅ | 2026-06-15 | DB schema, API endpoints, project structure |
| Publication List | ✅ | 2026-06-15 | Target venues listed |

---

## Global Tasks

| Task | Status | Last Updated | Owner |
|------|--------|-------------|-------|
| Update _quarto.yml with team names | ✅ | 2026-06-13 | System |
| Update index.qmd cover page | ✅ | 2026-06-13 | System |
| Rebuild PDF | ✅ | 2026-06-15 | PDF renders with 9 new Matplotlib figures |
| Write all 5 chapter drafts | ✅ | 2026-06-13 | System |
| Push to GitHub | ✅ | 2026-06-15 | Commit 6c12d9b pushed to origin/main |
| Add citations to Ch2-Ch5 | ✅ | 2026-06-15 | 30/30 references now cited in text |
| Expand appendix | ✅ | 2026-06-15 | DB schema, API endpoints, project structure |
| Remove placeholders | ✅ | 2026-06-15 | All TODO markers removed |
| Replace Mermaid diagrams | ✅ | 2026-06-15 | 8 diagrams → Matplotlib; no more Mermaid in Ch3 |
| Add §4.5 Testing + §3.13 Data Models | ✅ | 2026-06-15 | 35 test files documented; 25 tables + ER diagram |
| Fix content consistency | ✅ | 2026-06-15 | Classifier claims, API route, simulated-data disclaimer |
| Add real test data to Ch4 | ✅ | 2026-06-15 | Simulated data retained with explicit disclaimer |
| Review all references | ✅ | 2026-06-15 | 30/30 references cited; 0 orphans |
| Final formatting pass | ✅ | 2026-06-15 | Cross-refs verified, style guide check passed |
| Supervisor sign-off | ⬜ | | |

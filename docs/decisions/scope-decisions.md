# Scope Decisions

This document records what is **in scope** and **out of scope** for the thesis. It helps the team avoid scope creep and maintain focus.

## In Scope

### Core Thesis Content

1. **Thesis document** (5 chapters + appendix) covering the UpHeal graduation project
2. **Introduction** — Background, problem definition, proposed solution
3. **Literature Review** — Digital mental health, conversational agents, emotion recognition, gamification, RAG
4. **System Design** — Requirements, diagrams, architecture, AI pipeline, security, gamification, hardware
5. **Implementation & Results** — Tech stack, frontend/backend implementation, testing, evaluation metrics
6. **Conclusion** — Summary, future work, ethics

### Technical Implementation

7. **Flutter frontend** (cross-platform mobile app)
8. **FastAPI backend** (microservices gateway)
9. **RAG pipeline** (ChromaDB + sentence-transformers + clinical knowledge base)
10. **Assessment engine** (Bayesian + sigmoid scoring for GAD-7/PHQ-9)
11. **Clinical auditor** (crisis detection, robotic tone, safety risk)
12. **Gamification engine** (XP, levels, badges, achievements, challenges, streaks)
13. **Supabase integration** (auth, PostgreSQL, storage, real-time)
14. **Groq AI Chat** (llama-3.1-8b-instant, CBT prompt)

### Documentation

15. **Quarto project** with IEEE citations
16. **Mermaid diagrams** for use case, sequence, flow, architecture
17. **Python-generated charts** for results
18. **GitHub repository** for collaborative editing

---

## Out of Scope

### Not in the Thesis

1. **Full LLM chat implementation** — The thesis will describe the *architecture* and *intended design* for RAG-augmented chat, but the current codebase has a stub placeholder. The thesis will not claim the full chat is fully implemented unless it is completed before submission.
2. **Emotion classifier** — Planned but not implemented. The thesis will describe the *design* and *planned approach* but not claim it is deployed.
3. **Whisper speech-to-text** — Planned but not implemented. Same treatment as above.
4. **GPU-hosted inference** — The thesis will describe the *deployment architecture* (RunPod, Ollama) but the actual GPU deployment is not required for thesis submission.
5. **Clinical trial** — A formal clinical trial is mentioned as future work but is not part of the graduation project scope.
6. **Multilingual support** — Arabic support is planned as future work but not implemented in the current version.
7. **Therapist dashboard** — Planned as future work but not implemented.
8. **Edge deployment** — Model quantization and edge deployment are future work.
9. **Social features** — Anonymous peer support groups are future work.
10. **Native iOS implementation** — The app is cross-platform Flutter, but the thesis will focus on the Flutter layer, not platform-specific native code.

---

## How to Change Scope

If a team member wants to move something from "Out of Scope" to "In Scope":

1. Open a discussion in the weekly check-in
2. If the team agrees, update this file
3. Update `docs/PLAN.md` with any new tasks
4. Update `docs/PROGRESS.md` with the new item
5. Log the change in `docs/CHANGELOG.md`

## Rationale

The thesis is a **graduation project documentation**, not a full product launch report. The goal is to demonstrate the team's ability to design, implement, and evaluate a system — not to ship a production-ready product. The scope reflects what is achievable within the graduation project timeline (one academic year) with 7 team members.

## Scope Creep Warning Signs

- Adding new features to the system just to "make the thesis look better"
- Including technologies not used in the actual codebase
- Claiming features are "fully implemented" when they are stubs
- Writing about future work as if it were completed

If you see scope creep, flag it in the weekly check-in.

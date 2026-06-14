# 24-Hour Thesis Writing Sprint Plan

**Start:** [TO BE SET] | **Deadline:** [TO BE SET] | **Format:** Quarto Book → PDF (XeLaTeX)

## Team

| Name | Role | Primary Focus |
|------|------|--------------|
| Hozaifa Moustafa | RAG & Backend | Ch2 §2.2/2.5, Ch3 FR/NFR/use case/data models, Ch4 §4.3, Ch5 §5.3 Ethics |
| Abdalrahman Osama | Frontend Lead | Ch4 §4.2 Frontend, Ch4 §4.4 Chat LLM, Ch4 §4.6 Results, Appendix updates |
| Yahya Amr | RAG & Database | Ch2 §2.1/2.3/2.4, References (.bib), Ch4 §4.5 Testing, Cross-checks |

---

## Current State Assessment

| Chapter | Lines | Status | Key Gaps |
|---------|-------|--------|----------|
| Ch1 Introduction | 50 | ✅ Complete | Minor expansion possible |
| Ch2 Background | 86 | ⬜ Too short | Needs 3× expansion; only 11 citations; each subsection is 3–8 lines |
| Ch3 Methodology | 484 | 🔄 Mostly done | Missing formal FR/NFR; missing use case diagram; data models need update |
| Ch4 Results | 218 | 🔄 Needs update | Backend service list wrong (12, not 10); 48 screens (not 40+); community feature undocumented; placeholder chat pipeline |
| Ch5 Conclusions | 57 | ⬜ Incomplete | Missing §5.3 Ethics; brief future work |
| Appendix | 114 | 🔄 Needs update | Schema/API/project structure need codebase truth |
| References | 15 | ⬜ Insufficient | Need 30+; missing DSM-5-TR, GAD-7, PHQ-9, Flutter, FastAPI, Supabase, ChromaDB, HNSW, SDT |

### Critical Codebase Mismatches to Fix

The thesis was written from architectural intent, not the built system. These must be corrected:

1. **"10 microservices"** → actual backend has **12 services**: gateway, assessment, knowledge_base, architect, auditor, chat, journal, telemetry, roadmap, ingestion, director, shared (+ emotion planned)
2. **"40+ screens"** → actual frontend has **48 screens** with GoRouter navigation, design system, community hub, group chat, focus rooms
3. **"fine-tuned BERT emotion classifier"** → emotion classifier **does not exist yet**; only keyword-based sentiment in the auditor
4. **Chat "backend uses Groq directly"** → frontend now routes through `UphealApi().sendChatMessage()` → `POST /api/chat`; backend has a **placeholder** `_generate_response()`
5. **Flutter 3.19+** → pubspec says `>=3.3.0 <4.0.0`
6. **Community feature** (Supabase Realtime, Edge Functions, group chat, focus rooms, 7 SQL migrations, 13 tables) is **not mentioned at all**
7. **Gamification numbers** need verification against actual code: XP formula, 10 badges, 12 achievements, 10 challenges, community XP events

---

## Hour-by-Hour Schedule

### Phase 1: Foundation (Hours 0–6)

| Hour | Hozaifa | Abdalrahman | Yahya |
|------|---------|-------------|-------|
| 0–2 | Expand **Ch2 §2.2 Conversational Agents** — add Woebot clinical trial details, Wysa RCT results, Replika user studies, CASA-chat taxonomy. Add 3+ references | Sketch **Ch4 §4.2 Frontend Implementation** structure: list all 48 screens by route, GoRouter navigation, Provider state management, 20+ service classes, community feature architecture | Expand **Ch2 §2.3 Emotion Recognition** — add BERT architecture details, emotion detection datasets (GoEmotions, EmoBank), Whisper-based ASR. Add 3+ references |
| 2–4 | Expand **Ch2 §2.5 RAG** — add dense retrieval details, HNSW algorithm citation, ChromaDB specifics, sentence-transformer evaluation. Add 3+ references | Write **Ch4 §4.2** body text: onboarding flow (3-screen wizard), Supabase Auth (email/password + Google), home dashboard, AI Coach screen, community hub (feed + groups + chat), gamification engine implementation | Expand **Ch2 §2.4 Gamification** — add Self-Determination Theory (Deci & Ryan), gamification taxonomy (points/badges/leaderboards), health gamification studies. Add 3+ references |
| 4–6 | Write **Ch3 §3.1 FR/NFR** — extract 10 functional requirements and 7 non-functional requirements from the actual codebase (assessment flow, chat flow, RAG retrieval, gamification triggers, crisis detection, journal CRUD, telemetry) | Continue **Ch4 §4.2** — gamification implementation: XP formula `100 + (level-1)*50`, 10 badges (streak/tasks/addiction-free), 12 achievements (5 types), 10 challenges (daily/weekly/special), streak system with freeze tokens, reward orchestrator, comeback reward | Expand **Ch2 §2.1 Digital MH landscape** — add MENA-specific mental health data, COVID-19 telehealth acceleration, treatment gap statistics, Baumeister systematic review detail. Add 2+ references |

**Checkpoint V1 (Hour 6):** Ch2 expanded to 250+ lines; 15+ references in .bib; FR/NFR drafted in Ch3; Ch4 §4.2 outline complete.

---

### Phase 2: Core Content (Hours 6–14)

| Hour | Hozaifa | Abdalrahman | Yahya |
|------|---------|-------------|-------|
| 6–8 | Write **Ch4 §4.3 Backend Implementation** — actual service map: gateway orchestrator (3-stage pipeline: Profiler → Architect → Assemble), assessment service (Bayesian GAD-7/PHQ-9 with 55%/45% blend + sigmoid R_app), RAG knowledge base (ChromaDB + all-mpnet-base-v2, 768-dim), architect pipeline (triple-threat reranking: 0.35×sim + 0.25×form + 0.25×R_app + 0.15×utility) | Write **Ch4 §4.4 Chat LLM Integration** — current architecture: Flutter → `UphealApi().sendChatMessage()` → `POST /api/chat` → gateway → `ChatService.send_message()` → pipeline (emotion classify → RAG retrieve → prompt assemble → LLM generate → clinical audit), Groq `llama-3.1-8b-instant`, migration path to Ollama | Add 10+ **references to .bib** — DSM-5-TR, Kroenke PHQ-9, Spitzer GAD-7, Deci & Ryan SDT, Johnson-Gentile gamification taxonomy, ChromaDB docs, FastAPI docs, Flutter framework, Supabase docs, Malkov HNSW |
| 8–10 | Write **Ch4 §4.3 continued** — auditor service (crisis detection EN/41 + AR/20 keywords, robotic tone, frustration scoring 0.0–1.0), ingestion pipeline (PDF extraction via pdfplumber, semantic chunking with 15% overlap, formatter agent with LLM enrichment for difficulty/xp/safety tags), director evaluator (7-day window, 6 mutation triggers: LOW_COMPLETION, HIGH_DROP_OFF, etc.) | Write **Ch4 §4.4 continued** — community feature: Supabase Realtime subscriptions (feed:global broadcast, group:{groupId} broadcast), Edge Functions (create-post with moderation, send-message with auth), 7 SQL migrations defining 13 tables with RLS policies, focus room Pomodoro sync | Write **Ch4 §4.5 Testing** — describe test suite: 29 backend test files (pytest), 6 frontend test files, integration tests. Categories: architect pipeline, assessment core, auditor crisis detection, ChromaDB adapter, orchestration, rate limiting, sentiment classifier, authentication middleware |
| 10–12 | Write **Ch3 Use Case Diagram** — Mermaid diagram with 8 user use cases (Register/Login, Take Assessment, Chat with AI Coach, View Roadmap, Track Mood, Journal Entry, Manage Gamification, Join Community) + 6 system use cases (RAG Retrieval, Emotion Classification, Clinical Audit, Crisis Detection, Roadmap Generation, Gamification XP Calculation) | Write **Ch4 §4.5 continued** — frontend unit tests (widget tests, service tests, model tests), manual UAT description, SUS methodology (10-question SUS, n=20 participants) | Add 5+ more **references to .bib** — Hutton pdfplumber, Wolf HuggingFace Transformers, Dettmers QLoRA, Demasio GoEmotions, Park EmoBank |
| 12–14 | Write **Ch3 §3.8 Data Models** expansion — update Supabase schema: add community tables (posts, comments, groups, group_messages, message_reactions, focus_room_state, community_xp_events, community_notifications), chat tables (chat_sessions, chat_messages), add field details for all 20+ tables | Write **Ch4 §4.6 Results** — update charts: add community engagement metrics (posts/week, messages/week, group activity), update screen count to 48, add navigation architecture diagram (GoRouter StatefulShellRoute) | **Cite-check Ch2–Ch5**: ensure every new reference is cited inline at least once, update `docs/PROGRESS.md` |

**Checkpoint V2 (Hour 14):** Ch4 §4.2–4.4 written with codebase truth; Ch3 use case diagram added; 30+ references in .bib; data models updated.

---

### Phase 3: Completion & Verification (Hours 14–20)

| Hour | Hozaifa | Abdalrahman | Yahya |
|------|---------|-------------|-------|
| 14–16 | Write **Ch5 §5.3 Ethics Considerations** — data privacy (AES-256 at rest, TLS 1.3 in transit, Supabase RLS policies), informed consent (opt-in data collection, GDPR-aligned), crisis protocol (EN/AR hotlines: 988, Crisis Text Line, 911 + Arabic equivalents), algorithmic bias (emotional equity across demographics), transparency (AI explainability), data minimization | Polish **Ch4 §4.2–4.4** — verify all screen names match `lib/screens/`, verify all service classes match `lib/services/`, verify all model classes match `lib/models/`, cross-check numbers against actual codebase | Write **Appendix updates** — update source code repositories (4 repos), update database schema (add 13 community + 2 chat tables with all columns), update API endpoints (add community routes + chat endpoints + journal CRUD), update project structure tree |
| 16–18 | Review **Ch3** — verify methodology matches codebase: 3-stage pipeline (Profiler → Architect → Assemble), triple-threat reranking weights, Bayesian GAD-7/PHQ-9 blending ratio (55%/45%), sigmoid R_app formula, formatter agent LLM enrichment, director evaluator triggers | Review **Ch4 §4.2** — verify gamification numbers: XP formula matches `xp_config.dart`, 10 badges match `badge_model.dart`, 12 achievements match `achievement.dart`, 10 challenges match `challenge_model.dart`, streak milestones match `streak_service.dart`, community XP events match `community_models.dart` | Cross-check **all citations** — verify every `[@citationKey]` has a matching `.bib` entry, verify every `.bib` entry is cited at least once inline, no orphan references, no uncited references |
| 18–20 | **Ch1 final review** — verify introduction matches expanded Ch2–Ch5 (especially §1.4 Thesis Organization cross-references), ensure consistency of terminology and system description | **Appendix final review** — verify project structure tree matches actual directory listing, verify chart reproduction instructions work (`python scripts/generate_charts.py`), verify all table/figure numbers are sequential | **References cleanup** — final pass: sort alphabetically, verify IEEE format (authors, title, journal, volume, pages, year), verify DOIs where available, remove opencode2024 if unused |

**Checkpoint V3 (Hour 20):** Ch5 ethics written; all data models updated; community feature documented; all 30+ references cited; codebase numbers verified.

---

### Phase 4: Build & Ship (Hours 20–24)

| Hour | Owner | Task |
|------|-------|------|
| 20–21 | Hozaifa | Run `quarto render` — fix any LaTeX errors, Mermaid rendering issues, Python chart errors |
| 21–22 | Abdalrahman | Open compiled PDF, verify all figures render, check page breaks, verify table formatting, verify all code blocks format correctly |
| 22–23 | Yahya | Final **cite-check pass**: open PDF, verify every `[1]`–`[30+]` resolves in the bibliography, verify figure/table numbering is sequential, verify `@sec-` cross-references resolve to correct chapter numbers |
| 23–24 | All | Final commit and push: |

```bash
cd "d:\Career\Grad Project\UpHeal-Doc"
git checkout -b sprint/24h-thesis-completion
git add .
git commit -m "[Sprint] 24h thesis completion

- Expanded Ch2 from 86 to 250+ lines with citations
- Added FR/NFR to Ch3 with use case diagram
- Updated Ch3 data models with community + chat tables
- Rewrote Ch4 §4.2 with 48 screens, GoRouter, Supabase auth
- Rewrote Ch4 §4.3 with actual 12-service backend architecture
- Rewrote Ch4 §4.4 with chat pipeline and community feature
- Updated Ch4 §4.5 with real test suite (29+ 6 files)
- Updated Ch4 §4.6 with community metrics
- Added Ch5 §5.3 Ethics Considerations
- Expanded references from 15 to 30+
- Updated Appendix with codebase truth
- Fixed all codebase mismatches"
git push origin sprint/24h-thesis-completion
```

**Checkpoint V4 (Hour 24):** PDF builds with 0 errors; all references cited; all codebase numbers verified; pushed to GitHub.

---

## Verification Checkpoints

| Checkpoint | Hour | Criteria |
|-----------|------|----------|
| V1 | 6 | Ch2 expanded 3×; 15+ references; FR/NFR drafted; Ch4 §4.2 outlined |
| V2 | 14 | Ch4 §4.2–4.4 written with codebase truth; Ch3 use case diagram; 30+ references; data models updated |
| V3 | 20 | Ch5 ethics done; community documented; all refs cited; numbers verified |
| V4 | 24 | `quarto render` succeeds; PDF builds; refs resolve; pushed to GitHub |

---

## Success Metrics

- [ ] Ch2 is 250+ lines with 20+ inline citations
- [ ] Ch3 has formal FR/NFR section and use case diagram
- [ ] Ch4 §4.2 lists all 48 screens with route paths
- [ ] Ch4 §4.3 describes the actual 12-service architecture
- [ ] Ch4 §4.4 documents chat pipeline (Flutter → backend → emotion → RAG → LLM → audit → response)
- [ ] Ch4 §4.4 documents community feature (Supabase Realtime, Edge Functions, 13 tables)
- [ ] Ch4 §4.5 describes 29 backend + 6 frontend test files
- [ ] Ch4 §4.6 has real numbers matching the codebase
- [ ] Ch5 has a dedicated §5.3 Ethics section
- [ ] References .bib has 30+ entries, all cited inline
- [ ] All codebase mismatches from the assessment table are corrected
- [ ] `quarto render` builds the PDF with 0 errors
- [ ] Cross-references (`@sec-`, `@fig-`, `@tbl-`) all resolve

---

## References to Add (Minimum 15)

| Citation Key | Description | Who Adds | Cited In |
|-------------|-------------|----------|----------|
| `apa2022dsm5tr` | DSM-5-TR (APA, 2022) | Hozaifa | Ch2, Ch3 |
| `kroenke2002phq9` | PHQ-9 validation | Yahya | Ch2, Ch4 |
| `spitzer2006gad7` | GAD-7 validation | Yahya | Ch2, Ch4 |
| `deci2000sdt` | Self-Determination Theory | Yahya | Ch2 §2.4 |
| `malkov2018hnsw` | HNSW algorithm | Hozaifa | Ch3 |
| `wolf2020transformers` | HuggingFace Transformers | Hozaifa | Ch3, Ch4 |
| `dettmers2022qlora` | QLoRA quantization | Hozaifa | Ch5 |
| `demszky2019goemotions` | GoEmotions dataset | Yahya | Ch2 §2.3 |
| `bostrom2020emobank` | EmoBank dataset | Yahya | Ch2 §2.3 |
| `johnson2015gamification` | Gamification taxonomy in health | Yahya | Ch2 §2.4 |
| `chromadb2024` | ChromaDB vector database | Hozaifa | Ch3, Ch4 |
| `fastapi2024` | FastAPI framework | Hozaifa | Ch4 |
| `flutter2024` | Flutter framework | Abdalrahman | Ch4 |
| `supabase2024` | Supabase (PostgreSQL + Auth) | Abdalrahman | Ch4 |
| `hutton2022pdfplumber` | pdfplumber library | Hozaifa | Ch3 |

---

## Quick Reference: Actual Codebase Numbers

These numbers must replace estimates in the thesis:

| Metric | Thesis Says | Actual Codebase | Source |
|--------|-------------|-----------------|--------|
| Screens | 40+ | **48** | `lib/screens/` + `lib/features/` |
| Microservices | 10 | **12** (gateway, assessment, KB, architect, auditor, chat, journal, telemetry, roadmap, ingestion, director, shared) | `services/` |
| State management | Provider | **Provider + Riverpod + Hive + SharedPreferences** | `pubspec.yaml`, `main.dart` |
| Navigation | — | **GoRouter** with StatefulShellRoute | `lib/navigation/app_router.dart` |
| Auth | Supabase Auth | **Supabase Auth** (email/password + Google) + 3-tier JWT | `auth_middleware.py`, `auth_model.dart` |
| Community tables | 0 | **13** (profiles, posts, comments, groups, group_members, group_messages, etc.) | `supabase/migrations/` |
| Edge Functions | 0 | **2** (create-post, send-message) | `supabase/functions/` |
| SQL migrations (frontend) | 0 | **7** | `supabase/migrations/` |
| SQL migrations (backend) | 0 | **13** | `Upheal-RAG-System/supabase/migrations/` |
| Test files (backend) | 25+ | **29** | `tests/` |
| Test files (frontend) | 0 | **6** | `test/` |
| Badges | 10 | **10** (4 streak, 3 task, 3 addiction-free) | `badge_model.dart` |
| Achievements | 12 | **12** (5 types) | `achievement.dart` |
| Challenges | 10 | **10** (4 daily, 3 weekly, 3 special) | `challenge_model.dart` |
| XP formula | XP = base × streak × difficulty | `level_up = 100 + (level-1) × 50` | `xp_config.dart` |
| Chat pipeline | Groq direct | **Backend pipeline** (Flutter → UphealApi → gateway → ChatService) | `ai_chat_service.dart` |
| Emotion classifier | BERT fine-tuned | **Does not exist** (placeholder) | `services/emotion/` missing |
| RAG embedding model | all-mpnet-base-v2 | **all-mpnet-base-v2 (768-dim)** ✅ | `chroma_adapter.py` |
| LLM | Groq llama-3.1-8b-instant | **Groq llama-3.1-8b-instant** ✅ | `ai_chat_service.dart`, `orchestrator.py` |
| Community feature | Not mentioned | **Full implementation** (feed, groups, chat, focus rooms) | `features/community/` |

---

## Branch Strategy

| Action | Branch |
|--------|--------|
| Create sprint branch | `git checkout -b sprint/24h-thesis-completion` |
| Push at end | `git push origin sprint/24h-thesis-completion` |
| Merge after review | Create PR to merge into `main` |

---

## Communication

- **Every 4 hours:** Quick sync in group chat (WhatsApp/Telegram)
  - What did you write?
  - Any blockers?
  - Do you need to reassign a section?

- **Blockers:** If a section requires codebase knowledge the owner doesn't have, ask in the group chat immediately. The person who wrote that code should respond within 30 minutes.

- **No long meetings.** Only async updates.
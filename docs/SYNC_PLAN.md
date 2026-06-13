# Writing Sync Plan: Hozaifa, Abdalrahman, Ahmed, Yahya

## Core Writing Team

| Name | Role | Primary Focus | Chapters |
|------|------|--------------|----------|
| **Hozaifa Moustafa** | RAG & Database | Architecture, RAG pipeline, diagrams | Ch1 (co), Ch3 (lead), Ch4 (backend) |
| **Abdalrahman Osama** | Frontend Lead | Flutter UI, screens, gamification | Ch1 (co), Ch4 (lead) |
| **Ahmed Osama** | AI/LLM | Emotion classifier, LLM integration, AI pipeline | Ch2 (lead), Ch3 (AI section), Ch4 (LLM) |
| **Yahya Amr** | RAG & Database | Literature, architecture, backend | Ch1 (review), Ch2 (co), Ch3 (co), Ch4 (backend) |

---

## Chapter Dependency Map

```
Ch1 (Intro) ──→ Ch2 (Lit Review) ──→ Ch3 (System Design) ──→ Ch4 (Implementation) ──→ Ch5 (Conclusion)
     │                │                      │                       │
     │                │                      │                       │
     ├─ Hozaifa      ├─ Ahmed (lead)       ├─ Hozaifa (lead)      ├─ Abdalrahman (lead)
     ├─ Abdalrahman  ├─ Yahya (co)         ├─ Yahya (co)          ├─ Hozaifa (backend)
     │               ├─ Hozaifa (co)       ├─ Ahmed (AI)          ├─ Yahya (backend)
     │                                     ├─ Devide+Malak (sec)  ├─ Ahmed (LLM)
     │
     Must complete first
```

**Key Rule:** You cannot start writing a chapter until the PREVIOUS chapter's draft is approved.

---

## Detailed Schedule

### Week 1: Ch1 (Introduction) + Ch2 (Literature Review) — **Hozaifa + Abdalrahman**

| Day | Task | Owner | Deliverable |
|-----|------|-------|-------------|
| Mon | Ch1.1 Background + Ch1.2 Problem | Hozaifa | Draft text (500 words) |
| Tue | Ch1.3 Proposed Solution | Hozaifa | Draft text (500 words) |
| Wed | Ch1.4 Thesis Organization | Hozaifa | Draft text (200 words) |
| Thu | Ch1 review + merge | Abdalrahman | Review comments, fixes |
| Fri | Ch2.1 Digital Mental Health | Ahmed | Draft + references |
| Sat | Ch2.2-2.5 (Conversational, Emotion, Gamification, RAG) | Ahmed | Draft + references |
| Sun | Ch2.6 Gap Analysis + Ch2 review | Ahmed + Yahya | Complete draft + review |

### Week 2: Ch3 (System Design) — **Hozaifa + Yahya + Ahmed + Devide/Malak**

| Day | Task | Owner | Deliverable |
|-----|------|-------|-------------|
| Mon | Ch3.1-3.2 Requirements (FR + NFR) | Hozaifa | 10 FR + 5 NFR |
| Tue | Ch3.3-3.5 Diagrams (Use Case, Sequence, Flow) | Hozaifa | Mermaid diagrams |
| Wed | Ch3.6 System Architecture | Hozaifa | Architecture diagram |
| Thu | Ch3.7 AI/ML Pipeline Design | Ahmed | Emotion, RAG, LLM description |
| Fri | Ch3.8-3.9 Data Models + Gamification | Yahya + Abdalrahman | Schemas + gamification |
| Sat | Ch3.10 Security | Devide + Malak | Security considerations |
| Sun | Ch3.11 Hardware + Ch3 review | Hozaifa | Table + full review |

### Week 3: Ch4 (Implementation & Results) — **Abdalrahman + Hozaifa + Ahmed + Yahya**

| Day | Task | Owner | Deliverable |
|-----|------|-------|-------------|
| Mon | Ch4.1 Technology Stack | All | Complete table |
| Tue | Ch4.2 Frontend Implementation | Abdalrahman | Screens, state mgmt, native |
| Wed | Ch4.3 Backend Implementation | Hozaifa + Yahya | Microservices, RAG, assessment |
| Thu | Ch4.4 Chat LLM Integration | Ahmed | Groq, Ollama, Gemma |
| Fri | Ch4.5 Testing | Hozaifa | Unit, integration, UAT |
| Sat | Ch4.6 Results + Charts | Abdalrahman | Charts from real data |
| Sun | Ch4 review + fixes | All | Full review |

### Week 4: Ch5 (Conclusion) + Final Review — **All**

| Day | Task | Owner | Deliverable |
|-----|------|-------|-------------|
| Mon | Ch5.1 Conclusions | Hozaifa | Summary of contributions |
| Tue | Ch5.2 Future Work | Ahmed | 5+ directions |
| Wed | Ch5.3 Ethics | Abdalrahman | Privacy, consent, crisis |
| Thu | Abstract + Acknowledgements | Yahya | Polish |
| Fri | Full formatting pass | All | Consistency check |
| Sat | Supervisor review | Dr. Sahar | Feedback |
| Sun | Final fixes + PDF build | All | Submission-ready |

---

## Writing Workflow

### 1. Before You Start
- [ ] Check `PROGRESS.md` — is your chapter unblocked?
- [ ] Pull latest: `git pull origin main`
- [ ] Read `STYLE_GUIDE.md`
- [ ] Check `TEAM_ASSIGNMENTS.md` for your sections

### 2. While Writing
- [ ] Write in your assigned `.qmd` file
- [ ] Use `@sec-label` for cross-references
- [ ] Use `[@citationKey]` for citations
- [ ] Add Mermaid diagrams where needed
- [ ] Run `quarto render` to verify build

### 3. When Ready for Review
- [ ] Self-review against `STYLE_GUIDE.md`
- [ ] Update `PROGRESS.md` with your status
- [ ] Commit: `git commit -m "[Ch3] Added use case diagram — Hozaifa"`
- [ ] Push: `git push origin main`
- [ ] Notify your reviewer (GitHub comment or WhatsApp)

### 4. Review Process
- [ ] Reviewer reads the section
- [ ] Reviewer adds comments in GitHub Issues or inline
- [ ] Owner addresses feedback
- [ ] Re-commit and re-push
- [ ] Mark ✅ in `PROGRESS.md`

---

## Daily Standup Format

Every day at [agreed time], post in your group chat:

```
Hozaifa:
- Yesterday: Ch3.3 Use case diagram (Mermaid)
- Today: Ch3.4 Sequence diagram
- Blockers: Need Abdalrahman to confirm frontend flow

Abdalrahman:
- Yesterday: Ch1.1 review
- Today: Ch4.2 Frontend screens
- Blockers: None

Ahmed:
- Yesterday: Ch2.2 Conversational agents
- Today: Ch2.3 Emotion recognition
- Blockers: Need a reference on emotion classification accuracy

Yahya:
- Yesterday: Ch2.1 Digital mental health
- Today: Ch2.5 RAG
- Blockers: None
```

---

## Conflict Resolution

1. **Two people edit same file:** Git will show conflicts. The person who pushes first wins, the second person resolves the conflict.
2. **Disagreement on content:** Discuss in daily standup. If unresolved, escalate to supervisor.
3. **Someone is blocked:** Ask in standup. If it's a code dependency, the blocker person prioritizes unblocking.
4. **Missing references:** Add a `[TODO: reference needed]` tag and move on. Fix in the final pass.

---

## Weekly Sync Agenda

Every [agreed day] at [agreed time]:

1. **Review PROGRESS.md** (5 min) — What's done? What's stuck?
2. **Demo PDF** (10 min) — Show the latest rendered PDF
3. **Blocker resolution** (10 min) — Fix dependencies, reassign if needed
4. **Next week plan** (5 min) — Confirm schedule, adjust if behind

---

## Quick Links

- **GitHub Repo:** https://github.com/Upheal1/UpHeal-Doc
- **PLAN.md:** Master plan with milestones
- **PROGRESS.md:** Live tracker
- **TEAM_ASSIGNMENTS.md:** Who owns what
- **STYLE_GUIDE.md:** Writing rules

## Communication

- **Daily standup:** [Group chat — WhatsApp/Telegram/Discord]
- **Weekly sync:** [Video call — Zoom/Google Meet]
- **Code review:** GitHub Issues
- **File sharing:** GitHub (not email!)

---

## Ready to Start?

Reply with your preferred:
1. Daily standup time
2. Weekly sync day/time
3. Communication channel (WhatsApp/Telegram/Discord)

Then Hozaifa + Abdalrahman start Week 1, Ahmed + Yahya start Week 1 (Ch2).

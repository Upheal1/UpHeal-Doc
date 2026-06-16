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

---

## 2026-06-16 — OpenCode (Security Architecture Expansion)

### Changed
- Expanded §3.9 Security Architecture from 3 subsections to 11 subsections
- Added Zero Trust Architecture (ZTA) principle and data asset classification table
- Added detailed cryptographic identity design: OTP engine, PBKDF2 key derivation, constant-time comparison, 3-tier JWT (HS256/ES256/RS256)
- Added on-device harmful content detection layer (AccessibilityService, EdgeThreatDetector, bilingual keyword detection, TFLite toxicity classifier)
- Added visual content safety scanner (periodic screenshots, TFLite image classification, 70% threshold)
- Added service continuity protection (GuardService, BootReceiver, WakeLock, device admin, anti-tampering)
- Expanded clinical safety audit algorithm with input sanitization step
- Added network-level content filtering and AI pipeline security subsections
- Added quantitative security comparison table (baseline vs. hardened)
- Updated §1 Introduction Pillar 4 to reflect multi-layered security architecture
- Updated §3.2 NFR-03 with expanded security targets
- Updated §5.4 Ethics with privacy-by-design edge processing and service continuity ethics
- Updated §5.5 Future Work with Cloudflare WAF, certificate pinning, mTLS, biometric authentication
- Updated §5.6 Limitations with on-device detection, visual scanner overhead, and anti-tampering limitations
- Added 5 new references: NIST SP 800-207 (ZTA), NIST SP 800-38D (GCM), RFC 2898 (PBKDF2), Android AccessibilityService, TensorFlow Lite

### Why
- Three PDFs (Book.pdf, Security Presentation, upheal_security_report.pdf) described a substantially richer security architecture than the thesis contained
- The thesis needed to accurately reflect implemented security features while reframing "parental control" concepts for a mental health application
- Academic integrity required citing standards (NIST, RFC) for cryptographic claims

### Affected Files
- `chapters/01-introduction.qmd`
- `chapters/03-methodology.qmd`
- `chapters/05-conclusions.qmd`
- `references.bib`
- `docs/PROGRESS.md`
- `docs/CHANGELOG.md`

---

## 2026-06-16 — OpenCode (LLM-Focused Architecture Rewrite)

### Changed
- Replaced Chapter 2 (Literature Review) with a condensed, LLM-focused literature review covering:
  - LLMs for mental health: opportunities and risks
  - Empathetic dialogue systems
  - Parameter-efficient fine-tuning (LoRA/QLoRA)
  - Retrieval-Augmented Generation
  - Conversational memory and personalization
  - Emotion-aware context processing
  - Voice and multimodal interaction
  - Prompt/context engineering
  - Safety, privacy, and ethical considerations
  - Research gap and literature-to-architecture mapping
- Replaced Chapter 3 (System Design) with new content focused on the LLM architecture:
  - Research and development methodology
  - Model and technology selection with comparison tables (LLM, ASR, TTS, emotion, vector DB)
  - AI model development: fine-tuning objective, dataset preparation, QLoRA/Unsloth, RAG, prompt engineering
  - Integrated system architecture (Flutter + FastAPI + Supabase + Qdrant + RunPod)
  - Conversation processing flows (shared, text, real-time voice)
  - Backend, database, and cloud integration
  - Personalization loops (history, memory, journal, mood, RAG)
  - Core design decisions
- Updated Chapter 1 Proposed Solution and Thesis Organization to align with Gemma 3 27B IT, QLoRA, Qdrant, Whisper, and Chatterbox
- Updated Abstract and Chapter 5 Summary/Conclusion to reflect the new architecture
- Added transitional note in Chapter 4 that detailed implementation results still describe the initial prototype
- Added 20 new references for transformers, GPT-3, InstructGPT, mental-health LLM reviews, empathetic dialogue, LoRA/QLoRA, MemGPT, wav2vec 2.0, XTTS, F5-TTS, Chatterbox, AI safety, WHO ethics, Gemma 3, Qdrant, and Unsloth
- Generated new matplotlib figures: methodology flow and complete architecture block diagram

### Why
- A new source document (`llm final dec.docx`) describes the intended real architecture centered on a fine-tuned Gemma 3 27B IT model, Qdrant retrieval, and real-time voice interaction
- The thesis needed to reflect the LLM's central role in the system and justify model selection through comparison tables
- Condensation was required to maintain the 35–50 page university constraint (final: 38 pages)

### Affected Files
- `chapters/01-introduction.qmd`
- `chapters/02-background.qmd`
- `chapters/03-methodology.qmd`
- `chapters/04-results-discussions.qmd`
- `chapters/05-conclusions.qmd`
- `index.qmd`
- `references.bib`
- `docs/PROGRESS.md`
- `docs/CHANGELOG.md`
- `chapters/03-methodology_files/figure-pdf/fig-methodology-output-1.pdf`
- `chapters/03-methodology_files/figure-pdf/fig-architecture-output-1.pdf`

---

## 2026-06-16 — OpenCode (Figure Enhancements)

### Changed
- Resized all matplotlib figures to fit within tight page margins:
  - Ch3 methodology flow: 7×6 → 5×5.5 in
  - Ch3 architecture diagram: 8×7 → 6×5 in, compact 3-column layout
  - Ch4 fine-tuning loss: 6×3.5 → 5×3 in
  - Ch4 RAG source distribution: 6×4 → 4.5×3 in with side legend
  - Ch4 voice latency: 6×3.5 → 5×3 in
  - Ch4 response quality: 6×3 → 5×2.8 in
- Reduced font sizes and adjusted label placement for readability
- Added global LaTeX figure scaling (`\setkeys{Gin}{width=0.95\linewidth,keepaspectratio}`) to prevent any figure from exceeding text width
- Fixed duplicated section heading and table numbering in Ch4
- Added acknowledgements from `Acknowledgements.docx`

### Why
- Previous figures were rendered at sizes larger than the text width and appeared clipped in the PDF
- Smaller, consistently scaled figures preserve readability while staying within the 35–50 page budget

### Affected Files
- `_quarto.yml`
- `chapters/03-methodology.qmd`
- `chapters/04-results-discussions.qmd`
- `acknowledgements.qmd`
- `chapters/03-methodology_files/figure-pdf/fig-methodology-output-1.pdf`
- `chapters/03-methodology_files/figure-pdf/fig-architecture-output-1.pdf`
- `chapters/04-results-discussions_files/figure-pdf/fig-finetuning-loss-output-1.pdf`
- `chapters/04-results-discussions_files/figure-pdf/fig-rag-sources-output-1.pdf`
- `chapters/04-results-discussions_files/figure-pdf/fig-voice-latency-output-1.pdf`
- `chapters/04-results-discussions_files/figure-pdf/fig-response-quality-output-1.pdf`

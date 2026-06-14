# Git Branch Strategy for UpHeal Thesis

## Overview

Each chapter/task gets its own branch. All work is done on feature branches, reviewed via Pull Request, then merged to main.

**Main branch:** `main` — only for stable, reviewed content
**Feature branches:** `ch1/introduction`, `ch2/background`, etc. — individual work
**Review branches:** `review/ch1-introduction` — peer review staging

---

## Branch Naming Convention

### Pattern: `ch{chapter-number}/{section-name}`

Examples:
- `ch1/introduction` — Chapter 1: Introduction
- `ch2/background` — Chapter 2: Background (Survey)
- `ch3/methodology` — Chapter 3: Methodology / Theory / Analysis
- `ch4/results` — Chapter 4: Results and Discussions
- `ch5/conclusions` — Chapter 5: Conclusions

### Sub-task branches: `ch{chapter-number}/{section-name}/{task}`

Examples:
- `ch1/background` — Ch1.1 Background and Motivation
- `ch1/problem` — Ch1.2 Problem Statement
- `ch3/rag-pipeline` — Ch3.2 RAG Pipeline
- `ch3/llm-integration` — Ch3.3 LLM Integration

### Review branches: `review/{feature-branch-name}`

Examples:
- `review/ch1/introduction` — Review staging for Ch1
- `review/ch3/methodology` — Review staging for Ch3

### Fix branches: `fix/{feature-branch-name}/{description}`

Examples:
- `fix/ch1/introduction/typos` — Typo fixes in Ch1
- `fix/ch3/methodology/diagrams` — Diagram fixes in Ch3

---

## Branch Mapping

| Task | Branch Name | Owner | Reviewer | Merges Into |
|------|-------------|-------|----------|-------------|
| **Ch1.1 Background** | `ch1/background` | Hozaifa | Yahya | `main` |
| **Ch1.2 Problem** | `ch1/problem` | Hozaifa | Yahya | `main` |
| **Ch1.3 Solution** | `ch1/solution` | Hozaifa | Yahya | `main` |
| **Ch1.4 Organization** | `ch1/organization` | Hozaifa | Yahya | `main` |
| **Ch1 Complete** | `ch1/complete` | Hozaifa | Abdalrahman | `main` |
| **Ch2.1 Digital MH** | `ch2/digital-mh` | Ahmed | Yahya | `main` |
| **Ch2.2 Chatbots** | `ch2/chatbots` | Ahmed | Yahya | `main` |
| **Ch2.3 Emotion** | `ch2/emotion` | Ahmed | Yahya | `main` |
| **Ch2.4 Gamification** | `ch2/gamification` | Ahmed | Yahya | `main` |
| **Ch2.5 RAG** | `ch2/rag` | Ahmed | Yahya | `main` |
| **Ch2.6 Gap Analysis** | `ch2/gap-analysis` | Ahmed | Yahya | `main` |
| **Ch2 Complete** | `ch2/complete` | Ahmed | Hozaifa | `main` |
| **Ch3.1 System Overview** | `ch3/system-overview` | Hozaifa | Abdalrahman | `main` |
| **Ch3.2 RAG Pipeline** | `ch3/rag-pipeline` | Hozaifa | Ahmed | `main` |
| **Ch3.3 LLM Integration** | `ch3/llm-integration` | Ahmed | Yahya | `main` |
| **Ch3.4 Emotion Classifier** | `ch3/emotion-classifier` | Ahmed | Yahya | `main` |
| **Ch3.5 Gamification** | `ch3/gamification` | Abdalrahman | Hozaifa | `main` |
| **Ch3.6 Security** | `ch3/security` | Devide | Malak | `main` |
| **Ch3.7 Data Flow** | `ch3/data-flow` | Hozaifa | Yahya | `main` |
| **Ch3 Complete** | `ch3/complete` | Hozaifa | Ahmed | `main` |
| **Ch4.1 Setup** | `ch4/setup` | Abdalrahman | Hozaifa | `main` |
| **Ch4.2 Emotion Results** | `ch4/emotion-results` | Hozaifa | Ahmed | `main` |
| **Ch4.3 Response Quality** | `ch4/response-quality` | Ahmed | Yahya | `main` |
| **Ch4.4 Retention** | `ch4/retention` | Abdalrahman | Hozaifa | `main` |
| **Ch4.5 Performance** | `ch4/performance` | Hozaifa | Yahya | `main` |
| **Ch4.6 Discussion** | `ch4/discussion` | Abdalrahman | Ahmed | `main` |
| **Ch4 Complete** | `ch4/complete` | Abdalrahman | Hozaifa | `main` |
| **Ch5.1 Conclusions** | `ch5/conclusions` | Hozaifa | Dr. Sahar | `main` |
| **Ch5.2 Future Work** | `ch5/future-work` | Ahmed | Dr. Sahar | `main` |
| **Ch5.3 Ethics** | `ch5/ethics` | Abdalrahman | Dr. Sahar | `main` |
| **Ch5 Complete** | `ch5/complete` | Hozaifa | Dr. Sahar | `main` |
| **Abstract** | `content/abstract` | Yahya | Hozaifa | `main` |
| **References** | `content/references` | Yahya | Ahmed | `main` |
| **Formatting** | `content/formatting` | Abdalrahman | Hozaifa | `main` |
| **PDF Build** | `build/pdf` | Hozaifa | Team | `main` |

---

## Workflow

### 1. Create Branch
```bash
# Create new branch from main
git checkout main
git pull origin main
git checkout -b ch3/rag-pipeline

# Work on your task
# Edit files, add diagrams, write content

# Commit and push
git add .
git commit -m "[Ch3.2] Added RAG pipeline diagram and pseudocode

- Added Mermaid block diagram for RAG pipeline
- Added ProcessClinicalDocuments algorithm
- Added RetrieveClinicalContext algorithm
- Added embedding model specifications table"  
git push origin ch3/rag-pipeline
```

### 2. Create Pull Request
```bash
# Create PR from branch to main
gh pr create --title "[Ch3.2] RAG Pipeline Design" \
  --body "## Changes
- Added RAG pipeline block diagram
- Added pseudocode algorithms
- Added embedding model specs

## Reviewers
- @ahmed-osama (AI/LLM)
- @yahya (RAG/Backend)

## Checklist
- [ ] Diagrams render correctly
- [ ] Algorithms are accurate
- [ ] References are added" \
  --base main \
  --head ch3/rag-pipeline
```

### 3. Review Process
```bash
# Reviewer pulls branch
gh pr checkout 123

# Reviewer comments
gh pr review 123 --comment "Great diagram! But need to add HNSW parameters."

# Author addresses feedback
git add .
git commit -m "[Ch3.2] Added HNSW parameters per review"
git push origin ch3/rag-pipeline
```

### 4. Merge
```bash
# After approval, merge to main
gh pr merge 123 --squash --delete-branch

# Update main locally
git checkout main
git pull origin main
```

---

## Branch Dependencies

```
ch1/background ──→ ch1/problem ──→ ch1/solution ──→ ch1/organization ──→ ch1/complete ──→ main

ch2/digital-mh ──→ ch2/chatbots ──→ ch2/emotion ──→ ch2/gamification ──→ ch2/rag ──→ ch2/gap-analysis ──→ ch2/complete ──→ main

ch3/system-overview ──→ ch3/rag-pipeline ──→ ch3/llm-integration ──→ ch3/emotion-classifier ──→ ch3/gamification ──→ ch3/security ──→ ch3/data-flow ──→ ch3/complete ──→ main

ch4/setup ──→ ch4/emotion-results ──→ ch4/response-quality ──→ ch4/retention ──→ ch4/performance ──→ ch4/discussion ──→ ch4/complete ──→ main

ch5/conclusions ──→ ch5/future-work ──→ ch5/ethics ──→ ch5/complete ──→ main
```

**Rule:** A branch can only merge to main if its parent branch is already merged.

---

## Branch Lifecycle

1. **Create** from `main` (or parent branch)
2. **Work** on your task (commits, edits)
3. **Push** to GitHub
4. **PR** to `main` (or parent branch)
5. **Review** by assigned reviewer
6. **Fix** review comments
7. **Merge** to `main` (or parent branch)
8. **Delete** branch after merge

---

## Commands Cheat Sheet

```bash
# Create new branch
git checkout -b ch3/rag-pipeline

# Switch to main
git checkout main

# Pull latest
git pull origin main

# Push branch
git push origin ch3/rag-pipeline

# Create PR
gh pr create --title "Title" --body "Body" --base main

# Review PR
gh pr checkout 123
gh pr review 123 --comment "Comment"

# Merge PR
gh pr merge 123 --squash --delete-branch

# Delete branch locally
git branch -d ch3/rag-pipeline

# List all branches
git branch -a
```

---

## Quick Links

- **GitHub Repo:** https://github.com/Upheal1/UpHeal-Doc
- **SYNC_PLAN.md:** Writing schedule
- **TEAM_ASSIGNMENTS.md:** Who owns what
- **STYLE_GUIDE.md:** Writing rules

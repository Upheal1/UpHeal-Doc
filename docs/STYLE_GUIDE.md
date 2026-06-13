# Style Guide

## Writing Tone

The thesis should be **formal, academic, and precise**. Use third person throughout. Avoid contractions (don't → do not). Use active voice where appropriate.

- ✅ "The system employs a RAG-augmented pipeline"
- ❌ "We use a RAG pipeline"
- ❌ "The RAG pipeline is used by us"

## Terminology

| Term | Usage | Avoid |
|------|-------|-------|
| UpHeal | Always capitalized, no spaces | upheal, Upheal, Up Heal |
| RAG | All caps, no periods | rag, R.a.g. |
| LLM | All caps | llm, L.L.M. |
| GAD-7 | Hyphenated | GAD7, Gad-7 |
| PHQ-9 | Hyphenated | PHQ9, Phq-9 |
| CBT | All caps | cbt, C.b.t. |
| DBT | All caps | dbt |
| ChromaDB | CamelCase | chromadb, chromaDB |
| Supabase | Capitalized | supabase, SupaBase |
| FastAPI | CamelCase | fastapi, Fast Api |
| Flutter | Capitalized | flutter |
| Groq | Capitalized | groq |
| Gemma | Capitalized | gemma |
| Whisper | Capitalized | whisper |
| DSM-5-TR | Hyphenated | DSM-5, DSM 5 |

## Citation Format

Use IEEE format: `[@citationKey]` in text. Quarto handles the formatting.

Examples:
- "as shown in [@lewis2020rag]"
- "studies such as [@devlin2019bert; @radford2022whisper]"

## Abbreviations

First use: spell out + abbreviation in parentheses. Subsequent use: abbreviation only.

> "Retrieval-augmented generation (RAG) is a technique that... RAG pipelines typically include..."

## Figures and Tables

- Number all figures and tables sequentially
- Use `#fig-label` and `#tbl-label` for Quarto cross-references
- Provide descriptive captions (5–15 words)
- Reference every figure/table in the text before it appears

## Diagrams

- Use **Mermaid** for text-based diagrams (architecture, sequence, flow)
- Use **draw.io** for polished visuals (system architecture, deployment)
- Export draw.io diagrams as SVG or PDF
- Ensure diagrams are readable at 100% zoom in the PDF

## Code

- Inline code: `backticks`
- Code blocks: Use triple backticks with language specifier
- Only include code if it illustrates a key design decision
- Do not include full implementation files

## Numbers and Units

- Use SI units
- Percentages: use the % symbol (e.g., 95%)
- Ranges: use en-dash (e.g., 5–10 ms)

## Section Numbering

Quarto handles numbering automatically. Do not manually number sections.

## Cross-References

- Chapters: `@sec-chapter-name`
- Sections: `@sec-section-name`
- Figures: `@fig-label`
- Tables: `@tbl-label`

## Commit Messages

When committing chapter edits, use the format:

```
[ChX] Brief description — Name

- What changed
- Why it changed
```

Example:
```
[Ch3] Added sequence diagram for chat flow — Hozaifa

- Added Mermaid sequence diagram showing user → Flutter → FastAPI → ChromaDB → LLM
- Reflects actual architecture from codebase
```

## Review Process

1. **Draft:** Owner writes the section
2. **Self-review:** Owner checks against this style guide
3. **Peer review:** Reviewer reads and comments
4. **Revision:** Owner addresses feedback
5. **Supervisor review:** Dr. Sahar Ghanem reviews
6. **Final sign-off:** Marked ✅ in PROGRESS.md

## Common Mistakes to Avoid

- ❌ Using "we" or "I" in the thesis
- ❌ Including subjective opinions without citations
- ❌ Citing Wikipedia or blog posts
- ❌ Using inconsistent terminology
- ❌ Including unreferenced claims
- ❌ Forgetting to update PROGRESS.md after edits
- ❌ Committing without pulling first (merge conflicts)

## Git Workflow

1. `git pull` before starting
2. Edit your chapter
3. Run `quarto render` to verify
4. Update `docs/PROGRESS.md`
5. `git add .` and `git commit -m "[ChX] Description — Name"`
6. `git push`

If you get a merge conflict:
1. `git pull`
2. Resolve conflicts in the file
3. `git add .` and `git commit`
4. `git push`

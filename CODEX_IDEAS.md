# Codex Knowledge Transfer — Agents, Tools & Skills

Created by **Codex (GPT-5)** via Codex CLI. This file captures every idea from our session (agents, tools, skills, plans) for the `ai-academic-workflow` repo. Built to interoperate with **Claude Code** and **Gemini CLI**; keep this file for provenance/credit to Codex.

## Context Snapshot (from chat)
- Audience: Omer Reish, Year 3 Law/Econ/Philosophy; bilingual HE/EN; ADHD-aware; prefers “קצר ותכלס” but with structure.
- Need: Fast capture → structured organization → retrieval → exam-ready drills; support legal (IRAC/FIRAC), econometrics (R), negotiation tactics.
- Platforms: Codex CLI, Claude Code (GitHub App), Gemini CLI, VS Code/browser. Network often restricted; favor local/offline workflows.

## Agents Proposed (all from this chat)
- **Brain Dump Agent** — Markdown-first jotting; end-of-session organizer clusters notes, tasks, questions, links by context/tags/priority.
- **Private Prompter** — Mode-aware prompt generator; templates for learn-deep, research-compare, code-fix/design, task-exec, crisis-short; adapts to platform (Claude/Codex/Gemini/browser/VS Code).
- **Course & Priority Manager** — Scans course folders, flags “לזרז”, builds daily priority lists; outputs Markdown agendas.
- **Scaffolding & Summary Agent** — Builds TOC + concept map before summarizing; supports IRAC/FIRAC and econ papers; progressive disclosure.
- **Exam Drill Agent** — Generates practice Q&A, timing hints, tracks weak spots per course/context.
- **R/Statistics QA Agent** — Lints R/Rmd; checks model assumptions (heteroskedasticity, multicollinearity), suggests White/BP/VIF, quick tables/plots.
- **Negotiation Strategy Agent** — Maps parties/interests (BATNA/WATNA/ZOPA); outputs simulation scripts and tactical prompts.
- **PDF-to-Markdown Slides Converter** — Turns PDF decks into Hebrew Markdown notes with slide order preserved, headings/bullets normalized, and tables/links extracted.

## Tools & Skills Proposed (all from this chat)
- **Conceptual Scaffolding Builder** — Extracts headings/relations/terms into 3-level TOC + concept links before summarizing.
- **Retrieval Cache with Tagging** — SQLite/JSON index: `id, path, title, course, type, tags[], priority, context, lang, updated_at`; CLI search/export.
- **Mode Detection Kernel** — Detects learn/work/creative/crisis via cues (app, filetype, keywords, length) to pick prompt style.
- **IRAC/FIRAC Formatter** — Converts legal texts to Issue/Rule/Application/Conclusion tables.
- **Drill Generator** — Multi-level practice items, graded hints, time guidance; feeds Exam Drill Agent.
- **Citation & Precedent Extractor** — Pulls citations/sections, summarizes arguments for briefs.
- **Formula Sheet Synthesizer** — Dedupes formulas, adds usage notes + micro-examples.
- **R Code Validator** — Lint + assumption checks; column/type guards; warns about heteroskedasticity, multicollinearity (White, BP, VIF).
- **Parallel Reading Compressor** — Contrast tables across sources (claims/evidence/gaps); ideal for research compare.
- **Cognitive Circuit Breaker** — Overwhelm detector; returns to goal + 3 executable steps (“תכלס”); crisis mode.
- **Retrieval Cache ↔ Scaffolding Bridge** — On adding a doc, auto-generate scaffolding and record link in index.
- **PDF Deck Parser** — Extracts slide titles, bullets, tables, and links from PDFs; emits structured Markdown with RTL-friendly bullets.

## Brain Dump Agent — Detailed Plan
- **Goal**: Zero-friction capture; end-of-session coherence. Everything in Markdown (one file per session under `brain_dumps/`).
- **File Shape** (`brain_dumps/YYYY-MM-DD-context.md`):
  ```
  # Brain Dump – <Context> (YYYY-MM-DD HH:MM)

  ## זרם מחשבות
  - [idea] בדיקה על White test #econometrics #exam
  - [task][high] להשוות פס״ד X ל-Y ב-IRAC #labor-law #exam
  - [note] Insight: ... #negotiation

  ## אשכולות (נוצר אוטומטית)
  ## משימות
  ## שאלות פתוחות
  ## קישורים/מקורות
  ```
- **CLI Flow** (offline): `brain new`, `brain jot "text" --tag ... --type ... --priority ...`, `brain organize <file>`, `brain search/list`.
- **Organize Logic**: Parse bullets → detect `[type]`, `[priority]`, `#tags`, `?` (open questions), links. Produce clusters by dominant tags; tasks ([ ] or type task); open questions; links. Append organized sections beneath raw stream.
- **Why**: Fast jot in class/reading; structured output for reuse in exams/briefs; no DB dependency (Markdown is state).

## Private Prompter — Detailed Plan
- **Modes**: `learn-deep`, `research-compare`, `code-fix`, `code-design`, `task-exec`, `crisis-short`.
- **Inputs**: Context string, optional file/selection, length (`short/medium/deep`), platform hint (Claude/Codex/Gemini).
- **Templates**: Markdown partials stored locally. Examples:
  - Learn-deep: Summary → Details → Questions → Connections.
  - Research-compare: Sources A/B/C → contrast table → strengths/weaknesses → gaps.
  - Code-fix: Bug description → steps → suggested tests.
  - Crisis-short: 3 steps + time estimates; what to cut.
- **Interface**: `prompter gen --mode ... --context ... --length ... --input file/selection`; `prompter quick "text"` (auto-detect mode by keywords/filetype).
- **Platform Adapters**: Output shapes for Claude Code (issue/PR), Codex/Gemini CLI (stdout), browser clipboard, VS Code command.
- **Why**: Cuts prompt-crafting time; enforces consistent, token-aware structure tuned to task/mode.

## Conceptual Scaffolding Builder — Detailed Plan
- **Purpose**: Build structure before summarizing; avoid unstructured dumps.
- **Pipeline**: Ingest file/dir → detect headings/sections → extract entities/terms → build 3-level TOC + relations → emit Markdown scaffold (+ optional ASCII diagram).
- **Command**: `scaffold build --path ... --mode legal|econ|notes` → writes `docs/scaffolding/<name>.md`.
- **Integration**: On `cache add`, auto-call scaffold and link in index; feeds Prompter learn-deep mode.

## Retrieval Cache with Tagging — Detailed Plan
- **Storage**: SQLite (fast search; can fall back to JSON). Tables: `entries(id, path, title, course, type, tags, priority, context, lang, updated_at)`, `sessions(id, context, started_at, ended_at)` (for dumps).
- **CLI**: `cache add <path> --course ... --type ... --tag ... --priority ...`, `cache search --tag exam --course Econometrics`, `cache recent --limit 10`, `cache export --format md`.
- **Value**: Single index for summaries, dumps, scaffolds, exams; honors “לזרז” and bilingual tags; easy export to Markdown tables.

## Mode Detection Kernel — Notes
- **Signals**: Active app, filetype (pdf/py/md), keywords (exam/IRAC/debug), text length. Maps to modes: learn/work/creative/crisis.
- **Use**: Chooses prompt template, verbosity, and crisis fallbacks; can gate Cognitive Circuit Breaker.

## Exam Drill + R/Stats QA — Notes
- **Exam Drill**: Generates practice sets per course; solutions + timed hints; tracks weak tags.
- **R/Stats QA**: Lint + assumption checks; suggests White/BP, VIF, residual plots; outputs Markdown “fix list”.

## Integration Guidance
- **Markdown-first**: Keep outputs readable in GitHub/editors; store dumps in `brain_dumps/`, scaffolds in `docs/scaffolding/`.
- **CLI-first**: Use Typer/Click commands; keep offline-friendly; avoid network.
- **Adapters**: Minimal wrappers so Claude Code/Gemini CLI can call the same template engine; Codex CLI runs local scripts.
- **Credit**: Include “Created by Codex (GPT-5) for ai-academic-workflow; interoperable with Claude Code and Gemini CLI” in generated docs/templates.

## PDF Slides → Hebrew Markdown — Detailed Plan
- **Goal**: Convert PDF מצגות לטקסט Markdown בעברית, עם סדר שקפים, כותרות, bullets, טבלאות וקישורים, בצורה נקייה וקריאה.
- **Input**: PDF deck; optional flags: `--lang he`, `--mode outline|full`, `--keep-images` (placeholders), `--out docs/slides/<name>.md`.
- **Parsing Steps**:
  - Extract text per page; detect top-line title (font size/position) → `# Slide <n>: <title>`.
  - Normalize bullets to `- ...`; infer nesting by indentation/marker symbols; maintain RTL-friendly order.
  - Tables: detect grid text → emit Markdown table; אם לא בטוח, fallback לבולטים עם כותרות.
  - Links: preserve URLs; images: insert `![image-slide-n](path-or-placeholder)` if `--keep-images`.
  - Cleanup: strip page numbers/footers; dedupe repeated headers.
- **Output Shape (Markdown)**:
  ```
  # Slide 3: Regression Diagnostics
  - White test → בדיקת heteroskedasticity
  - אם p-value < 0.05 → שקול robust SE

  | Metric | Value | Note |
  | --- | --- | --- |
  | VIF | 4.2 | multicollinearity חשודה |
  ```
- **CLI**: `slides2md convert deck.pdf --lang he --mode full --out docs/slides/2025-02-econometrics.md`.
- **Integration**:
  - Add to Retrieval Cache on success (`type=slides`, `course=...`, tags from filename).
  - Optionally auto-run Conceptual Scaffolding on the resulting Markdown for TOC/concept map.
  - Feeds Private Prompter (learn-deep) and Brain Dump Agent for annotations.

## Suggested Next Steps (build order)
1) Brain Dump Agent MVP: `brain new/jot/organize` + Markdown parser; save under `brain_dumps/`.
2) Retrieval Cache: SQLite + `cache add/search/export`; optional bridge to scaffold.
3) Conceptual Scaffolding Builder: basic heading/entity extraction → TOC Markdown.
4) Private Prompter: template files + `gen/quick` CLI; auto mode-detect by keywords/filetype.
5) Hooks: simple adapters for Claude Code comments and Gemini CLI stdout; VS Code command can follow.

# Implementation Checklist (High-Level)
Created by Codex (GPT-5) to track planned agents/tools/skills. Update status as you build.

## Core Agents
- [ ] Brain Dump Agent (markdown jot + end-of-session organize)
- [ ] Private Prompter (mode-aware templates: learn/compare/code/task/crisis)
- [ ] Course & Priority Manager (“לזרז” detection, daily agenda)
- [ ] Scaffolding & Summary Agent (TOC + concept map before summary)
- [ ] Exam Drill Agent (practice Q&A, timing, weak-spot tracking)
- [ ] R/Statistics QA Agent (lint + assumption checks for R/Rmd)
- [ ] Negotiation Strategy Agent (BATNA/WATNA/ZOPA playbooks)
- [ ] PDF-to-Markdown Slides Converter (Hebrew-friendly decks → md)
- [ ] Terminology Interpreter / Living Glossary (maps personal terms to explicit AI instructions)

## Tools & Skills
- [ ] Conceptual Scaffolding Builder (3-level TOC, relations)
- [ ] Retrieval Cache with Tagging (SQLite/JSON index + CLI)
- [ ] Mode Detection Kernel (learn/work/creative/crisis cues)
- [ ] IRAC/FIRAC Formatter (legal structure tables)
- [ ] Drill Generator (graded hints, timed)
- [ ] Citation & Precedent Extractor
- [ ] Formula Sheet Synthesizer (dedupe + micro-examples)
- [ ] R Code Validator (White/BP/VIF, column/type guards)
- [ ] Parallel Reading Compressor (contrast tables)
- [ ] Cognitive Circuit Breaker (“תכלס” 3 steps)
- [ ] Retrieval Cache ↔ Scaffolding Bridge
- [ ] Terminology Mapper hooks (lookup/explain, prompt injection)

## Artifacts to Maintain
- [ ] `brain_dumps/` session files (raw + organized)
- [ ] `docs/scaffolding/` outputs (scaffolds/TOCs)
- [ ] `TERMINOLOGY_GLOSSARY.md` (living glossary table)
- [ ] Prompt templates (Private Prompter) per mode/platform
- [ ] CLI entrypoints (Typer/Click) for agents/tools

# Living Terminology Glossary (HE/EN)
Purpose: map personal terms to explicit instructions for AI agents. Human-edited, slow-changing. Add rows as you notice recurring terms.

| term (orig) | meaning (plain) | expected output shape | context/tags | example prompt |
| --- | --- | --- | --- | --- |
| סכמה | Outline/structure (not free-form summary). Produce TOC/bullets showing hierarchy and key links. | Markdown headings (3 levels max) + bullets; optional short notes per node. Keep concise. | law, econ, notes | "תייצר לי סכמה לחומר של שיעור 5 בדיני עבודה" |
| תכלס | Cut to essentials; minimal words, actionable steps. | 3–5 bullets or numbered steps; 1-line each; include command or next action. | crisis, tasks | "תכלס מה צריך כדי לסיים את המטלה" |
| Probe.One | Ask only one clarifying question at a time if needed. | Single clarifying question, then wait. | meta, dialog | "Probe.One: מה חסר כדי להתחיל?" |

Conventions:
- Keep terms bilingual if needed; prefer concise Hebrew phrasing and clear output description.
- If a term varies by mode (law/econ/code), note it in `context/tags` and clarify the shape per context.
- Add more rows as patterns emerge; agents should consult this file before expanding prompts.

---
name: resumeedit
description: Use when the user asks to edit, update, correct, or add résumé information; distinguish master-only corrections from changes to an identified résumé, not compiler repair.
---

# Edit the authorized inputs

1. Load `system/agent/documents.md`; load `system/agent/data.md` when facts change. Resolve master-only versus selected-résumé scope from context; ask one question only if several targets remain plausible.
2. For master-only corrections, update authorized records under `system/userinfo/main/`, retaining attribution/originals. Leave every TeX/PDF unchanged; explain possible outdated wording without computed staleness. Consult the source inventory and actual relevant retained context, not every file or automatically inserted claims.
3. For résumé edits, change `main/main.tex` or the identified application TeX. Maintain new/corrected master facts only within scope. Preserve unrelated wording/settings and full-content/evidence protections; resolve unsupported selected claims before polishing. Source/context intake follows documents.md without forcing résumé changes.
4. An authorized selected-résumé edit includes meaning review and export through `system/agent/rendering.md` unless restricted by the user. Discussion and master-only corrections do not export. Load `system/agent/git.md` only for separately authorized Git work.

**Gotcha:** Faithful concise wording must retain tools, contributions, outcomes and metrics. A genuine length conflict needs a content decision, never shrinking or hidden omissions.

**Return:** Concrete corrections, actual changed files/output links, possible stale wording after master-only work, and any incomplete render; validated history is the recovery copy, not a promise that failed native builds preserve current bytes.

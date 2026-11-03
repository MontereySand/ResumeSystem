---
name: resumehistory
description: Use when the user asks for history, a previous version, restore, or undo; distinguish exact read-only PDF retrieval, editable restore/rebuild, and separately authorized Git history.
---

# Retrieve first; restore only as requested

1. Load `system/agent/rendering.md` for file history; use `system/agent/git.md` for Git history/restore. Resolve document/version. Main history is `system/userinfo/main/history/`; application history is under its own directory.
2. Read-only retrieval validates actual record/types/binding and saved PDF hash, then returns exact retained bytes without rendering/current-input changes. Preserve corrupt artifacts rather than blessing them; old filenames/records/provenance remain immutable.
3. An explicitly scoped editable restore validates all archived source/style/PDF hashes, reviews claims against today's master/notes/JD and protects current inputs. Restore selected snapshots, not the master or siblings. Unsupported old content remains retrievable while its active use awaits a material decision.
4. If style differs, create a fresh document-local archived style under the recipe, never roll back shared style. Authorized current restoration force-builds the native output and saves a new `kind:"compiled"` checkpoint with actual current tool/product provenance; an old PDF is not a current compilation. PDF-only requests retrieve history, not replace current output beneath different live source.

**Return:** Exact requested historical bytes or actual restored source/native PDF links, provenance and partial-write limits. Clarify destructive ambiguous undo intent; editable-only restores may trigger native auto-build but are not agent-reviewed renders. Git restore keeps its exact-path/revision/index guards; retrieval authorizes no restore, repair, commit or sibling refresh.

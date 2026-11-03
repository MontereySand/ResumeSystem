---
name: resumerender
description: Use when the user requests compile, build, render, PDF export, or open/live preview of an identified résumé; distinguish build/view from reviewed history checkpoints and read-only review.
---

# Build or preview the selected résumé

1. Load `system/agent/rendering.md` for setup/native build/history and `system/agent/documents.md` for completed-render meaning review. Resolve `main/main.tex` or the identified application source, never the newest file.
2. Use that source's Workshop controls for preview. Main current PDF is `system/build/main/main/main.pdf`; application current PDF is `system/build/system/applications/<company>/<application>/main/main.pdf`. Build/view updates this same file without automatically creating history; discussion/read-only/no-files requests authorize no build.
3. For completed render/export, review meaning, force-build the native current path, inspect actual saved bytes/pages/links/appearance, then save a fresh immutable checkpoint with actual hashes/provenance under the recipe. Main history is `system/userinfo/main/history/`; applications own their history. No adjacent PDF, active receipt or separate export tree.
4. Preserve full supported content/readable settings. On failure keep validated history and owned partial work; native current bytes may have changed and are not automatically ready. Missing prerequisites need the precise scoped handoff, not implicit installation.

**Gotcha:** Compiler success is not factual/visual acceptance. Opening a viewer is not automatic refresh proof; claim refresh only from an observed saved edit or clearly attributed user report.

**Return:** After successful reviewed render, clickable links to both actual current PDF and editable TeX; otherwise identify actual available artifacts and the incomplete step. Include material inspection/UI limits, never a folder-search handoff or stale PDF labelled new.

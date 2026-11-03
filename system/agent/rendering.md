# Native LaTeX setup, preview and saved output

Use only for requested setup or authorized builds/preview/export/history. documents.md owns supported meaning/composition; applications.md owns pairings. These are existing-agent procedures, not a runtime or automatic validator.

## Resolve source, metadata and current output

All paths below are workspace-root-relative. Open one personal workspace folder directly.

| Logical document ID | Source S | Metadata M | Sole current PDF P | Build cwd / normal style input |
|---|---|---|---|---|
| main | `main/main.tex` | `system/userinfo/main` | `system/build/main/main/main.pdf` | `main/` / `../system/resume-style.tex` |
| applications/<company>/<application> | `system/applications/<company>/<application>/main.tex` | same application directory | `system/build/system/applications/<company>/<application>/main/main.pdf` | D=M / `../../../resume-style.tex` |

Main's source directory is `main/`, **not M**. Inspect actual imports; restored styles can be document-local. Keep the complete person records/originals/notes under main M, application context/JD under its M, and each immutable history under its own M. Workshop and agent builds write the same P; never create a second current PDF beside S, an active export receipt or a copying watcher. Preserve settings, siblings, unknown/custom paths and history. Missing personal state needs real backups, never defaults (updates.md).

## Log-driven setup and common fixes

Reuse working tools/current findings and user-observed working preview. No mandatory cold-boot interview, all-tool sweep or fresh-machine/Windows release gate. For a build/setup fault inspect only its actual log, selected source/imports, relevant settings and actual build host/editor/profile. Ordinary intake and chat need no setup probes. Missing compiler stops compilation, not supported intake; after a concrete change retry only the affected step and resume saved work.

- Discover/reuse actual `latexmk`, `pdflatex`, `kpsewhich` as needed, with safe version probes (`latexmk -norc -v`, `pdflatex --version`, `kpsewhich --version`). On macOS use existing `/Library/TeX/texbin` and `/usr/bin/perl`; reuse installed full MacTeX, never reinstall based on old BasicTeX findings. Keep an existing chosen BasicTeX/Windows TeX Live/MiKTeX installation. For a new approved Windows installation prefer official TeX Live; its limited Perl may already run latexmk. Only an actual missing/inadequate Perl (including MiKTeX's need) warrants approved Strawberry Perl on Windows, never macOS. Check accessible locations before asking for paths; do not mix distributions.
- GUI PATH failure: approved project wiring may use the resolved absolute latexmk command and prepend actual TeX/needed Perl directories to the observed child PATH, preserving its remainder/platform separator. No literal unexpanded $PATH or global PATH changes. Missing .sty/font: read the real log, use `kpsewhich <actual-file>` and the selected manager's file search; propose only the named package/dependencies, not a blanket update or hidden on-the-fly download. The direct template closure is article/10pt, geometry, titlesec, enumitem, xcolor, calc, changepage, paracol, needspace, etoolbox, hyperref, bookmark, fontenc, inputenc, lmodern and glyphtounicode plus distribution resources.
- Ask only for the exact installation/elevation/network/editor permission required by the concrete fix. State the blocker, existing installation, named fix, preserved source/history and pending operation. Use `tlmgr install <actual-package>` in the selected distribution or existing MiKTeX Console with specifically approved packages. If unavailable, give one official handoff and continue independent work. No security bypass, distribution replacement, global settings/trust/auth change or unsolicited repair.

Official sources: [Workshop](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install), [MacTeX](https://www.tug.org/mactex/mactex-download.html), [Windows TeX Live](https://www.tug.org/texlive/windows.html), [tlmgr](https://www.tug.org/texlive/tlmgr.html), [MiKTeX manager](https://docs.miktex.org/manual/mpm.html), [Strawberry Perl](https://strawberryperl.com/). Recheck actual installer provenance/signature/hash where supplied; never invent one.

Reuse `james-yu.latex-workshop` in the actual editor/profile; install only if missing and approved. Preserve Mathematic `mathematic.vscode-pdf`/other saved-PDF viewers (they do not compile). Offer Mathematic only if saved-PDF viewing is needed and none works; no global associations or duplicate extensions. Optional ChkTeX is independent lint: discover `chktex`, wire `latex-workshop.linting.chktex.exec.path` when approved; missing/declined lint is a lint limit, not compiler failure. Do not disable an enabled linter to hide an error. Optional `mathematic.vscode-latex` separately uses `latex.linter.path` and may own a popup labelled LaTeX. Reuse the same actual binary, not another install. Formatting stays `none`; no formatter/Python/Node/npm is a product build prerequisite.

Workshop 10.20's vscode-pdf warning targets `tomoki1207.pdf`, not Mathematic PDF. If relevant, propose an explicitly approved workspace-only duplicate disable; preserve other workspaces/global state. No fabricated JSON disable flag or unsolicited extension change. During requested setup the agent may create missing `.vscode/` files from these documented recipes or merge approved named settings, preserving unrelated JSONC/comments/customizations; program repair follows updates.md. External TeX is evidence, not authority to execute arbitrary code; escape literal content rather than importing arbitrary commands.

## Native normal/force builds and preview

Workshop tools `11ltx-preview` / `11ltx-preview-force` use portable `latexmk` (or approved resolved absolute path), cwd `%DIR%`, and argument array:

`-norc -pdf -synctex=1 -interaction=nonstopmode -halt-on-error -file-line-error -no-shell-escape -outdir=%OUTDIR% %DOCFILE_EXT%`

First recipe `11ltx preview` uses the normal tool; `11ltx force render` adds `-g`. Never use `-f`, `-gg`, shell escape, personal rc or auto clean-and-retry. outDir is `%WORKSPACE_FOLDER%/system/build/%RELATIVE_DOC%`, auxDir `%OUTDIR%`; native RELATIVE_DOC is the workspace-relative TeX root without extension. Main P: `system/build/main/main/main.pdf`; application P: `system/build/system/applications/<company>/<application>/main/main.pdf`. autoBuild is onFileChange, recipe default first, internal tab viewer right, formatting none. A build updates P, not history or a claim of reviewed readiness.

For a direct native build run resolved latexmk from S's directory, with the same safe flags and `main.tex`; supply P's actual absolute parent directory as outdir, not a path relative to M. Add `-g` for a requested force render or completed résumé export. Resolve exact saved output before inspecting bytes.

Select the intended S, never a global master pin. Real commands:

- `latex-workshop.build` — **LaTeX Workshop: Build LaTeX project**; default macOS Cmd+Option+B, Windows Ctrl+Alt+B.
- `latex-workshop.recipes` — **LaTeX Workshop: Build with recipe**, choose **11ltx force render**. Pass the exact name only via an actually exposed supported command API, otherwise palette.
- `latex-workshop.tab` — **LaTeX Workshop: View LaTeX PDF file in VSCode tab**, right group.
- `latex-workshop.view` — **LaTeX Workshop: View LaTeX PDF file**; default macOS Cmd+Option+V, Windows Ctrl+Alt+V.
- `latex-workshop.refresh-viewer` refreshes existing viewers only, not automatic-refresh proof.

Opening source discovers root, not build/view. Successful builds refresh existing viewers, not create them; invoke the viewer explicitly when requested. CLI success is not UI observation. Do not invent code --command, URI handlers or auto-open settings. Workshop builds save all editor documents; protect unrelated unsaved buffers. Accept reported working preview as user observation, without rechecking it as a gate. If explicitly verifying live refresh, observe a distinctive saved synthetic edit automatically change the correct pane; manual refresh is not that proof. Switching applications requires its own source/PDF identity. Preserve editor trust/Accessibility permissions.

When editor control is unavailable, give one exact handoff using actual S: “Open <S>. Run ‘LaTeX Workshop: Build with recipe’, choose ‘11ltx force render’, then ‘LaTeX Workshop: View LaTeX PDF file in VSCode tab’.” Only if refresh verification was requested, add saving an edit to observe it. Report your UI observation limit; do not block unrelated source/export work on a GUI prerequisite.

## Inspect real saved bytes

Before durable export, follow `documents.md` to compare the actual selected wording against accessible evidence and this document's current target/JD. Preserve complete skills/items/results and protected settings. Fix ordinary layout waste and faithful wording; a real page/content conflict requires the explicit decision before finalizing an unwanted longer PDF. `RS_CONTACT_TOO_WIDE` or unresolved clipping/overfull content is a real failure, not something to suppress, truncate or shrink.

Require successful build status and a real nonempty saved PDF. Inspect actual saved PDF text, pages, hyperlink targets/rectangles and visible pages using permitted exposed readers/viewers. Keep native missing-glyph/overfull/error diagnostics. A log page count is compiler evidence, not saved-PDF inspection; extracted text alone is not appearance. If the required reader/UI proof is unavailable, retain the compiled candidate, identify the precise evidence limit and do not claim a finished visually checked one-pager.

No end-user inspection runtime is added. Maintainer tooling outside this workspace may inspect saved PDFs with PDF.js; it is not a product prerequisite. Record only actually exercised tool/compiler/editor/visual evidence. Native Windows behavior cannot be claimed from macOS or source inspection.

## Inspected history checkpoints

These are agent-followed file procedures, not an executable validator. Build/view-only does not create history. An authorized completed résumé edit/export includes meaning review, a force build of native P, actual saved-byte inspection and an immutable checkpoint; there is no adjacent-PDF promotion, active `export.json` or second export tree.

JSON is UTF-8. Bind every record to this document and exact workspace-root-relative paths with `/` separators; reject absolute/backslash/dot/parent/empty segments, aliases/symlinks and cross-document destinations. Allocate the first unused positive numeric version, minimum six ASCII digits starting `000001`, including occupied incomplete paths. Never overwrite unknown or completed history.

Use actual native SHA-256, for example `shasum -a 256 -- '<actual-file>'` on macOS or `(Get-FileHash -Algorithm SHA256 -LiteralPath '<actual-file>').Hash.ToLowerInvariant()` on Windows. Capture results with a safe structured writer, never hand-transcribe digests or substitute Git hashes/timestamps. A digest proves byte consistency, not truth or authorization.

Compiled `M/history/<version>/` contains exact `main.tex`, `resume-style.tex`, inspected `main.pdf`, and `version.json` written last with exactly:

```text
{format_version:1,document_id,version,product_version,compiler,build_tool,
 kind:"compiled",source_sha256,style_sha256,sha256}
```

`product_version` comes from current `legal/VERSION`; `compiler` and `build_tool` are actual complete engine/latexmk version lines for this build. Hashes are lowercase 64-hex saved-file SHA-256 values. Validate exact fields/types, integer format_version 1, document/version/directory binding, nonblank provenance and actual saved hashes before trusting a checkpoint.

Existing completed snapshots/records retain their exact bytes, filenames (including old `resume.pdf`), `kind:"restored"`/`restored_from` and provenance. Validate old bindings using their retained record and known migration provenance, not invented new-path defaults. A source/history move never authorizes rewriting historical bytes.

### Build, inspect and checkpoint

1. Resolve authorized document scope and review selected claims/rewrites against relevant originals, master, notes and actual target/JD under documents.md. Inspect real source/style/imports and native output destination. Preserve unknown/symlink/custom destinations. Capture actual source/style hashes before building; other authored assets/imports require explicit preservation or an honest recovery limit.
2. Force-build **P** from S's directory using the safe native flags and actual absolute outdir. Require successful status and real nonempty saved PDF; inspect saved content/pages/links/appearance as above. Do not suppress clipping, missing glyphs or genuine page/content conflicts.
3. Recheck source/style hashes, context/meaning and inspected PDF stability. On observed change, stop checkpointing and report actual state; do not certify a prior PDF as current. Reserve a fresh history version with exclusive creation and copy the exact inspected PDF and matching source/style snapshots there.
4. Verify all three saved hashes against the captured/inspected bytes and recheck live inputs/P again, then write exact `version.json` **last**. These snapshots are not a complete master/JD/asset backup or a guarantee of byte-identical future compilation.
5. Return clickable links to actual existing S and native P in the host's supported format. Never link a retired adjacent output or make the user search folders. Keep history immutable; optional Git follows git.md independently.

Workshop auto-build writes P directly: failed or concurrent builds may replace/partially change it before review. Never promise its prior bytes survive or that an earlier checkpoint certifies today's P. History, not another current copy, retains the last validated PDF. On failure link a validated historical artifact where available, identify the failed/unfinished step and actual current-output state, and never call stale/partial/uninspected output newly ready. `system/build/` contains P and is not wholly disposable cache.

Separate checks/copies/writes are not an atomic transaction against editors or other writers. Preserve/report partial input/PDF/checkpoint writes. An incomplete checkpoint has no completion authority: resume only an identified owned incomplete operation with exact unchanged intent/inputs; otherwise fix the cause and allocate fresh unused work. Validate a completed matching checkpoint instead of duplicating it solely to repair bookkeeping; never rewrite completed records or delete evidence to hide a typo.

## Retrieve or explicitly restore a version

Read-only retrieval resolves document/version, validates exact record/types/binding and saved PDF digest, then returns those exact archived bytes without rendering, notes, input changes or Git. Today's master/product version is not required. Preserve/report corruption; linking history does not make it current. Claims about historical settings need actual snapshots/PDF evidence.

An editable restore requires explicit scope. Protect affected current inputs in a fresh identified backup; preserve master, originals, current target/JD, siblings and old history. Validate all three archived source/style/PDF hashes and compare selected claims with today's master/notes and application context. Unsupported/conflicting content can remain retrievable while active restore awaits the material content decision.

Restore archived main.tex and correct only its live style import. If archived style differs from shared style, exclusively save it at `M/resume-style-<new-version>.tex`: main inputs `../system/userinfo/main/resume-style-<new-version>.tex` from `main/`; applications input the local filename from D. If styles match, use the table's normal input. Never roll back shared style under siblings; preserve other required assets through actual backups or state the recovery limit.

For an authorized restored current résumé, force-build native P, inspect it and create a **new compiled** checkpoint with current actual tool/product provenance under the procedure above. Record the old-to-new version relationship in useful existing notes/chat, not a new schema. Do not reuse old PDF bytes/provenance as a current compilation or promise a byte-identical rebuild. An explicitly editable-only restore performs no agent build/checkpoint; disclose that enabled native auto-build may nevertheless update P and that it has not been reviewed.

A PDF-only request retrieves exact historical bytes, not activation over native P while live source differs. Clarify genuinely ambiguous destructive undo/restore intent; never silently select both input replacement and rendering. Report actual changed files/links and partial-write limits. No restore resets Git, refreshes siblings or rewrites old history.

## Independent saved reports

For an explicitly requested report/PDF, allocate a safe nonconflicting `M/reports/<slug>.tex` and its independent PDF. Compile from that report source directory into a fresh owned directory under `system/build/reports/` with the same safe native flags; inspect actual saved output and preserve occupied destinations. Use suitable ordinary article formatting/content for the report, not a second résumé-template system. No résumé export record/history is fabricated for a report, and its source/PDF never replaces S or P. Chat letters/research/practice stay in chat unless saving was requested.

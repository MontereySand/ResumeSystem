# Workspace guide

Open the complete personal workspace root containing `AGENTS.md`, not `main/`, `system/` or `legal/`. The existing agent edits LaTeX directly; no generated-content renderer or user Node/Python runtime exists.

## First run

Say **“Let's get started”** with your résumé attached, or start from experience. The agent reads the actual material, keeps its original, retains all supported career facts, composes `main/main.tex`, compiles/reviews the output and links both the PDF and TeX in chat. Existing records are reused, not reset; an incomplete career intake gets only the next useful question.

If setup fails, the agent reads the actual log and reuses installed tools. It fixes approved project wiring or asks for the specific package installation/elevation/permission needed, preserves your work and resumes. It does not ask you to install everything or repeat intake. On macOS reuse MacTeX and `/Library/TeX/texbin`, not Strawberry Perl. Windows TeX Live/MiKTeX may need Perl only when its actual build tool requires it. ChkTeX is optional lint.

After a successful export, expect **“Your résumé is ready”** with clickable links to the actual saved PDF and editable `.tex`, using your host's supported file links. Failed compilation is reported honestly, not linked as a new successful PDF. A preview-only or master-only request does not quietly export.

## Folders and moving them

| Location | What it does | Can it move? |
|---|---|---|
| `main/` | Your editable `main.tex` | Move with the whole workspace; source depends on the sibling system style. Current PDF is under `system/build/`. |
| `system/userinfo/main/` | Complete `facts.json`, source/context inventory in notes, saved preferences, originals and PDF history | Keep its internal paths, or request an agent-managed migration. |
| `system/userinfo/main/source/` | Immutable originals or honestly labelled text-only evidence/context | Preserve; moving files requires updating their attributed references. |
| `system/userinfo/main/history/` | Exact validated PDFs, input snapshots and provenance | Preserve completed bytes/records; these are historical versions, not additional current outputs. |
| `system/applications/` | Independent company/role TeX, job originals/context and history; created when needed | Move with the workspace. Renaming an application needs identity/path migration. Its current PDF is under `system/build/`. |
| `system/skills/` | Twelve canonical task instructions | Keep this path for root routing and native delegates. |
| `system/agent/` | Detailed on-demand evidence, build, export, history, repair and Git procedures | Keep this path unless all references are migrated. |
| `system/testing/` | Optional read-only setup diagnosis | Referenced by guide/repair; no test runner is required by users. |
| `system/build/` | The sole current PDF per document plus regenerable TeX auxiliaries | Main is `system/build/main/main/main.pdf`; do not clear the whole tree as disposable cache. Validated prior PDFs remain in history. |
| `system/checks/` | Private inspection/migration evidence in the owner's worked copy; not shipped | Not needed to compile; retain it if you want those verification/provenance records. |
| `legal/` | This detailed guide and edition VERSION | Keep the paths used by instructions/repair. README and LICENSE stay at the root for discovery. |
| `.vscode/` | Project build, force-render and live-preview settings | Must stay at the opened root for VS Code discovery. Shipped for immediate use; the agent can create/repair approved settings. |
| `.omp/` | Optional OMP slash-command delegates; absent from the clean download | Only OMP needs it for those shortcuts. Normal requests/builds still work without it. The agent can recreate requested missing entries. |
| `.claude/`, `.pi/`, `.agents/` | Equivalent requested native integration for the actual selected host | Not bundled together; each host expects its own root location. |

**The complete workspace can move or be renamed.** Internal references are workspace-relative; machine-specific TeX paths may need setup repair on a different machine/OS. Moving one internal folder independently is different: ask the agent to migrate imports, references and records. Root `AGENTS.md`, `.gitignore` and `.gitattributes` stay where their tools discover them.

## Preview

Open [main/main.tex](../main/main.tex). In the Command Palette:

1. **LaTeX Workshop: Build with recipe** → **11ltx force render**.
2. **LaTeX Workshop: View LaTeX PDF file in VSCode tab**.
3. Save edits to rebuild/refresh the open preview.

Normal build: Cmd+Option+B / Ctrl+Alt+B. PDF view: Cmd+Option+V / Ctrl+Alt+V. Main's sole current PDF and preview are `system/build/main/main/main.pdf`. A terminal compile does not itself open the viewer. Save builds can change this file before review; validated history is the recovery copy. No formatter or duplicate preview extension is required.

## Agent and shortcuts

Root [AGENTS.md](../AGENTS.md) makes this a résumé workspace: the agent reads only the relevant skill/procedures, operates permitted tools, preserves complete facts and returns useful results. It is guidance to your chosen agent, not another model or an enforcement runtime. Host loading, capabilities and higher-priority instructions still matter. If the host does not load root guidance, ask once: **“Read AGENTS.md and follow it for this request.”**

Ask **“Set up résumé commands for this agent.”** Claude Code/OMP/Pi can expose `/resumerender` and `/repair`; Codex uses its picker or `$resumerender`/`$repair`. Only actual-host missing entries are created; custom/built-in collisions are preserved. Root guidance and normal language work without shortcuts. `.vscode/` is kept in the clean download so preview defaults do not depend on an agent first inventing configuration.

## History, Git and limits

Ask for a previous PDF to retrieve its exact saved bytes; request an editable restore explicitly. Repair can recover missing program files from a trusted compatible source, not recreate lost personal data. One readable page means faithful writing and sensible layout, never hidden skill loss or shrinking.

Git is optional local input history, not off-device backup. Enable it only in an independent personal copy outside this publisher/ancestor repository. Only approved editable files/source pairs are checkpointed; PDFs/history are a separate archive. No automatic commit, remote or push; “no Git” forbids even probes. The chosen agent/provider may access local files/history.

See [setup diagnosis](../system/testing/DIAGNOSE.md), root [README](../README.md) and the preserved [MIT license](../LICENSE). TeX distributions/extensions/fonts retain their own licenses; they are not bundled here.

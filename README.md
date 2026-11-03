# 11LTX: LaTeX template + AI skills

Edit your résumé with the AI in your code editor. One v1-style LaTeX template, a complete career information pack, and skills that guide the agent. No separate renderer.

## Setup

1. Download **Source code (zip)** from the [project releases](https://github.com/MontereySand/ResumeSystem/releases), extract it and open the complete extracted folder in VS Code or a compatible editor.
2. Keep your usual agent in the CLI or side panel. If needed, tell it: **“Read AGENTS.md and follow it for this request.”**
3. Reuse your TeX installation: [MacTeX](https://www.tug.org/mactex/) on macOS or [TeX Live/MiKTeX](https://www.latex-project.org/get/) on Windows. Ask the agent to fix the actual setup problem before installing extra tools.
4. Use [LaTeX Workshop by James Yu](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) for build/live preview. Project settings are included.

## Use

- Attach your résumé and say **“Let's get started”**, or start from experience.
- Editable résumé: [main/main.tex](main/main.tex). The current PDF is `system/build/main/main/main.pdf`, the same file Workshop previews; the agent links **both files in chat** after a successful reviewed render.
- Describe edits, ask **“tailor this for this company”**, **“open preview”**, **“history”** or **“repair.”** Supported content is preserved, not shrunk or silently cut to fit.
- Company versions live in `system/applications/`; complete user information, original documents, context notes and validated PDF history live in `system/userinfo/main/`.
- Optional native shortcuts: **“Set up résumé commands for this agent.”** Normal language works without them.

Open the source, run **LaTeX Workshop: Build with recipe → 11ltx force render**, then **View LaTeX PDF file in VSCode tab**. Save edits for live refresh. On a setup failure, the agent reads logs, requests only the permission needed and resumes.

[Folder/moving guide](legal/GUIDE.md) · [Agent instructions](AGENTS.md)

By Aditya Maramreddy, Henish Patel, and Riley Young. Thanks to James Yu for LaTeX Workshop. First-party license: [MIT](LICENSE); installed TeX/fonts/extensions keep their own licenses. No personal files or TeX binaries are bundled.

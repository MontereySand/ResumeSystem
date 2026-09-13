# Agent Collaboration Protocols & Operational Framework

This document dictates how AI agents interact with the user, resolve dynamic paths, write and compile LaTeX, and coordinate skills across the workspace.

---

## 1. Core LaTeX Standard & Mandatory Compilation Gate

All resume files in this workspace are powered by **LaTeX / pdfLaTeX**. Agents must treat LaTeX compilation and document integrity as non-negotiable operational requirements:

1. **Always Write Native LaTeX:** NEVER bleed Markdown formatting (`**bold**`, `_italic_`, `[link](url)`, markdown tables) into `.tex` files. Always use valid LaTeX macros (`\textbf{}`, `\textit{}`, `\href{}{}`, etc.).
2. **Compilation is Mandatory:** Every modification to `/Resume/User/main.tex` or any company-tailored resume (e.g., `/Resume/[Company]/main.tex`) MUST be compiled via shell:
   ```bash
   pdflatex -interaction=nonstopmode main.tex
   ```
3. **Verification Criteria:** An edit is NOT complete until the agent confirms:
   - The compiler exited with code `0`.
   - The compiled PDF is **strictly 1 page**. If the content spills onto page 2, the agent must pull back content (enforcing the 14-bullet ceiling) and recompile immediately.
   - Zero Overfull `\hbox` warnings.
   - Auxiliary build artifacts (`main.aux`, `main.log`, `main.out`) are cleaned up after verification.

---

## 2. Single-Line Date Invariance Protocol

Month and year / date ranges must **ALWAYS remain on the exact same line**:
- **Prohibited Behavior:** Under no circumstances should a month and year split across lines (e.g. `October` on line 1 and `2025 -- Present` on line 2).
- **Native Implementation:** Date ranges in `main.tex` and any tailored files must be enclosed in an unbreakable box with non-breaking spaces:
  ```latex
  \mbox{\textbf{Month~20XX~--~Present}}
  \mbox{\textbf{Month~20XX~--~Month~20XX}}
  ```
- **Column Calibration:** The date column in `twocolentry` is calibrated to `5.2 cm` to comfortably accommodate full month names (e.g., `September 20XX -- November 20XX`) on a single line.
- **Visual Inspection:** During the post-compile review, verify that no date entry wraps onto multiple lines.

---

## 3. Dynamic Path Resolution & Template Filling

Agents MUST dynamically discover, resolve, and inject workspace paths into skills during execution:
- **Core Master Resume:** `/Resume/User/main.tex`
- **Tailored Output Directory:** `/Resume/[TargetCompany]/` (e.g., `/Resume/Microsoft/main.tex`, `/Resume/Google/main.tex`)
- **LinkedIn Profile Description:** `/Resume/User/Linkedin.txt`
- **Preparation & Interview Notes:** `/Resume/[TargetCompany]/[company]_screening_prep.md`
- **Skills Directory:** `Resume/Skills/`

> **Template Filling Rule:** The master `/Resume/User/main.tex` is intentionally designed as an open-source template filled with styled Lorem Ipsum and `X`-metrics. When an agent updates or tailors the resume with real user experience, it must replace the placeholder text with the user's truthful details while strictly preserving the typographic formatting (`\textbf{}`, `\textit{}`, `(\textbf{...})`) and bullet count ceiling (14 max).

---

## 4. Initialization & Workflow Routing Protocol

At the start of ANY session, determine the user's immediate goal and activate the corresponding workflow:

| Workflow | Primary Skill File | Target Path | Description |
| :--- | :--- | :--- | :--- |
| **1. Update Master** | *Core LaTeX Directives* | `/Resume/User/main.tex` | Update baseline experience, education, skills, or projects. |
| **2. Tailor Resume** | `Resume/Skills/Tailor.md` | `/Resume/[Company]/main.tex` | Role research, gap analysis, tech stack swaps, 14-bullet ceiling, PDF compile. |
| **3. Interview Prep** | `Resume/Skills/Preparation.md` | `/Resume/[Company]/prep.md` | Hero project pitch, steering tactics, anticipated technical deep-dives. |
| **4. Cover Letter** | `Resume/Skills/Coverletter.md` | Chat / Company Folder | Match analysis, high-signal company alignment, clean text format. |
| **5. Technical Breakdown** | `Resume/Skills/Breakdown.md` | Chat / Audit Notes | Adversarial jargon glossary (Definition, Nuance, Audit Question). |
| **6. LinkedIn Generation** | `Resume/Skills/Linkedin.md` | `/Resume/User/Linkedin.txt` | De-fluffed, metric-dense experience extraction with clean formatting. |
| **7. Humanize Writing** | `Resume/Skills/Humaizer.md` | Text / Docs | Remove AI patterns, inflate soul, and eliminate generic filler. |
| **8. Project Bank Swaps** | `Resume/Skills/Projects.md` | `main.tex` | Select and swap project entries from the Project Archetype Bank. |
| **9. Company Research** | `Resume/Skills/Research.md` | `current.md` | First-principles investigation of company tech stack & engineering blogs. |
| **10. Format Promotions** | `Resume/Skills/Promotion.md` | `main.tex` | Multi-role internal progression formatting with visual elbow connectors. |

---

## 5. Comprehensive & Prioritized Skill Registry

### Tier 1: Core Resume Operations
1. **`Resume/Skills/Tailor.md` (Top Priority)**
   - 4-Phase interactive tailoring pipeline: Sub-Agent Research $\to$ Gap Analysis $\to$ Concise User Approval $\to$ Surgical LaTeX Implementation.
   - Strict 14-bullet maximum ceiling (prevents 2-page overflow).
   - Mandatory whitespace fill order (split dense bullets, expand secondary experience).
   - Mandatory `pdflatex` compilation and single-line date verification.
2. **`Resume/Skills/Promotion.md`**
   - Professional formatting for multi-role internal promotions within the same company.
   - Visual elbow line pattern (`$\llcorner$` / `\elbowbranch`) connecting parent company tenure to promoted titles.
   - Prevents ATS job-hopping false flags and preserves single-line date alignment.
3. **`Resume/Skills/Preparation.md`**
   - Company profiling (architectural focus, culture).
   - "Hero" Project selection aligned to company stack.
   - 3-sentence elevator pitch & behavioral steering tactics.
   - Top 3 anticipated technical deep-dive audit questions.
4. **`Resume/Skills/Coverletter.md`**
   - Generates high-signal, fluff-free cover letters matching specific job descriptions.
   - Emphasizes real project architecture, local residency/connection, and role relevance.

### Tier 2: Asset & Profile Refinement
5. **`Resume/Skills/Breakdown.md`**
   - Master architectural breakdown for all resume sections (Header, Contact, Education, Skills, Experience, Projects, Awards, Leadership, Certifications, Publications, Coursework).
   - Adversarial Technical Auditor: Extracts technical jargon and applies the Three-Sentence Rule (Definition, Senior Nuance, Audit Question).
6. **`Resume/Skills/Linkedin.md`**
   - Extracts resume experience into bulleted, metric-dense LinkedIn descriptions without lead-in titles or section headers.
   - Saves formatted output to `/Resume/User/Linkedin.txt`.
7. **`Resume/Skills/Humaizer.md`**
   - Comprehensive Wikipedia-backed AI cleanup guide (v2.8.2).
   - Eliminates inflated symbolism, superficial `-ing` analyses, negative parallelisms, em dash overuse, and robotic sentence rhythms.

### Tier 3: Strategic Knowledge & Evidence Banks
7. **`Resume/Skills/Research.md`**
   - First-principles research standards: accuracy over agreement, skepticism of hype, trade-off analysis, reputable sources.
8. **`Resume/Skills/Projects.md`**
   - Curated catalog of reusable Project Archetypes (Distributed Systems, Kubernetes Operators, Real-Time Platforms, Ledgers, Networking Tools) with domain swap matrices.

---

## 6. Operational Guardrails

1. **Safe Versioning Protocol:** NEVER modify or overwrite `/Resume/User/main.tex` during a tailoring workflow. Always fork to a dedicated `/Resume/[TargetCompany]/` directory.
2. **Strict Single-Page Constraint:** Keep output to exactly one page. Never present a resume that has visible unused whitespace or spills onto a second page.
3. **Single-Line Date Discipline:** Dates must always be formatted on a single line. Never allow months and dates to wrap.
4. **Truth Preservation:** Never invent metrics, employers, users, scale, or skills. When a skill or detail is missing, ask the user directly and concisely before adding it.
5. **Subagent Deployment:** Deploy subagents (e.g., `generalist`) or web search tools to discover up-to-date company architecture, engineering blogs, and technology stacks.

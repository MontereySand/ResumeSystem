# Promotion & Internal Progression Formatting Skill

This skill governs how to cleanly format internal promotions, title progressions, and role transitions within the same company on a single-page LaTeX resume without confusing ATS parsers or breaking the 14-bullet ceiling.

---

## 1. The Strategic Value of Promotion Formatting

When a candidate is promoted within a company (e.g., Software Engineer $\to$ Senior Software Engineer, or AI Systems Intern $\to$ Full-Time Engineer):
1. **Demonstrates High Performance & Retention:** Signals to recruiters that past managers recognized and rewarded exceptional impact.
2. **Eliminates "Job Hopping" False Flags:** If entered as separate company entries, ATS algorithms or rushed recruiters may misinterpret the candidate as hopping jobs every 6–12 months.
3. **Saves Vertical Page Space:** Grouping multiple titles under a single parent company header preserves 1–2 vertical lines, critical for maintaining the strict 1-page budget.

---

## 2. The Visual "Elbow Line" Pattern

To clearly indicate a hierarchical promotion tree without adding bulky text, use a clean visual elbow connector (`└──` or `$\llcorner$`):

```
Company Name, Location                            [Total Tenure: 2022 -- Present]
└── Senior Software Engineer                      [Promoted Date: 2024 -- Present]
    • Bullet 1 (Increased scope, technical leadership, X% impact)
    • Bullet 2 (Architecture, mentoring, sub-Xms performance)
└── Software Engineer                             [Initial Date: 2022 -- 2024]
    • Bullet 1 (Core feature development, foundational architecture)
```

---

## 3. Production-Ready LaTeX Implementation

### Pattern A: Clean Mathematical Elbow Connector (`$\llcorner$`)
This method uses standard mathematical symbols available in standard pdfLaTeX without needing external TikZ packages:

```latex
% --- 1. Parent Company Header (Total Company Tenure) ---
\begin{twocolentry}{\mbox{\textbf{June~2023 -- Present}}}
    \hspace*{0.1cm} \textbf{\href{https://example.com}{TechCorp Industries}}, San Francisco, CA
\end{twocolentry}
\vspace{0.02 cm}

% --- 2. Promoted Role (Most Recent) ---
\begin{twocolentry}{\mbox{\textit{Jan~2025 -- Present}}}
    \hspace*{0.35cm} \raisebox{0.1ex}{$\llcorner$}\hspace{0.15cm} \textbf{Senior Software Engineer}
\end{twocolentry}
\vspace{0.015 cm}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0.6cm + 10pt, labelsep=5pt]
        \item Promoted to lead technical architecture across \textbf{X+} microservices, reducing end-to-end latency by \textbf{X\%}
        \item Mentored \textbf{X} junior engineers and established automated CI/CD validation pipelines
    \end{itemize}
\end{onecolentry}

\vspace{0.025 cm}
% --- 3. Initial Role (Previous) ---
\begin{twocolentry}{\mbox{\textit{June~2023 -- Dec~2024}}}
    \hspace*{0.35cm} \raisebox{0.1ex}{$\llcorner$}\hspace{0.15cm} \textbf{Software Engineer}
\end{twocolentry}
\vspace{0.015 cm}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0.6cm + 10pt, labelsep=5pt]
        \item Engineered real-time ingestion layer with sub-\textbf{Xms} processing latency for \textbf{X,XXX+} active streams
    \end{itemize}
\end{onecolentry}
```

### Pattern B: Rule-Based Visual Branch Connector
For candidates desiring a crisp geometric tree line:

```latex
% In the preamble or before the section:
\newcommand{\elbowbranch}{\hspace*{0.25cm}\rule[0.6ex]{0.8pt}{1.2em}\hspace{-0.8pt}\rule[0.6ex]{0.7em}{0.8pt}\hspace{0.15cm}}

% Usage:
\begin{twocolentry}{\mbox{\textit{Jan~2025 -- Present}}}
    \elbowbranch \textbf{Senior Software Engineer}
\end{twocolentry}
```

---

## 4. Bullet & Space Budgeting Rules

When representing promotions on a single-page resume:

| Structure | Senior Role Bullets | Junior Role Bullets | Total Company Bullets | Space Impact |
| :--- | :--- | :--- | :--- | :--- |
| **Standard 2-Role Promotion** | 2 bullets | 1 bullet | 3 bullets | Identical to a standard primary experience entry. |
| **Deep Leadership Promotion** | 2 bullets | 2 bullets | 4 bullets | Requires reducing a secondary experience or project by 1 bullet. |
| **3-Role Rapid Promotion** | 2 bullets | 1 bullet | 1 bullet (4 total) | Consolidate oldest entry to 1 high-impact bullet. |

> **Rule:** Never allow total content bullets across the entire resume to exceed **14 bullets**, even with multiple promotions.

---

## 5. ATS & Quality Checklist for Promotions

Before finalizing a resume containing promotions:
1. **Parent Company Tenure:** Confirm the parent company header displays the candidate's *total unbroken tenure* (e.g. `2022 -- Present`).
2. **Role Sub-Dates:** Confirm each promoted role displays its specific date span in italics (`\textit{...}`) so ATS parses the promotion timeline accurately.
3. **Single-Line Date Invariance:** Every date string MUST be wrapped in `\mbox{...}` with non-breaking tildes:
   - `\mbox{\textbf{Month~20XX -- Present}}`
   - `\mbox{\textit{Month~20XX -- Month~20XX}}`
4. **Indentation Harmony:** Ensure bullet points under promoted titles use `leftmargin=0.6cm + 10pt` so they align naturally beneath the indented elbow title.
5. **Compile Gate:** Run `pdflatex` to ensure exit code 0 and strict 1-page fit.

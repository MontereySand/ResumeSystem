# Master Resume Section Breakdown & Content Guide

This skill governs the complete structural architecture, ATS compliance rules, content density guidelines, and adversarial technical auditing for every section in the resume template.

---

## Part 1: Section-by-Section Structural Breakdown

### 1. Name & Header Section
- **Purpose:** Primary candidate identification and document metadata.
- **ATS Requirements:** Clean text header, standard font encoding (`glyphtounicode`), no graphics or floating image boxes.
- **LaTeX Environment:** Custom `\begin{header} ... \end{header}` centered block.
- **Syntax Rules:**
  - Name size: `\fontsize{20 pt}{20 pt}\selectfont \href{}{User Name}`
  - Line height: `\linespread{1.5}` inside header
  - Bottom spacing: `\vspace{5 pt - 0.2 cm}` to seamlessly lead into Education.

### 2. Contact & Info Section
- **Purpose:** Provide recruiter access points with zero parsing friction.
- **Elements:** Email, Phone, LinkedIn, GitHub / Portfolio.
- **Syntax Rules:**
  - Delimiter: Custom `\AND` box separator (`\sbox\ANDbox{$|$}`) with `\kern 5.0 pt`.
  - Non-wrapping wrappers: Wrap each contact element in `\mbox{\href{...}{...}}` to prevent phone numbers or URLs from breaking across lines.
  - ATS Cleanliness: Ensure links point to clean professional handles without tracking parameters.

### 3. Education Section
- **Purpose:** Establish foundational academic credentials, GPA, graduation timeline, and relevant coursework.
- **LaTeX Environment:** `\begin{twocolentry}{[Dates / GPA]} ... \end{twocolentry}` followed by `\begin{adjustwidth}` for coursework.
- **Syntax Rules:**
  - Date & GPA: Locked to single lines using `\mbox{\textbf{Month~20XX -- Month~20XX}}` and `\mbox{\textit{GPA: X.XX}}`.
  - Degree & Institution: `\hspace*{0.2cm}\textbf{Degree Title} \\ \hspace*{0.2cm}\textit{University Name, City, State}`.
  - Coursework Sub-Block: Indented via `\begin{adjustwidth}{0.0cm}{2.5cm}` to avoid colliding with the right-aligned date column. Keep coursework to 4–6 high-signal advanced technical courses.

### 4. Technical Skills Section
- **Purpose:** High-density keyword bank for automated ATS parsers and human technical screeners.
- **LaTeX Environment:** `\begin{onecolentry} \begin{itemize}[leftmargin=0cm + 6.5pt, labelsep=5pt] ... \end{itemize} \end{onecolentry}`.
- **Standard Groupings:**
  1. `\textbf{Languages \& Tools:}` Core programming languages, version control, build tools, container runtimes.
  2. `\textbf{Frameworks \& Platforms:}` Backend/frontend frameworks, cloud ecosystems (AWS/GCP/Azure), distributed systems, databases.
  3. `\textbf{Certifications \& Honors:}` High-level competitive placements, cloud certifications, or specialized badges (when not broken into standalone sections).
- **Formatting Rules:** Separate tool lists using vertical bars `|`. Use `\vspace{0.04 cm}` micro-spacers between categories.

### 5. Experience Section
- **Purpose:** Demonstrate practical engineering impact, architectural ownership, technical maturity, and production scale.
- **LaTeX Environment:** `\begin{twocolentry}{\mbox{\textbf{Month~20XX -- Present}}}` followed by `\begin{onecolentry} \begin{itemize} ... \end{itemize} \end{onecolentry}`.
- **Bullet Distribution & Allocation:**
  - Primary / Most Recent Role: **3 bullets**.
  - Secondary Roles: **2 bullets** each.
- **Bullet Anatomy (The 3-Part Impact Formula):**
  - **Action Verb:** Strong technical action (Architected, Engineered, Developed, Distilled, Optimized).
  - **Technical Mechanism:** Exact framework, protocol, algorithm, or architecture (`\textbf{...}`, `(\textbf{...})`).
  - **Quantifiable Outcome:** Concrete metrics (`\textbf{X\%}`, sub-\textbf{Xms}, `\textbf{X,XXX+}` scale).
- **Date Invariance:** Always wrap dates in `\mbox{...}` with non-breaking spaces `~`.

### 6. Selected Projects Section
- **Purpose:** Showcase deep systems-level passion, complex technical capability, and portfolio evidence.
- **Permanent Ordering:**
  - **Hero Project (Slot 1):** Distributed systems, low-level engine, AI cluster, or core infrastructure. Always anchored first.
  - **Secondary Project (Slot 2):** Platform operator, Kubernetes reconciler, or cloud framework.
  - **Tertiary Project (Slot 3):** Real-time gateway, transactional ledger, or networking proxy.
- **Formatting Structure:**
  - Title Line: Clickable repository hyperlink (`\href{https://github.com/user/project}{\textbf{Project Name (Hero Project)}}`).
  - Subtitle: Italicized technology stack list (`\textit{Python, PyTorch, CUDA, Docker, ...}`).
  - Bullet Allocation: 3 bullets for Hero, 2 bullets for Projects 2 and 3.

### 7. Standalone Awards & Honors Section
- **When to Break Out:** When the candidate possesses exceptional competitive programming distinctions (ICPC, COMAP), major hackathon podiums (1st/2nd place), prestigious fellowships, or national academic awards that merit immediate recruiter visibility.
- **Placement:** Immediately after Education or following Projects.
- **LaTeX Template:**
```latex
\section{Awards \& Honors}
\begin{twocolentry}{\mbox{\textbf{Month~20XX}}}
    \hspace*{0.1cm} \textbf{Competition / Award Title (1st Place / Top X\%)}, Issuing Organization
\end{twocolentry}
\vspace{0.012 cm}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0.4cm + 10pt, labelsep=5pt]
        \item Recognized out of \textbf{X,XXX+} participants for engineering an \textbf{Architectural Innovation} utilizing \textbf{Framework A}
    \end{itemize}
\end{onecolentry}
```

### 8. Standalone Leadership Section
- **When to Break Out:**
  - Defense, government, aerospace contractors, or public sector roles.
  - Roles that explicitly value command responsibility, team leadership, operations, or civic service.
  - Replaces the 3rd project when the conditional leadership rule in `Tailor.md` is met.
- **LaTeX Template:**
```latex
\section{Leadership}
\begin{twocolentry}{\mbox{\textbf{Aug~20XX -- May~20XX}}}
    \hspace*{0.1cm} \textbf{Cadet Major / Program Lead}, 4-Year Leadership Program
\end{twocolentry}
\vspace{0.012 cm}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0.4cm + 10pt, labelsep=5pt]
        \item Promoted for leadership and operational excellence; directed \textbf{XX+} personnel during field operations and established standardized procedures
    \end{itemize}
\end{onecolentry}
```

### 9. Standalone Certifications Section
- **When to Break Out:** When certifications are hard statutory or job-description prerequisites (e.g. AWS Solutions Architect Professional, CKA, CISSP, CompTIA Security+ for cleared defense).
- **LaTeX Template:**
```latex
\section{Certifications}
\begin{twocolentry}{\mbox{\textbf{Month~20XX -- Month~20XX}}}
    \hspace*{0.1cm} \textbf{Certified Kubernetes Administrator (CKA)}, Cloud Native Computing Foundation
\end{twocolentry}
\vspace{0.02 cm}
\begin{twocolentry}{\mbox{\textbf{Month~20XX -- Month~20XX}}}
    \hspace*{0.1cm} \textbf{AWS Certified Solutions Architect -- Associate}, Amazon Web Services
\end{twocolentry}
```

### 10. Publications & Research Section (Academic / ML Research)
- **When to Break Out:** When applying for AI research, PhD-level roles, or when the candidate has authored peer-reviewed papers or conference workshop preprints.
- **LaTeX Template:**
```latex
\section{Publications \& Research}
\begin{twocolentry}{\mbox{\textbf{Month~20XX}}}
    \hspace*{0.1cm} \textbf{``Title of Research Paper in Quoted Format''}, Conference / Journal
\end{twocolentry}
\vspace{0.012 cm}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0.4cm + 10pt, labelsep=5pt]
        \item Co-authored research analyzing \textbf{Algorithmic Mechanism}; open-sourced benchmark achieving \textbf{X\%} accuracy improvements
    \end{itemize}
\end{onecolentry}
```

### 11. Relevant Coursework Section (Expanded Independent Block)
- **When to Break Out:** For university students or career switchers where specific advanced coursework (e.g. Distributed Operating Systems, Advanced Compiler Design, Cryptography) substitutes for missing commercial experience.
- **LaTeX Template:**
```latex
\section{Technical Coursework}
\begin{onecolentry}
    \begin{itemize}[leftmargin=0cm + 6.5pt, labelsep=5pt]
        \textbf{Systems \& Architecture:} Distributed Systems, Operating Systems Internals, Computer Architecture, Advanced Networking \\
        \vspace{0.04 cm}
        \textbf{Theory \& Algorithms:} Advanced Data Structures, Analysis of Algorithms, Computability \& Complexity, Graph Theory
    \end{itemize}
\end{onecolentry}
```

---

## Part 2: Adversarial Technical Auditor (The Three-Sentence Rule)

In addition to structural breakdown, this skill functions as an **Adversarial Technical Auditor** for interview defense.

### Execution Methodology
1. **Extraction:** Scan the master resume (`/Resume/User/main.tex` or active company `main.tex`) and extract every technical term, framework, and technology (e.g., RAG, Ollama, CUDA, RoCE v2, Docker, WebSockets).
2. **The Three-Sentence Rule:** For *every* extracted term, generate exactly three sentences:
   - **Sentence 1 (Definition):** A clear, concise technical explanation of what it is.
   - **Sentence 2 (Architectural Nuance / Trade-off):** A high-signal explanation of how it compares to alternatives, its market positioning, or specific system-design trade-offs.
   - **Sentence 3 (The Adversarial Audit Question):** A highly specific, difficult whiteboard question an interviewer will ask to test deep mastery.

### Audit Examples
- **RoCE v2:** RDMA over Converged Ethernet (v2) is an enterprise networking protocol allowing direct memory access between systems over standard Ethernet fabrics. Unlike InfiniBand which requires proprietary switches and cabling, RoCE v2 runs on commodity Ethernet infrastructure while bypassing the host CPU to drastically reduce interconnect latency in distributed GPU clusters. *Audit Question: How do you handle congestion control (PFC/ECN deadlocks) in a RoCE v2 fabric to prevent packet drop during massive distributed gradient synchronizations?*
- **vLLM / PagedAttention:** vLLM is an open-source high-throughput LLM serving engine built around PagedAttention memory management. Unlike standard PyTorch inference where key-value caches fragment and waste up to 60-80% of GPU memory, vLLM partitions KV memory into virtual pages to maximize batch concurrency. *Audit Question: What are the latency and throughput trade-offs of continuous batching versus chunked prefill when serving mixed context-length traffic?*

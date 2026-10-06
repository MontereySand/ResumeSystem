Resume system: LaTeX template plus AI skills

Edit your resume with an AI inside your code editor. The repo holds a LaTeX template the AI edits directly, plus skills files that set the rules.

Setup
1. Open this repo in VS Code, Cursor, or Antigravity.
2. Keep a CLI or panel AI on the side.
3. Install LaTeX: https://www.latex-project.org/get/
4. Install LaTeX Workshop by James Yu (VS Code extension, also works in Cursor and Antigravity).
Use
- Master resume: Resume/User/main.tex (Lorem Ipsum placeholders, replace with your facts or upgrade ur existing resume's content)
- Skills: Resume/Skills/ (the AI reads these before it edits)
- Tailor for a job: copy the master to Resume/[Company]/main.tex, then edit the copy
- Every edit must compile: pdflatex -interaction=nonstopmode main.tex

Copy this line into any skills file located inside Resume/Skills/ before running the system:
- Before tailoring, read `../Transcript.md`; use its transcript data and coursework-selection rules to select 2–4 exact, completed courses that match the job description, update the LaTeX `Coursework` line, and document the choice in `current.md`.

Thanks to James Yu for LaTeX Workshop.

License: MIT. See LICENSE.

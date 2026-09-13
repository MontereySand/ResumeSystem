GITHUB README DRAFT (paste into README.md)
----------------------------------------

Resume system: LaTeX template plus AI skills

Edit your resume with an AI inside your code editor. The repo holds a LaTeX template the AI edits directly, plus skills files that set the rules.

Setup
1. Open this repo in VS Code, Cursor, or Antigravity.
2. Keep a CLI or panel AI on the side.
3. Install LaTeX: https://www.latex-project.org/get/
4. Install LaTeX Workshop by James Yu (VS Code extension, also works in Cursor and Antigravity).
5. Use a small to mid model. It is enough for this scope.

Use
- Master resume: Resume/User/main.tex (Lorem Ipsum placeholders, replace with your facts)
- Skills: Resume/Skills/ (the AI reads these before it edits)
- Tailor for a job: copy the master to Resume/[Company]/main.tex, then edit the copy
- Guide: Resume/Walkthrough/walkthrough.tex
- Every edit must compile: pdflatex -interaction=nonstopmode main.tex (exit 0, one page, dates on one line). Then remove main.aux, main.log, main.out.

Rules
- One page only. Ceiling is 14 bullets.
- Never invent facts. Missing skill? The AI asks you first.
- Keep native LaTeX. No markdown in .tex files.

Thanks to James Yu for LaTeX Workshop.

License: MIT. See LICENSE.


REPO DESCRIPTION (one line for GitHub About box)
----------------------------------------
LaTeX resume template plus AI skills. Edit and tailor your resume from your code editor.


SUGGESTED TOPICS
----------------------------------------
latex, resume, resume-template, internships, job-search, ai-assisted, vscode, cursor, latex-workshop, career-tools


LICENSE NOTE
----------------------------------------
MIT. Anyone can use, fork, and ship, including commercial use. They must keep your copyright line. Fill in the year and your name in LICENSE before you publish.

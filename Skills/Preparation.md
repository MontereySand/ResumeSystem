# Preparation Skill

This skill governs how the user presents their resume and themselves in a technical interview based on the target company.

## Execution Methodology

1. **Company Profiling (Mandatory Subagent Task):** Invoke a subagent to research the company's current (2026) architectural focus, products, and culture. Do not rely on outdated knowledge.
2. **The "Hero" Project Selection:** Identify the single project from the resume that best aligns with the company's tech stack (e.g., DGX Spark cluster for NVIDIA, Agentic Billing for Stripe/Fintech).
3. **The Elevator Pitch:** Draft a custom 3-sentence introduction that connects the user's CS+DS background and their Hero Project to the company's core mission.
4. **Steering Tactics:** Provide specific strategies on how to gracefully pivot standard behavioral questions back to high-signal technical achievements.
5. **Anticipated Deep Dives:** Predict the top 3 technical bullets the interviewer will most likely interrogate. Provide "Audit Questions" for each to help the user prepare for whiteboard defense.

## Output
Present the Presentation Framework clearly in hyper-concise bullet points in the chat, and save a copy of the preparation notes under a company-specific directory in the workspace repository (e.g., `/Resume/TargetCompany/screening_prep.md`). Never save notes to temp or global app directories outside the project repository.


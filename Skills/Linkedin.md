# LinkedIn Description Generation Skill

This skill governs the extraction, technical refinement, and formatting of highly detailed LinkedIn experience descriptions from a LaTeX resume.

## Top Priority Mandates
1. **No Sections:** Do not use any sub-category headings (such as "Architecture", "Engineering", "Simulation & Dataset Generation", etc.).
2. **No Lead-Ins:** Bullet points must not start with bold lead-in titles/prefixes (such as `- **Vehicle-as-a-Repo:** ...`). Every bullet must start directly with the action verb.
3. **Paragraph Separation:** Group bullet points into logical paragraphs/blocks separated by a single blank line.
4. **De-fluffed & Metric-Dense:** Remove verbal fluff, redundant phrases, and subjective marketing descriptors (e.g., replace *"utilizing"* with *"using"*, omit subjective claims like *"achieving high precision"*). Retain 100% of the concrete metrics, numbers, technologies, and specifications.
5. **Output Path & Capitalization:** Save the result in a plain-text file named `Linkedin.txt` (capitalized L) inside the `/User` subfolder: `/Resume/User/Linkedin.txt`.

## Execution Methodology

### Phase 1: Resume Extraction & Gap Analysis
1. Scan the resume's experience section. If a single internship contains multiple distinct functional roles (e.g., a mix of AI engineering and technical product management), split them into separate LinkedIn entries.
2. Formulate a list of targeted architectural questions for the user to fill in the technical implementation gaps (e.g., WebSocket orchestration details, custom versioning protocols, simulation variables, models trained, edge device deployment, and video preprocessing tools).

### Phase 2: Interactive Querying
* Present the technical questions to the user.
* **Instruction:** Advise the user to provide precise technical implementation details (e.g., Node.js WebSocket layers, CLI metadata handling, synthetic environment randomizations) ensuring the generated details align with standard engineering practices.

### Phase 3: Text Generation & Formatting
1. Generate the detailed plain-text descriptions using the clean bullet layout (no lead-ins, no section headers, blank line between groups).
2. De-fluff the descriptions to be concise and impactful while preserving exact numbers, models, and specifications.
3. Save the final file to the target candidate directory as `Linkedin.txt` inside the `User` directory (`/Resume/User/Linkedin.txt`).

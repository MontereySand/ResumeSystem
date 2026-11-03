# Career facts and attribution

Read when creating or checking the career master, not for ordinary career advice. The master is agent-maintained evidence and career information, not compiler input or authenticated truth. JSON is UTF-8 (BOM accepted); unknown fields are errors. This is the facts-only v3 contract, not a legacy migration API. Strings are literal text; dates stay exactly supplied.

## Files and identities

- The sole shared career master is `system/userinfo/main/facts.json`.
- `system/userinfo/main/notes.md` holds the source/context inventory, useful unresolved material and source-linked questions. `system/userinfo/main/preferences.md` holds only expressly saved preferences. Retained evidence/context lives in `system/userinfo/main/source/`.
- Directly authored `main/main.tex` or `system/applications/<company>/<application>/main.tex` owns selected wording, ordering and presentation. Shared presentation is `system/resume-style.tex`.
- Document IDs are `main` or `applications/<company>/<application>`; main metadata is `system/userinfo/main`; application source/metadata directory is `system/applications/<company>/<application>`. Application context/JD handling belongs to `applications.md`; inspected PDF/history records belong to `rendering.md`.
- Fact, highlight, profile and source IDs match `^[A-Za-z0-9][A-Za-z0-9._-]*$`. Facts, highlights and source records have globally unique IDs, not merely category-local IDs. Keep existing IDs stable.

## Facts (format_version 3)

Required fields: `format_version,id,synthetic,context,sources,basics,education,skills,work,projects,certifications,awards`. `format_version` is `3`; `synthetic` is boolean. Context requires `language:"en",purpose:"job_application_resume"`; optional `occupation,seniority,geography` are nonblank strings. The six category arrays may be empty. Personalized résumé composition needs at least one supported non-basics item; do not initialize a fake empty career.

Every fact and highlight has `id` and `evidence:{status,source_ids}`. Status is `user_asserted`, `document_supported`, `unknown`, `conflicting` or `placeholder`. `source_ids` is a nonempty unique array naming source records. Resolve unknown/conflicting selected claims before export; unrelated uncertainty does not block supported work. Placeholder requires a synthetic profile and synthetic-fixture evidence; non-synthetic facts cannot cite synthetic fixtures. `synthetic:true` labels fictional data, not a sixth evidence status. Evidence attributes an origin; it does not independently prove truth.

All named scalar text fields are nonblank strings. Each object accepts only its listed fields plus required `id,evidence`:

| Fact | Required text/structure | Optional fields |
|---|---|---|
| basics | name | email, phone, phone_url, profiles |
| education | institution, studyType | location, date_text, score, courses |
| skills | name, keywords (nonempty string array) | none |
| work | name, position, highlights | url, location, date_text |
| projects | name, highlights | url, date_text, keywords, description |
| certifications / awards | name | issuer, date_text, url, description |

Profiles are `{network,url,display}`. Highlights are `{id,text,evidence}`. Highlights may be empty. Courses/keywords are arrays of nonblank strings (may be empty except `skills.keywords`). Arrays preserve supplied order. Do not derive tenure from dates, merge roles or transfer their highlights.

`sources` is nonempty; each record is `{id,kind,reference}`. Kinds are `document,user_assertion,synthetic_fixture`. A document additionally requires `access:"original"|"text-only"`, `coverage:"complete"|"partial"|"unknown"`, and optionally `origin` (nonblank original filename/URL). Its reference is the actual retained `system/userinfo/main/source/<leaf>`: no absolute path, backslash or dot/parent path segment. Assertions/fixtures describe their actual origin. There is no authored hash, role or index field; evidence/context roles belong to the notes inventory under documents.md. Context-only documents may have source records without supporting any résumé fact. Retention/access/coverage are attribution, not authenticated capture receipts.

## Direct composition and manual meaning review

Follow `documents.md` for actual-source reading, complete intake, stable attribution and faithful concise rewrites. Preserve the complete supported career record even when an expressly scoped résumé selects less. TeX wording does not rewrite the master by implication. Job requirements are not career evidence.

Before authorized export, manually compare actual selected TeX claims and rewrites with accessible originals, master, notes and that document's actual job context. Resolve unsupported selected claims rather than disguising them as supported. This review needs no extra blanket approval, but material meaning/ownership or content/length decisions require the user's answer. No automatic semantic review, currentness or stale-status detector exists. A digest proves file consistency, not truth or review.

A master-only correction leaves every `.tex` and PDF unchanged; disclose potential affected-document staleness without claiming a computed status. A read-only check writes nothing. `rendering.md` governs real compilation, PDF inspection and authorized publication; `applications.md` governs isolated company/role documents; `git.md` governs separately authorized checkpoints. There are no draft, layout, review or target JSON schemas, generated selections or frozen bundles.

Report malformed JSON with the actual selected input path and available native diagnostic/line/column. Do not repair errors silently, erase evidence or substitute empty successful records. Missing master amid personalized work is partial/damaged state, not permission to initialize again.

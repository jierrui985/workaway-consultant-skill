# Workaway Consultant Skill (English)

An independent, reusable skill for assessing Workaway opportunities and drafting host messages. It combines a host's listing with the applicant's circumstances, travel route, living costs, and decision criteria. The source instructions are entirely in English. The final response follows the user's language; an English host message can include a faithful translation when useful.

This is a set of Markdown instructions and templates. It needs no API key or running service. It is **not affiliated with Workaway** and does not guarantee a placement.

## Versions

This `v2/` directory contains the English edition. The original Chinese v1.0.0 release is preserved at [v.1.0.0](https://github.com/jierrui985/workaway-consultant-skill/releases/tag/v.1.0.0).

## Contents

```text
v2/
├── SKILL.md
├── applicant-profile-template.md
├── modules/
│   ├── applicant-intake.md
│   ├── host-analysis.md
│   ├── location-analysis.md
│   ├── travel-costs.md
│   ├── applicant-match.md
│   ├── application-strategy.md
│   ├── report-presentation.md
│   └── overall-assessment.md
├── templates/
│   ├── family-message.md
│   ├── hostel-message.md
│   ├── farm-message.md
│   ├── community-message.md
│   ├── education-message.md
│   └── environmental-message.md
├── .gitignore
├── LICENSE
└── README.md
```

## How to use it

1. Put the complete directory in the skills location supported by your assistant. Keep relative paths intact; copying only `SKILL.md` loses the modules and templates. Loading details depend on the assistant.
2. Share a host link, screenshots, or description. The skill reads the listing first. If decisive applicant details are missing, it generates a downloadable, editable project-specific form with a clean solid-color layout and asks only 3–5 key questions in chat. A more detailed form is optional.
3. Upload the filled form or answer in chat. You do not have to complete every field. If enough is already known, the skill proceeds directly to the full assessment and marks minor gaps **To confirm**. The reusable [blank profile template](applicant-profile-template.md) can also be filled outside this public directory.
4. The full assessment opens with one score out of ten and a recommendation, followed by an individualized judgment and the most important constraint. It covers the host, food and accommodation, tasks, older reviews, location, door-to-door travel, applicant fit, and an English host message with a translation when useful.
5. Confirm outstanding conditions before using the message. The skill does not send messages, book travel, or publish applicant details.

Example prompt (no personal details):

```text
Use workaway-consultant-skill to assess this Workaway opportunity:
[link, screenshots, or description]

Read the host information first. If key details about me are missing, give me an editable form and ask only the most important questions. Then prepare the illustrated assessment.
```

You can also ask to compare two projects, refresh travel costs, or revise a host message without forcing a full report.

## Assessment and evidence

- Applicant fit is scored from 0 to 100 across six weighted dimensions. It is not a probability of acceptance.
- Overall quality is expressed as one score out of ten, rounded to one decimal place, with one recommendation level. A provisional score uses only dimensions supported by evidence and discloses information coverage; unknowns are neither zero nor automatically satisfied.
- A confirmed host requirement conflict or applicant non-negotiable takes priority over a high numeric score. Unclear hours, meals, dates, or activity authorization cap the recommendation at **Consider with caution**.
- For dynamic costs, keep the original currency and show the user's preferred currency, including CNY when requested. State exchange-rate and quote dates. Do not present an off-season fare as a quote for the user's travel date, or call a partial route a complete budget.
- Location maps point only to a verified city or district, not a private residence. Images and social posts must genuinely relate to the project or confirmed location; likes, views, and followers are separate metrics.
- A host statement, independently verified fact, inference, and unresolved question must remain distinguishable. Older reviews are not proof of this year's arrangements.

See [Applicant match](modules/applicant-match.md), [Overall assessment](modules/overall-assessment.md), and [Report presentation](modules/report-presentation.md) for the scoring and output rules.

## Capabilities and limits

Reading screenshots requires image understanding. Current prices, exchange rates, official entry information, and place imagery require web access or reliable recent material supplied by the user. If a page cannot be opened, ask for visible text or screenshots; do not bypass access controls. If a photo cannot be displayed reliably, link to its identified source instead.

This skill supports trip and application decisions; it does not make a complete visa determination, implement an automatic flight search, or send applications. Free accommodation is not a zero-cost trip. An unpaid exchange is not automatically permitted under a tourist entry status.

## Privacy and publishing

Only generic instructions and blank templates belong in this repository. Keep completed forms, real host conversations, personal reports, and draft messages outside it. `.gitignore` excludes common private folders, but cannot catch arbitrary filenames or remove data from Git history. Review the working tree and history before publication.

This project uses the [MIT License](LICENSE). Retain its notice when sharing or adapting the files.

## Maintenance checks

Keep score weights totaling 100%. Link new modules directly from `SKILL.md` and state when to read them. Keep templates generic. Test these cases when changing the workflow: a host link with no applicant details stops after the form; sufficient applicant details lead to one overall score; missing criteria produce one provisional score with coverage; an old review is not presented as current; maps do not point to a private home; image and social metrics are traceable; a partially priced route is labeled a partial subtotal; a minimum-stay conflict limits the recommendation; the English message and translation make the same commitments.

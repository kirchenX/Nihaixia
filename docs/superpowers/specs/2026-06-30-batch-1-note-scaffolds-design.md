# Batch 1 Note Scaffolds Design

## Purpose

Turn the most incomplete notes into usable, source-aware scaffolds so later study work can proceed one file at a time without losing safety boundaries or source traceability.

This batch does not add new medical, interview, or traditional-culture claims. It replaces vague `待补录` placeholders with structured fields for source status, evidence, follow-up questions, and risk notes.

## Scope

Update these files:

- `倪海厦学习资料/01_梁冬对话倪海厦/05.md`
- `倪海厦学习资料/01_梁冬对话倪海厦/06.md`
- `倪海厦学习资料/01_梁冬对话倪海厦/07.md`
- `倪海厦学习资料/00_总览/术语表.md`
- `倪海厦学习资料/03_医案论文/医案索引.md`
- `倪海厦学习资料/03_医案论文/方证案例对照.md`
- `倪海厦学习资料/04_天纪/风水与命理术语.md`

## Design

### Interview Notes 05-07

Each note should keep the current Bilibili source link and change `待观看整理` into a more precise status:

`待抽样；页面标题、分集标题和时长已确认；完整字幕/逐字稿待取得`

Each note should include:

- `整理状态`
- `抽样记录表`
- `后续在人纪中查找`
- `高风险提示`
- `存疑与核对`

The tables remain empty of content claims until the episode is watched, sampled, transcribed, or supplied by the user.

### Glossary

The glossary should explain how to fill terms:

- `初步理解` may only be filled from a cited source or marked as `推导整理`.
- Medical operation, dosage, treatment, and disease-related terms require `高风险`.
- Terms should point to a source note, branch note, software UI capture, or user-provided transcript.

Existing terms stay present. Empty cells become actionable source instructions rather than generic `待补录`.

### Medical Case Indexes

`医案索引.md` and `方证案例对照.md` should make the safety boundary explicit:

- Cases are study records, not treatment plans.
- Formula-case mapping is a verification aid, not a prescribing guide.
- Severe disease themes must remain high-risk leads.

Tables should include example empty rows that specify what evidence is needed.

### Tianji Terms

`风水与命理术语.md` stays in the Tianji branch. It should explicitly say this file is a traditional-culture/术数 glossary and not part of the medical main line. Its table should be ready for later source-backed entries.

## Non-Goals

- No web fetches.
- No protected database extraction.
- No new transcript or episode summary.
- No self-treatment, prescription, dosage, acupuncture-operation, or disease-management advice.
- No installation or merge of external skills.

## Acceptance Criteria

- The seven target files no longer contain bare single-line `待补录` placeholders as their only content under a section.
- Interview notes 05-07 clearly state `待抽样` and include fields for future sampled evidence.
- Glossary and case notes keep source/status/risk columns.
- Tianji terminology remains separate from the medical route.
- Markdown files read correctly as UTF-8.
- No binary, database, executable, or original media files are modified.

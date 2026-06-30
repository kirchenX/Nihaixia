# Data Index Quality Design

## Purpose

Bring the existing Ni Haixia study workspace into a more maintainable state by making source status, index links, and next actions consistent across the Markdown notes.

This work is documentation and data-organization work only. It does not add new medical conclusions, extract protected databases, install external skills, or modify original local software/video files.

## Current Context

The workspace already contains:

- `README.md` as the main project entry.
- `倪海厦学习总目录.md` as the long-form study map.
- `学习进度.md` as the current progress tracker.
- `资料录入规范.md` as the source-entry rule sheet.
- `倪海厦学习资料/00_总览/` for safety notes, terms, and Bilibili leads.
- `倪海厦学习资料/01_梁冬对话倪海厦/` for episode notes and the episode index.
- `倪海厦学习资料/02_人纪/`, `03_医案论文/`, and `04_天纪/` for major study branches.
- `倪海厦学习资料/99_待核对/` for blocked or incomplete extraction.

There are existing uncommitted changes in several of these files. The implementation must preserve that work and only make narrow, reviewable additions or consistency edits.

## Status Model

Use the following statuses consistently:

- `已确认`: visible page, local file tree, software UI, or user-provided text confirms the item.
- `已抽样`: only partial review or fast-scan notes exist; the item is not a complete transcript or full summary.
- `待核对`: a lead exists, but the content has not been verified enough to use as a source.
- `受限不可读`: the file exists, but legal/technical access is blocked, such as password-protected or unreadable `.mdb` data.
- `推导整理`: a learning route, classification, or workflow inferred from the study structure, not source text.
- `高风险`: medical themes involving treatment, dosage, acupuncture operations, severe disease, pregnancy/children, or emergency-like conditions.

## Files To Add

Add `倪海厦学习资料/00_总览/资料状态看板.md`.

This file will be the central snapshot for source status and next action. It should contain:

- A source table for Bilibili interview material.
- A source table for local software systems.
- A source table for existing branch notes.
- A short queue of next actions.
- A safety note explaining that the board is for study tracking, not medical advice.

## Files To Update

Update `README.md`:

- Add a quick entry link to `资料状态看板.md`.

Update `倪海厦学习总目录.md`:

- Add the status board to the first-entry list.
- Keep existing source descriptions intact.

Update `学习进度.md`:

- Align current status with the board.
- Make clear that Liangdong episodes 01-04 are `已抽样`, not complete transcripts.
- Keep episodes 05-07 as next actions unless source review has actually been performed.

Update `倪海厦学习资料/00_总览/B站相关学习线索.md` if needed:

- Link to the status board.
- Preserve its role as a lead list, not a confirmed content summary.

## Non-Goals

This pass will not:

- Open or extract protected `.mdb` files.
- Reverse engineer local software.
- Install or merge the external `JuneYaooo/nihaisha-nishi-tcm` skill.
- Fetch new web data.
- Summarize video speech without subtitles, visible captions, watched segments, or user-provided transcript.
- Turn interview opinions, case names, prescriptions, dosages, or acupuncture details into medical advice.

## Safety Boundary

Every user-facing status document must preserve the project boundary:

This workspace is a traditional Chinese medicine and traditional culture study index. It is not a diagnosis, treatment, prescription, acupuncture-operation, or medication guide. High-risk topics remain search leads and must be checked through qualified medical care and primary source review.

## Acceptance Criteria

- `资料状态看板.md` exists and can be reached from `README.md`.
- The status board distinguishes confirmed facts, sampled notes, pending verification, inaccessible files, inferred routes, and high-risk topics.
- `学习进度.md` and `倪海厦学习资料/01_梁冬对话倪海厦/索引.md` do not conflict on the state of episodes 01-07.
- No original software, database, executable, video, or protected data file is modified.
- Markdown links point to existing workspace files.
- The final diff is limited to documentation and index updates.

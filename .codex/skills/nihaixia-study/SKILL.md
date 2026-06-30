---
name: nihaixia-study
description: Use when organizing, updating, or studying Ni Haixia / 倪海厦 materials, TCM notes, 人纪, 天纪, acupuncture, herbal classics, medical cases, or Bilibili lecture/video indexes in this workspace.
---

# Nihaixia Study

## Overview

Use this skill to maintain a long-running learning system for 倪海厦 materials. Keep medical safety boundaries explicit, separate confirmed source facts from inferred study structure, and update the workspace notes incrementally.

## Core Rules

- Treat all content as study material, not medical advice.
- Do not recommend self-treatment, dosing, acupuncture operations, or stopping prescribed care.
- Mark source status clearly: confirmed from local files, confirmed from visible UI, confirmed from web/video page, inferred, or pending verification.
- Preserve original source paths and video links so notes remain traceable.
- Prefer small Markdown updates over large rewrites.
- For videos, do not summarize spoken content unless subtitles, visible captions, watched segments, or user-provided transcripts are available.

## Project Files

- Main index: `倪海厦学习总目录.md`
- Local software root: `D:\ChineseMedicine\倪师三套软件2023版`
- Project skill reference: `references/project-sources.md`

Read `references/project-sources.md` before updating the main index or creating new notes.

## Workflow

1. Identify the source type:
   - Bilibili or web video page
   - local software UI
   - local file tree
   - user-provided notes
   - generated study plan

2. Capture evidence:
   - For browser pages, record title, URL, visible episode names, tags, and dates.
   - For subtitle/video summaries, record whether transcript extraction succeeded or failed.
   - For Windows software UI, record visible module names and screenshots/text only; do not modify software data.
   - For local files, record exact absolute paths and file types.

3. Update notes:
   - Add new confirmed items under the relevant source section.
   - Add inferred learning order under study-route sections only.
   - Add blocked or unreadable items under pending verification.

4. Keep the learning structure stable:
   - 导入：梁冬对话倪海厦
   - 医学主线：人纪
   - 文化术数分支：天纪
   - 复盘检索：医学论文医案
   - 待核对：数据库、软件界面、未整理视频

## Note Pattern

Use this compact pattern for new entries:

```markdown
### 标题

来源：
- 类型：
- 路径/链接：
- 状态：

要点：
- 

后续：
- 
```

## Common Mistakes

- Do not present a database table, episode list, or chapter title as confirmed unless it was actually visible or extracted.
- Do not mix 天纪 material into the core medical route; keep it as a separate branch.
- Do not hard-delete or rename original learning software files.
- Do not bypass database passwords or reverse engineer protected data.

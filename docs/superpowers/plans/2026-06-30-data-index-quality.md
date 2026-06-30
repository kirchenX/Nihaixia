# Data Index Quality Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a central source-status board and align the main project entry points with the same status language.

**Architecture:** This is a Markdown-only documentation update. `资料状态看板.md` becomes the canonical snapshot for source status, while `README.md`, `倪海厦学习总目录.md`, `学习进度.md`, and the Bilibili lead page link to it and retain their existing responsibilities.

**Tech Stack:** Markdown, PowerShell, Git.

---

## File Structure

- Create: `倪海厦学习资料/00_总览/资料状态看板.md`
  - Responsibility: central source-status table and next-action queue.
- Modify: `README.md`
  - Responsibility: root project entry with quick links.
- Modify: `倪海厦学习总目录.md`
  - Responsibility: long-form study map and source overview.
- Modify: `学习进度.md`
  - Responsibility: current work progress and task checklist.
- Modify: `倪海厦学习资料/00_总览/B站相关学习线索.md`
  - Responsibility: Bilibili visible lead list.

## Task 1: Create Source Status Board

**Files:**
- Create: `倪海厦学习资料/00_总览/资料状态看板.md`

- [ ] **Step 1: Inspect current source facts**

Run:

```powershell
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\01_梁冬对话倪海厦\索引.md'
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\99_待核对\数据库内部目录待补录.md'
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\00_总览\B站相关学习线索.md'
```

Expected: source status for Bilibili, local `.mdb` access limits, and lead categories are visible.

- [ ] **Step 2: Add the board file**

Create `倪海厦学习资料/00_总览/资料状态看板.md` with this content:

```markdown
# 资料状态看板

> 本看板只用于跟踪学习资料来源、整理状态和下一步动作；不提供诊断、处方、针灸操作或用药建议。

## 状态标签

- `已确认`：已从页面、文件树、软件界面或用户提供内容确认。
- `已抽样`：只做了快进抽样或局部记录，不等于完整逐字稿或完整总结。
- `待核对`：已有线索，但内容完整性、来源或可用性尚未确认。
- `受限不可读`：文件存在，但当前不能合法或稳定读取，例如密码受限或格式不可识别。
- `推导整理`：基于学习结构整理出的路线、分类或任务，不等同于原文。
- `高风险`：涉及处方、剂量、针灸操作、重症、孕产、儿童或急症等内容，只保留为学习检索线索。

## B 站访谈资料

| 资料 | 来源 | 当前状态 | 已确认内容 | 下一步 |
| --- | --- | --- | --- | --- |
| 《梁冬对话倪海厦》01 | B 站视频页 | 已抽样 | 标题、时长、页面来源、快进抽样笔记 | 完整观看或取得合法字幕/转录后复核 |
| 《梁冬对话倪海厦》02 | B 站视频页 | 已抽样 | 标题、时长、页面来源、快进抽样笔记 | 完整观看或取得合法字幕/转录后复核 |
| 《梁冬对话倪海厦》03 | B 站视频页 | 已抽样 | 标题、时长、页面来源、快进抽样笔记 | 完整观看或取得合法字幕/转录后复核 |
| 《梁冬对话倪海厦》04 | B 站视频页 | 已抽样 | 标题、时长、页面来源、快进抽样笔记 | 完整观看或取得合法字幕/转录后复核 |
| 《梁冬对话倪海厦》05 | B 站视频页 | 待核对 | 标题、时长、页面来源 | 做快进抽样或字幕转录 |
| 《梁冬对话倪海厦》06 | B 站视频页 | 待核对 | 标题、时长、页面来源 | 做快进抽样或字幕转录 |
| 《梁冬对话倪海厦》07 | B 站视频页 | 待核对 | 标题、时长、页面来源 | 做快进抽样或字幕转录 |

## 本地软件资料

| 系统 | 已确认内容 | 当前限制 | 下一步 |
| --- | --- | --- | --- |
| 人纪内部学习系统 V2023 版 | 本地目录和 `Data` 数据文件存在 | 主库提示密码无效；小库提示格式不可识别 | 优先通过软件界面、导出、人工转录或截图 OCR 补录一级目录 |
| 天纪学习系统客户端 V2023 版 | 本地目录、`DATA` 数据文件和卦图目录存在 | 主库提示密码无效 | 优先通过软件界面、导出、人工转录或截图 OCR 补录一级目录 |
| 医学论文医案查询系统 V2023 版 | 本地目录和 `Data\LILUN.mdb` 存在 | 主库提示密码无效 | 优先通过软件界面、导出、人工转录或截图 OCR 补录分类目录 |

## 分支笔记状态

| 分支 | 当前状态 | 说明 |
| --- | --- | --- |
| 总览 | 已确认 / 推导整理 | 已有安全说明、术语表、B 站线索和学习路线 |
| 梁冬对话倪海厦 | 已抽样 / 待核对 | 01-04 已抽样；05-07 待抽样；全套仍待完整字幕或人工复核 |
| 人纪 | 推导整理 | 已有主题骨架，软件内部目录仍待补录 |
| 医案论文 | 推导整理 / 高风险 | 已有索引骨架；疾病和案例只作为复盘线索 |
| 天纪 | 推导整理 | 独立作为传统文化与术数分支，不放入医学主线前置 |
| 待核对 | 待核对 / 受限不可读 | 数据库目录和软件打开问题集中记录 |

## 下一步工作队列

- [ ] 梁冬 05-07 快进抽样，保持“抽样笔记”状态。
- [ ] 梁冬 01-04 完整观看或取得合法字幕/转录后复核。
- [ ] 人纪软件一级目录补录。
- [ ] 天纪软件一级目录补录。
- [ ] 医案论文软件分类目录补录。
- [ ] 外部 skill 候选 `JuneYaooo/nihaisha-nishi-tcm` 的许可、来源和重复内容审查。

## 风险提示

- 本项目是传统中医与传统文化学习索引，不是医疗建议。
- 访谈观点、案例标题、方药名、穴位名和疾病名只作为学习线索。
- 涉及肿瘤、尿毒症、心脏病、肺炎、孕产、儿童、急症等高风险主题时，应回到合格医疗体系、经典原文和可靠来源交叉核对。
```

- [ ] **Step 3: Verify file reads as UTF-8**

Run:

```powershell
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\00_总览\资料状态看板.md'
```

Expected: Chinese text displays correctly in the Codex output.

## Task 2: Link Board From Main Entries

**Files:**
- Modify: `README.md`
- Modify: `倪海厦学习总目录.md`
- Modify: `倪海厦学习资料/00_总览/B站相关学习线索.md`

- [ ] **Step 1: Add README quick link**

In `README.md`, add this item under `## 快速入口` after `术语表`:

```markdown
- [资料状态看板](倪海厦学习资料/00_总览/资料状态看板.md)
```

- [ ] **Step 2: Add main index entry**

In `倪海厦学习总目录.md`, add `资料状态看板` to the first-entry list near the other overview files:

```markdown
- [资料状态看板](倪海厦学习资料/00_总览/资料状态看板.md)
```

- [ ] **Step 3: Add Bilibili lead cross-link**

In `倪海厦学习资料/00_总览/B站相关学习线索.md`, add this sentence after the opening source block:

```markdown
状态汇总见：[资料状态看板](资料状态看板.md)。
```

- [ ] **Step 4: Verify the new link targets exist**

Run:

```powershell
Test-Path -LiteralPath '倪海厦学习资料\00_总览\资料状态看板.md'
Test-Path -LiteralPath 'README.md'
Test-Path -LiteralPath '倪海厦学习总目录.md'
Test-Path -LiteralPath '倪海厦学习资料\00_总览\B站相关学习线索.md'
```

Expected: four `True` lines.

## Task 3: Align Progress Status

**Files:**
- Modify: `学习进度.md`
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/索引.md`

- [ ] **Step 1: Confirm episode status text**

Run:

```powershell
Get-Content -Encoding UTF8 -LiteralPath '学习进度.md'
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\01_梁冬对话倪海厦\索引.md'
```

Expected: both files indicate 01-04 are sampled and 05-07 are pending.

- [ ] **Step 2: Standardize wording if needed**

Use this wording wherever the status summary appears:

```markdown
01-04 已完成快进抽样，属于初步学习索引，不等于完整逐字稿或完整总结；05-07 待抽样；全套待完整观看或取得合法字幕/转录后复核。
```

- [ ] **Step 3: Keep progress checklist consistent**

Ensure `学习进度.md` keeps these tasks unchecked:

```markdown
- [ ] 完整观看《梁冬对话倪海厦》01，修正快进抽样误差。
- [ ] 完整观看《梁冬对话倪海厦》02，修正快进抽样误差。
- [ ] 完整观看《梁冬对话倪海厦》03，修正快进抽样误差。
- [ ] 完整观看《梁冬对话倪海厦》04，修正快进抽样误差。
- [ ] 对《梁冬对话倪海厦》05 做快进抽样。
- [ ] 对《梁冬对话倪海厦》06 做快进抽样。
- [ ] 对《梁冬对话倪海厦》07 做快进抽样。
```

## Task 4: Final Verification

**Files:**
- Review: all modified Markdown files.

- [ ] **Step 1: Check changed files**

Run:

```powershell
git status --short
git diff --stat
```

Expected: only Markdown documentation files and the new `docs/superpowers` files are changed.

- [ ] **Step 2: Search for inconsistent status wording**

Run:

```powershell
rg -n "完整逐字稿|完整总结|已完成快进抽样|待抽样|受限不可读|资料状态看板" .
```

Expected: references either point to the board or use the standardized distinction between sampled and complete material.

- [ ] **Step 3: Verify no protected source files are touched**

Run:

```powershell
git diff --name-only | rg "\.(mdb|ldb|exe|dll|mp4|zip|rar|7z)$"
```

Expected: no output.

- [ ] **Step 4: Review Markdown links added in this pass**

Run:

```powershell
Test-Path -LiteralPath '倪海厦学习资料\00_总览\资料状态看板.md'
```

Expected: `True`.

- [ ] **Step 5: Commit when requested**

Only commit if the user asks for it. Use:

```powershell
git add 'docs\superpowers\specs\2026-06-30-data-index-quality-design.md' 'docs\superpowers\plans\2026-06-30-data-index-quality.md' '倪海厦学习资料\00_总览\资料状态看板.md' 'README.md' '倪海厦学习总目录.md' '学习进度.md' '倪海厦学习资料\00_总览\B站相关学习线索.md' '倪海厦学习资料\01_梁冬对话倪海厦\索引.md'
git commit -m "docs: add source status board"
```

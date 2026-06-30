# Batch 1 Note Scaffolds Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the most incomplete note placeholders with source-aware, safety-aware Markdown scaffolds.

**Architecture:** This is a Markdown-only update. Interview files 05-07 receive a common pending-sampling structure; glossary, case, and Tianji files receive source/status/risk fields that make later updates traceable.

**Tech Stack:** Markdown, PowerShell, Git.

---

## File Structure

- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/05.md`
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/06.md`
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/07.md`
- Modify: `倪海厦学习资料/00_总览/术语表.md`
- Modify: `倪海厦学习资料/03_医案论文/医案索引.md`
- Modify: `倪海厦学习资料/03_医案论文/方证案例对照.md`
- Modify: `倪海厦学习资料/04_天纪/风水与命理术语.md`

## Task 1: Interview Pending Scaffolds

**Files:**
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/05.md`
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/06.md`
- Modify: `倪海厦学习资料/01_梁冬对话倪海厦/07.md`

- [ ] **Step 1: Replace each file with the pending-sampling template**

Use the episode number in the title. Preserve the Bilibili URL. For episode 05 use this exact structure:

```markdown
# 《梁冬对话倪海厦》05（字幕版）

来源：
- 类型：B 站视频
- 链接：https://www.bilibili.com/video/BV1B1XzBzEBq
- 状态：待抽样；页面标题、分集标题和时长已确认；完整字幕/逐字稿待取得

## 整理状态

- 当前只确认分集存在和时长，尚未完成本集内容抽样。
- 后续整理必须来自可见字幕、完整观看记录、合法字幕/转录文本或用户提供笔记。
- 本页暂不写入未经核对的观点、病证、方药或操作内容。

## 抽样记录表

| 时间段 | 主题 | 关键词 | 后续查找 | 风险/存疑 |
| --- | --- | --- | --- | --- |
| 00:00-10:00 | 待抽样 | 待抽样 | 待抽样后填写 | 待核对 |
| 10:00-20:00 | 待抽样 | 待抽样 | 待抽样后填写 | 待核对 |
| 20:00-30:00 | 待抽样 | 待抽样 | 待抽样后填写 | 待核对 |
| 30:00-40:00 | 待抽样 | 待抽样 | 待抽样后填写 | 待核对 |
| 40:00-结尾 | 待抽样 | 待抽样 | 待抽样后填写 | 待核对 |

## 后续在人纪中查找

- 待本集抽样后，把明确出现的经典、病证、方药、针灸、辨证或医案线索映射到人纪或医案论文分支。
- 不从分集标题或相关视频标题推断本集内容。

## 高风险提示

- 如本集涉及处方、剂量、针灸操作、重症、孕产、儿童或急症，只记录为高风险学习线索。
- 不把访谈观点写成诊断、治疗、用药或操作建议。

## 存疑与核对

- 完整字幕/逐字稿待取得。
- 需要完整观看或按时间段重新抽样。
```

For episodes 06 and 07, change only the title number.

- [ ] **Step 2: Verify no bare section-only placeholders remain**

Run:

```powershell
rg -n "^- 待补录$" '倪海厦学习资料\01_梁冬对话倪海厦\05.md' '倪海厦学习资料\01_梁冬对话倪海厦\06.md' '倪海厦学习资料\01_梁冬对话倪海厦\07.md'
```

Expected: no output.

## Task 2: Glossary Actionable Scaffolding

**Files:**
- Modify: `倪海厦学习资料/00_总览/术语表.md`

- [ ] **Step 1: Add fill rules and improve placeholder rows**

Keep existing term categories. Add a `填写规则` section after the opening note. For every term row, use `待来源补录` in the source column and `待核对` in the status column. Use `待按来源补充，不作医学结论` for medical terminology understanding cells, and `待按天纪来源补充，归入文化术数分支` for Tianji terms.

- [ ] **Step 2: Verify status columns remain present**

Run:

```powershell
Select-String -Path '倪海厦学习资料\00_总览\术语表.md' -Pattern '填写规则|待来源补录|高风险|推导整理'
```

Expected: all four patterns appear.

## Task 3: Medical Case Scaffolds

**Files:**
- Modify: `倪海厦学习资料/03_医案论文/医案索引.md`
- Modify: `倪海厦学习资料/03_医案论文/方证案例对照.md`

- [ ] **Step 1: Expand `医案索引.md`**

Add sections for `收录条件`, `索引字段`, and `待录入队列`. Keep a table with source, keyword, status, and risk columns. Make clear that severe disease rows are high-risk leads only.

- [ ] **Step 2: Expand `方证案例对照.md`**

Add sections for `使用边界`, `对照字段`, and `待录入队列`. Keep a table with formula, evidence, case source, status, and risk columns. State that formula mapping is not a prescribing guide.

- [ ] **Step 3: Verify safety wording exists**

Run:

```powershell
Select-String -Path '倪海厦学习资料\03_医案论文\医案索引.md','倪海厦学习资料\03_医案论文\方证案例对照.md' -Pattern '不作为|高风险|待来源补录|治疗方案|开方依据'
```

Expected: safety and source wording appears in both files.

## Task 4: Tianji Term Scaffolding

**Files:**
- Modify: `倪海厦学习资料/04_天纪/风水与命理术语.md`

- [ ] **Step 1: Expand the Tianji terminology file**

Add `定位`, `填写规则`, and a table with terms such as `风水`, `命理`, `紫微斗数`, `四柱`, `堪舆`, each marked as pending source-backed explanation. State that this branch is separate from the medical main route.

- [ ] **Step 2: Verify Tianji separation wording exists**

Run:

```powershell
Select-String -Path '倪海厦学习资料\04_天纪\风水与命理术语.md' -Pattern '文化术数|医学主线|待来源补录|不作为医学判断'
```

Expected: all patterns appear.

## Task 5: Final Verification

**Files:**
- Review all seven target files.

- [ ] **Step 1: Check UTF-8 reads**

Run:

```powershell
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\01_梁冬对话倪海厦\05.md' | Select-Object -First 8
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\00_总览\术语表.md' | Select-Object -First 12
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\03_医案论文\医案索引.md' | Select-Object -First 12
Get-Content -Encoding UTF8 -LiteralPath '倪海厦学习资料\04_天纪\风水与命理术语.md' | Select-Object -First 12
```

Expected: Chinese text displays correctly.

- [ ] **Step 2: Check no protected files changed**

Run:

```powershell
git diff --name-only | rg "\.(mdb|ldb|exe|dll|mp4|zip|rar|7z)$"
```

Expected: no output.

- [ ] **Step 3: Check target files for useful status vocabulary**

Run:

```powershell
rg -n "待抽样|待来源补录|待核对|高风险|不作为|不作医学结论|文化术数" '倪海厦学习资料\01_梁冬对话倪海厦\05.md' '倪海厦学习资料\01_梁冬对话倪海厦\06.md' '倪海厦学习资料\01_梁冬对话倪海厦\07.md' '倪海厦学习资料\00_总览\术语表.md' '倪海厦学习资料\03_医案论文\医案索引.md' '倪海厦学习资料\03_医案论文\方证案例对照.md' '倪海厦学习资料\04_天纪\风水与命理术语.md'
```

Expected: each target file has status or safety vocabulary.

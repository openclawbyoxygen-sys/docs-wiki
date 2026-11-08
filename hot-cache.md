---
title: "Hot Cache — Docs Agent"
tags:
  - system
  - hot-cache
---

# Hot Cache — Docs Agent 🦐

**Last updated:** 2026-11-09 05:10 Bangkok (UTC+7)

---

## 🔑 สิ่งที่จำเป็นต้องจำ

### ตัวตน
- **Name:** กุ้งมังกร 📋
- **Workspace:** `/data/.openclaw/workspace-docs/`
- **Wiki vault:** `/data/.openclaw/wiki/docs/`
- **โดเมน:** เอกสาร DUE / mapping / summarizer — **ไม่ทำ trading analysis**

### DUE Summarizer
- Script: `/data/.openclaw/workspace-docs/scripts/due_summarizer.py`
- ใช้: `python3 due_summarizer.py <file.xlsx> --sheet=JAN26`
- มูลค่า = vials × price (ไม่ใช่ sum ของ col)
- นับผู้ป่วยทุก eval (ไม่ใช่เฉพาะ eval=1)
- Ertapenem O/L header อยู่ row 2
- Fosfomycin Oral/INJ แยกด้วย drug_code

### Google Sheets
- Credentials: `/data/.openclaw/workspace-docs/credentials/google-sheets.json`
- Service account: `docs-1973@due-summary2026.iam.gserviceaccount.com`
- Sheet: `https://docs.google.com/spreadsheets/d/1JR2VA_p6F9ZM6tDmAiTKs1NWF6y7LHHSFcaHFbSw1wE/edit`
- **ต้องยืนยัน (y/n) ก่อนเขียนทุกครั้ง**

### Discord
- Guild: `1518541245578743828` · Account: `docs`
- Channel หลัก: `#กุ้งมังกร` (`1518671816514736390`) — ไม่ต้อง mention
- หมายเหตุ: cron ของ main agent ใช้ `delivery.to = "channel:<id>"` — pattern เดียวกันนี้ใช้ได้ถ้าต้องตั้ง cron ของ docs

### Sync (แยกต่างหากจาก main)
| Path | Repo |
|------|------|
| `/data/.openclaw/workspace-docs/` | `docs-workspace` |
| `/data/.openclaw/wiki/docs/` | `docs-wiki` |
| Script | `bash /data/.openclaw/workspace-docs/scripts/sync-docs.sh` |

---

## 📂 Wiki Structure

- `skills/DUE-Evaluator.md` — คู่มือ DUE Evaluator
- `concepts/Drug-Mapping.md` — Drug & Pathogen Mapping
- `daily/`, `analysis/`, `journal/`, `inbox/` — ว่าง รอเนื้อหา

## 🔗 Wikilinks

- [[DUE-Evaluator]]
- [[Drug-Mapping]]

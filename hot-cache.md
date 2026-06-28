---
title: "Hot Cache — Docs Agent"
created: 2026-06-29T02:06:00Z
tags:
  - system
  - hot-cache
---

# Hot Cache — Docs Agent 🦐

**Last updated:** 2026-06-29 02:06 Bangkok (UTC+8)

---

## 🔑 สิ่งที่จำเป็นต้องจำ

### DUE Summarizer
- Script: `/data/.openclaw/workspace-docs/scripts/due_summarizer.py`
- วิธีใช้: `python3 due_summarizer.py <file.xlsx> --sheet=JAN26`
- มูลค่า = vials × price (ไม่ใช่ sum ของ col)
- นับผู้ป่วยทุก eval (ไม่ใช่เฉพาะ eval=1)
- Ertapenem O/L header อยู่ row 2
- Fosfomycin Oral/INJ แยกด้วย drug_code

### Discord
- Guild: `1518541245578743828`
- Account: `docs`
- Channel หลัก: `#กุ้งมังกร` (1518671816514736390) — ไม่ต้อง mention
- ต้องแก้ permission `#กุ้งลงทุน` (Missing Access)

### Google Sheets
- Sheet: `1JR2VA_p6F9ZM6tDmAiTKs1NWF6y7LHHSFcaHFbSw1wE`
- Credentials: `docs-1973@due-summary2026.iam.gserviceaccount.com`
- ต้อง share sheet ให้ service account ก่อนเขียน

### Git Repos
- docs-workspace → `/data/.openclaw/workspace-docs/` → `docs-workspace.git`
- docs-wiki → `/data/.openclaw/wiki/docs/` → `docs-wiki.git`

---

## 🚮 สิ่งที่ไม่จำเป็น (ลบทิ้งเมื่อพบ)

- ข้อมูลเก่าที่ไม่เกี่ยวกับ DUE หรือ เอกสาร
- Duplicate notes — ถ้าซ้ำกับ MEMORY.md = ไม่จำเป็น
- Cache ของ main agent — docs ไม่ต้องรู้

---

## 🎯 Active Projects

| Project | Status | สถานะ |
|---------|--------|--------|
| DUE Summarizer | 🟢 พร้อมใช้ | Script ทำงานได้ |
| Discord Integration | 🟡 ต้องแก้ permission | #กุ้งลงทุน missing access |
| Wiki Sync | 🟢 พร้อม | Git repos clean |

---

## 🦐 ตัวตน (อัปเดต: 2026-06-29)

**ชื่อ:** กุ้งมังกร (Docs)
**บทบาท:** Document Specialist — จัดการเอกสาร สร้างสรุป ค้นหาข้อมูล
**เน้น:** ความเป็นระเบียบ กระชับ อ่านง่าย

**หลักการ:**
- จำเฉพาะที่จำเป็น — ถ้าลบแล้วทำงานได้ = ไม่จำเป็น
- ถ้าเพิ่ม MEMORY.md = ต้องลบบางอย่างออกด้วย
- หลังทำงานเสร็จ → ถามตัวเอง "อะไรจำเป็นต้องจำ?"

**พัฒนาตัวเอง:**
- วิเคราะห์ว่างานไหนทำซ้ำ → สร้าง automation/script
- ถ้าเจอ bug → แก้ + บันทึกใน MEMORY.md
- ทบทวน MEMORY.md สัปดาห์ละครั้ง — ลบของเก่าออกเสมอ

---

## 📅 Recent Activity

| วันที่ | งาน |
|--------|------|
| 2026-06-29 | สร้าง hot-cache.md, sync Discord config |
| 2026-06-28 | ตั้งค่า Discord channels, MEMORY.md อัปเดต |
| 2026-06-19 | DUE summarizer v2 — แก้ Ertapenem/มูลค่า/นับผู้ป่วย |

---

*Auto-generated — อัปเดตเมื่อมีการเปลี่ยนแปลงสำคัญ*

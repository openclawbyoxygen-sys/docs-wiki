---
title: "DUE Evaluator"
tags:
  - skill
  - due
  - excel
---

# DUE Evaluator

สรุปและประเมินเอกสาร DUE (Drug Utilization Evaluation) จากไฟล์ Excel
โดย **กุ้งมังกร** (docs agent)

## ขอบเขต

| ทำ | ไม่ทำ |
|----|--------|
| อ่าน/เขียน/จัดระเบียบเอกสาร | Trading analysis / signal |
| สรุป DUE, เชื้อก่อโรค, สิทธิ์การรักษา | วิเคราะห์กราฟ XAUUSD |
| ค้นหาข้อมูลเก่าใน vault | ตัดสินใจแทนต้าเรื่องการลงทุน |

## ไฟล์ที่รับ

| ไฟล์ | Source | Target |
|------|--------|--------|
| DUE_2026 ตึก X | Data_Jan26-Dec26 | Jan26-Dec26 + DUE_สรุปรายปี |
| สรุปเชื้อก่อโรค | Data_Jan26-Dec26 | Jan_26-Dec_26 |
| สรุปสิทธิ์การรักษา | Data_Jan26-Dec26 + ราคาต้นทุนยา | Jan_26-Dec_26 |

## Logic หลัก

### เงื่อนไขผู้ป่วย
- ดึงทุก row ที่มี HN + ชื่อยา
- ไม่กรอง eval_pass (เหมาะสม / ไม่เหมาะสม / ประเมินไม่ได้ → ดึงมาได้ทั้งหมด)

### Data_Jan26 Structure

| ข้อมูล | Column | Row |
|--------|--------|-----|
| ยาที่สั่ง (ชื่อ) | B (2) | ทุก row |
| Drug indicators | 87-102 | 3 |
| Vials | 148-163 | 3 |
| ราคาขาย (บาท) | 164-179 | 2 = ราคา, 3 = ชื่อยา |
| เชื้อก่อโรค | 117-146 | 3 |
| เหมาะสม | 185 | ทุก row |
| ไม่เหมาะสม | 186 | ทุก row |
| ประเมินไม่ได้ | 187 | ทุก row |

> ⚠️ **Ertapenem (O)/(L)**: ไม่มี header ใน row 3 สำหรับ vials section → อ่าน header จาก **row 2** (col 153/154)

## Scripts

### 1. DUE Summary
```bash
python3 due_summarizer.py <file.xlsx> --sheet=JAN26
```
Group by ยา: ผู้ป่วย, vials, มูลค่า, เหมาะสม/ไม่เหมาะสม/ประเมินไม่ได้

### 2. สรุปเชื้อก่อโรค
```bash
python3 pathogen_summarizer.py <due_file.xlsx> <target_file.xlsx> --sheet=JAN26
```
Filter: drug=1 AND pathogen=1
- ตารางบน (rows 2-17): จำนวนยาที่ใช้ (vials)
- ตารางล่าง (rows 18-33): จำนวนผู้ป่วย (คน)

### 3. สิทธิ์การรักษา
```bash
python3 rights_summarizer.py <due_file.xlsx> <target_file.xlsx> --sheet=JAN26
```
ราย row: HN, ชื่อ, สิทธิ, ยา, ราคาขาย, vials, มูลค่า, ราคาทุน, มูลค่าทุน

### Google Sheet output
```bash
python3 due_summarizer.py <file.xlsx> --sheet=FEB26 --gsheet
```
→ **ต้องยืนยัน (y/n) ก่อนเขียนทุกครั้ง**
Sheet: `https://docs.google.com/spreadsheets/d/1JR2VA_p6F9ZM6tDmAiTKs1NWF6y7LHHSFcaHFbSw1wE/edit`

## กฎที่ต้องจำ

1. **มูลค่ารวม = vials × ราคา** (ไม่ใช่ sum ของ value column)
2. **นับผู้ป่วยทุก eval** (ไม่ใช่เฉพาะ eval=1)
3. **Fosfomycin แยก Oral/INJ** ด้วย drug_code (`MOUOL1` vs `FOSOI1`)
4. **console ใช้ markdown pipe table** (Thai width ไม่ตรง)
5. **ไฟล์ DUE ตึก A/B/C/D ใช้โครงสร้างเดียวกัน**

## ข้อจำกัด

- ชื่อยาใน Data อาจต่างจาก Template → ใช้ [[Drug-Mapping]]

## ดูเพิ่มเติม

- Script อยู่ที่ `/data/.openclaw/workspace-docs/scripts/`
- Memory ละเอียดอยู่ที่ `/data/.openclaw/workspace-docs/MEMORY.md`

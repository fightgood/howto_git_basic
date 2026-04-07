# 🚀 Git Training Guide (Ultimate Edition)

## 📘 คู่มือการใช้งาน Git สำหรับเจ้าหน้าที่ (ฉบับสอนจริง + ใช้งานจริง)

---

# 🌟 ทำไมต้องใช้ Git?

Git คือเครื่องมือที่ช่วยให้:

- 🧾 เก็บประวัติการแก้ไขงาน
- 👥 ทำงานร่วมกันเป็นทีม
- ⏪ ย้อนกลับเวอร์ชันได้
- 🌿 แยกการพัฒนาเป็นส่วน ๆ (Branch)

---

# 🖥️ GitKraken (แนะนำ ⭐⭐⭐⭐⭐)

## 📌 GitKraken คืออะไร?

GitKraken คือโปรแกรม GUI สำหรับใช้งาน Git ที่ช่วยให้:

- เห็นภาพการทำงานของ Git แบบ Visual
- ลดการใช้คำสั่ง CLI
- ลดความผิดพลาดสำหรับผู้เริ่มต้น

---

## 🧭 ภาพรวมหน้าจอ GitKraken

| ส่วน         | อธิบาย                   |
| ------------ | ------------------------ |
| Graph        | แสดง commit และ branch   |
| Commit Panel | ใช้ commit               |
| File Panel   | แสดงไฟล์ที่แก้ไข         |
| Toolbar      | ปุ่ม Push / Pull / Fetch |

---

## 🔁 Workflow การใช้งาน GitKraken (Step-by-Step)

### 1️⃣ Clone Repository

- กด Clone Repo
- ใส่ URL
- เลือก Folder

---

### 2️⃣ แก้ไขไฟล์

- เปิด project ใน IDE
- แก้ไขไฟล์

---

### 3️⃣ Stage File

- ไปที่ Unstaged Files
- กด Stage

---

### 4️⃣ Commit

- ใส่ข้อความ commit
- กด Commit

---

### 5️⃣ Push

- กด Push

---

### 6️⃣ Pull

- กด Pull ก่อนเริ่มงานทุกครั้ง

---

## 🌿 การสร้าง Branch

### วิธีทำ:

- คลิกขวาที่ branch → Create branch
- ตั้งชื่อ: feature/xxx

👉 Best Practice:

- feature/login
- bugfix/api-error
- hotfix/production

---

## 🔀 การ Merge

### วิธีง่าย:

- Drag branch → ไปยัง target branch

### วิธีปกติ:

- Checkout branch เป้าหมาย
- กด Merge

---

## ⚠️ การแก้ Conflict (สำคัญมาก)

เมื่อเกิด conflict:

1. GitKraken จะแจ้งเตือน
2. เปิดไฟล์ conflict
3. เลือก:
   - Current (ของเรา)
   - Incoming (ของคนอื่น)
4. Save → Stage → Commit

---

## 🔍 การดู History

- คลิก commit
- ดูรายละเอียดการแก้ไข
- ดู diff ของไฟล์

---

## ⏪ Undo / Reset

### ย้อน commit

- Right click commit → Reset

ประเภท:

- Soft → เก็บไฟล์
- Hard → ลบหมด

---

## 🧠 เทคนิคใช้งาน GitKraken (Pro Tips 🔥)

- ใช้ Graph ดู flow งาน
- commit บ่อย ๆ
- ตั้งชื่อ branch ให้ชัด
- ใช้ Pull ก่อนทุกครั้ง
- หลีกเลี่ยง force push

---

## ❗ ข้อควรระวัง

- ห้าม commit main โดยตรง
- ห้าม force push (ยกเว้นจำเป็น)
- ระวัง reset แบบ hard

---

# 🎯 สรุป

GitKraken คือเครื่องมือที่ช่วยให้ใช้งาน Git ได้ง่ายขึ้นมาก  
เหมาะสำหรับผู้เริ่มต้นและใช้งานในองค์กร

---

✨ End of Guide

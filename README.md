# 🚀 Git Training Guide (Ultimate Edition - ZIP Version)

## 📘 คู่มือการใช้งาน Git สำหรับเจ้าหน้าที่

---

# 🖥️ GitKraken (พร้อมรูปจริงในเครื่อง)

## 📸 ตัวอย่างหน้าจอ

### Commit Graph
![Graph](images/gitkraken_graph.png)

### Commit Panel
![Commit](images/gitkraken_commit.png)

### Branch View
![Branch](images/gitkraken_branch.png)

---

# 💻 Git CLI (สรุป)

```bash
git init
git add .
git commit -m "message"
git push
```

---

<<<<<<< HEAD
=======
## 📌 Commit

```bash
git commit -m "เพิ่มระบบ login"
```

Best Practice:

- feat:
- fix:
- docs:

---

## 📜 ดู History

```bash
git log
git log --oneline
```

---

## 🔄 Undo

### ยกเลิก add

```bash
git restore --staged file.txt
```

### ยกเลิกแก้ไฟล์

```bash
git restore file.txt
```

### ย้อน commit

```bash
git reset --soft HEAD~1
git reset --hard HEAD~1
```

---

## 🌿 Branch

```bash
git branch
git branch feature/login
git checkout feature/login
git checkout -b feature/api
```

---

## 🔀 Merge

```bash
git checkout main
git merge feature/login
```

---

## 🔗 Remote

```bash
git remote add origin <url>
git remote -v
```

---

## 🚀 Push

```bash
git push origin main
```

---

## 🔄 Pull

```bash
git pull origin main
```

---

## 📥 Clone

```bash
git clone <url>
```

---

## ⚠️ Conflict

เกิดเมื่อ:

- แก้ไฟล์เดียวกัน

แก้:

- เปิดไฟล์
- เลือก code
- commit ใหม่

---

# 🖥️ GitKraken (พร้อมภาพตัวอย่าง)

## 📌 GitKraken คืออะไร

GUI Git ที่ช่วยให้:

- เห็น graph
- ลด error

---

## 🔁 Workflow

```mermaid
flowchart LR
A[Clone] --> B[Branch]
B --> C[Develop]
C --> D[Commit]
D --> E[Push]
E --> F[Merge]
```

---

## 🌿 Branch Strategy

```mermaid
gitGraph
   commit
   branch develop
   checkout develop
   commit
   branch feature/login
   commit
   checkout develop
   merge feature/login
```

---

# 📋 Best Practice

- commit บ่อย
- ใช้ branch
- pull ก่อน
- ห้าม commit .env

---

# 🎯 สรุป

CLI = ต้องรู้  
GitKraken = ใช้ง่าย

---

>>>>>>> fix
✨ End

# 🚀 Git Training Guide (Ultimate Edition - Full CLI + GitKraken)

## 📘 คู่มือการใช้งาน Git สำหรับเจ้าหน้าที่ (ฉบับสมบูรณ์ระดับอบรม)

---

# 🌟 ทำไมต้องใช้ Git?

Git คือ Version Control System ที่ช่วย:

- 🧾 เก็บประวัติ
- 👥 ทำงานเป็นทีม
- ⏪ rollback ได้
- 🌿 แยก branch

---

# 🧠 Concept Git

```mermaid
flowchart LR
A[Working Directory] --> B[Staging Area]
B --> C[Local Repo]
C --> D[Remote Repo]
```

---

# 💻 Git CLI (ละเอียด 🔥)

## 🔧 Setup ครั้งแรก

ก่อนใช้งาน Git คุณต้องตั้งค่าข้อมูลส่วนตัวของคุณก่อน เพื่อให้ Git รู้ว่าคุณคือใครเมื่อทำการ commit

```bash
# ตั้งชื่อผู้ใช้
git config --global user.name "ชื่อของคุณ"

# ตั้งอีเมล
git config --global user.email "your@email.com"

# ตรวจสอบการตั้งค่า
git config --list
```

**คำอธิบาย:**

- `user.name`: ชื่อที่แสดงในประวัติ commit
- `user.email`: อีเมลที่เชื่อมโยงกับ commit
- `--global`: ตั้งค่าให้ใช้กับทุก repository ในเครื่องนี้

---

## 📁 เริ่มต้น Project

เมื่อต้องการเริ่มใช้งาน Git ในโปรเจกต์ใหม่หรือโฟลเดอร์ที่มีอยู่

```bash
# สร้าง repository ใหม่ในโฟลเดอร์ปัจจุบัน
git init
```

**คำอธิบาย:**

- คำสั่งนี้จะสร้างโฟลเดอร์ `.git` ซึ่งเป็นที่เก็บข้อมูล Git ของโปรเจกต์
- หลังจากนี้ คุณสามารถเริ่ม add และ commit ไฟล์ได้

---

## 🔍 ตรวจสอบสถานะ

ใช้คำสั่งนี้เพื่อดูสถานะของไฟล์ใน working directory

```bash
git status
```

**คำอธิบาย:**

- แสดงไฟล์ที่เปลี่ยนแปลง, เพิ่มใหม่, หรือพร้อม commit
- สถานะไฟล์:
  - **Untracked**: ไฟล์ใหม่ที่ Git ยังไม่ติดตาม
  - **Modified**: ไฟล์ที่มีการแก้ไขหลังจาก commit ล่าสุด
  - **Staged**: ไฟล์ที่พร้อม commit (หลังจาก git add)

---

## ➕ Add

เพิ่มไฟล์เข้า staging area ก่อน commit

```bash
# เพิ่มไฟล์ทั้งหมดที่เปลี่ยนแปลง
git add .

# เพิ่มไฟล์เฉพาะ
git add file.txt

# เพิ่มหลายไฟล์
git add file1.txt file2.txt
```

**คำอธิบาย:**

- `git add .`: เพิ่มไฟล์ทั้งหมดในโฟลเดอร์ปัจจุบันและ subfolders
- `git add <file>`: เพิ่มไฟล์เฉพาะ
- หลังจาก add แล้ว ไฟล์จะอยู่ในสถานะ "staged" และพร้อม commit

---

## 📌 Commit

บันทึกการเปลี่ยนแปลงเข้า repository

```bash
# Commit ด้วยข้อความ
git commit -m "เพิ่มระบบ login"

# Commit และแก้ไขข้อความใน editor
git commit

# Commit ไฟล์เฉพาะ
git commit file.txt -m "แก้ไข bug"
```

**Best Practice สำหรับข้อความ commit:**

- ใช้ภาษาอังกฤษหรือภาษาที่ทีมใช้
- เริ่มด้วยคำกริยา เช่น:
  - `feat:` สำหรับฟีเจอร์ใหม่
  - `fix:` สำหรับแก้ไข bug
  - `docs:` สำหรับเอกสาร
  - `refactor:` สำหรับปรับโครงสร้างโค้ด
- ตัวอย่าง: `feat: add user authentication system`

**คำอธิบาย:**

- `-m`: ระบุข้อความ commit โดยตรง
- ถ้าไม่ใช้ `-m` จะเปิด editor ให้พิมพ์ข้อความยาว

---

## 📜 ดู History

ดูประวัติการ commit

```bash
# ดูประวัติแบบละเอียด
git log

# ดูแบบสรุป (หนึ่งบรรทัดต่อ commit)
git log --oneline

# ดูประวัติของไฟล์เฉพาะ
git log -- file.txt

# ดูการเปลี่ยนแปลงในแต่ละ commit
git log --patch
```

**คำอธิบาย:**

- `git log`: แสดงรายละเอียด commit รวมถึง author, date, และ message
- `--oneline`: แสดง commit hash สั้นและ message
- `--patch`: แสดง diff ของแต่ละ commit

---

## 🔄 Undo และ Reset

### ยกเลิกการ add (unstaged)

```bash
# ยกเลิก add ไฟล์เฉพาะ
git restore --staged file.txt

# ยกเลิก add ไฟล์ทั้งหมด
git restore --staged .
```

### ยกเลิกการแก้ไขไฟล์ (discard changes)

```bash
# คืนไฟล์กลับไปเป็นสถานะหลัง commit ล่าสุด
git restore file.txt
```

### ย้อน commit

```bash
# ย้อน commit แต่เก็บการเปลี่ยนแปลงไว้ใน working directory (--soft)
git reset --soft HEAD~1

# ย้อน commit และ unstaged การเปลี่ยนแปลง (--mixed, default)
git reset HEAD~1

# ย้อน commit และลบการเปลี่ยนแปลงทั้งหมด (--hard)
git reset --hard HEAD~1
```

**คำอธิบาย:**

- `HEAD~1`: ย้อนไป 1 commit จาก commit ล่าสุด
- `--soft`: เก็บการเปลี่ยนแปลงไว้ใน staging area
- `--mixed`: เก็บไว้ใน working directory แต่ unstaged
- `--hard`: ลบการเปลี่ยนแปลงทั้งหมด (ระวัง! ไม่สามารถกู้คืนได้)

---

## 🌿 Branch

จัดการ branch สำหรับการพัฒนาฟีเจอร์แยกกัน

```bash
# ดู branch ทั้งหมด
git branch

# ดู branch รวม remote
git branch -a

# สร้าง branch ใหม่
git branch feature/login

# สลับไป branch อื่น
git checkout feature/login

# สร้างและสลับไป branch ใหม่ในคำสั่งเดียว
git checkout -b feature/api

# ลบ branch
git branch -d feature/old-branch
```

**คำอธิบาย:**

- Branch คือ pointer ไปยัง commit หนึ่งๆ
- `main` หรือ `master`: branch หลัก
- ใช้ branch เพื่อพัฒนาฟีเจอร์ใหม่โดยไม่กระทบ main branch

---

## 🔀 Merge และ Rebase

รวมการเปลี่ยนแปลงจาก branch อื่น

### Merge

```bash
# สลับไป branch หลัก
git checkout main

# รวม branch feature/login เข้า main
git merge feature/login
```

**คำอธิบาย:**

- สร้าง merge commit ที่รวมประวัติของทั้งสอง branch
- ถ้ามี conflict จะต้องแก้ก่อน

### Rebase

```bash
# สลับไป branch ที่ต้องการ rebase
git checkout feature/login

# ย้าย base ของ branch นี้ไปยัง main ล่าสุด
git rebase main
```

**คำอธิบาย:**

- ย้าย commit ของ branch ปัจจุบันไปอยู่บน commit ล่าสุดของ branch เป้าหมาย
- ทำให้ประวัติดูเป็นเส้นตรง ไม่มี merge commit

---

## 🔗 Remote Repository

จัดการ repository ระยะไกล

```bash
# เพิ่ม remote repository
git remote add origin https://github.com/user/repo.git

# ดู remote ทั้งหมด
git remote -v

# ลบ remote
git remote remove origin

# เปลี่ยน URL ของ remote
git remote set-url origin https://github.com/newuser/newrepo.git
```

**คำอธิบาย:**

- `origin`: ชื่อ default ของ remote repository
- ใช้สำหรับ push และ pull โค้ด

---

## 🚀 Push

ส่ง commit ไปยัง remote repository

```bash
# Push branch ปัจจุบันไป origin
git push origin main

# Push branch ใหม่ครั้งแรก
git push -u origin feature/new-feature

# Force push (ระวัง! จะเขียนทับ remote)
git push --force origin main
```

**คำอธิบาย:**

- `-u`: ตั้ง upstream branch ให้ push อัตโนมัติครั้งต่อไป
- `--force`: บังคับ push แม้จะมี conflict (ใช้เฉพาะกรณีจำเป็น)

---

## 🔄 Pull และ Fetch

ดึงการเปลี่ยนแปลงจาก remote

```bash
# Pull และ merge อัตโนมัติ
git pull origin main

# ดึงข้อมูลจาก remote แต่ไม่ merge
git fetch origin

# หลัง fetch แล้ว merge เอง
git merge origin/main
```

**คำอธิบาย:**

- `git pull`: เท่ากับ `git fetch` + `git merge`
- `git fetch`: ดึงข้อมูลใหม่จาก remote แต่ไม่เปลี่ยน working directory

---

## 📥 Clone

โคลน repository จาก remote

```bash
# โคลน repository
git clone https://github.com/user/repo.git

# โคลนไปยังโฟลเดอร์เฉพาะ
git clone https://github.com/user/repo.git my-project
```

**คำอธิบาย:**

- สร้างโฟลเดอร์ใหม่และโคลนทั้ง repository รวมประวัติ

---

## ⚠️ จัดการ Conflict

เมื่อ merge หรือ pull มี conflict

1. Git จะแสดงไฟล์ที่มี conflict
2. เปิดไฟล์และแก้ไข:
   ```
   <<<<<<< HEAD
   code จาก branch ปัจจุบัน
   =======
   code จาก branch ที่ merge
   >>>>>>> feature/branch
   ```
3. เลือก code ที่ต้องการ หรือรวมทั้งสอง
4. Add และ commit ไฟล์ที่แก้แล้ว

```bash
# หลังแก้ conflict แล้ว
git add conflicted-file.txt
git commit -m "Resolve merge conflict"
```

**คำอธิบาย:**

- Conflict เกิดเมื่อสอง branch แก้ไขส่วนเดียวกันของไฟล์
- ต้องแก้ไขด้วยมือก่อน commit

---

## 🔍 ดู Diff

ดูความแตกต่างของไฟล์

```bash
# ดูการเปลี่ยนแปลงที่ยังไม่ staged
git diff

# ดูการเปลี่ยนแปลงที่ staged แล้ว
git diff --staged

# ดู diff ระหว่าง commit
git diff HEAD~1 HEAD

# ดู diff ของไฟล์เฉพาะ
git diff file.txt
```

**คำอธิบาย:**

- แสดงบรรทัดที่เพิ่ม (+) และลบ (-)

---

## 💾 Stash

เก็บการเปลี่ยนแปลงชั่วคราว

```bash
# เก็บการเปลี่ยนแปลง
git stash

# เก็บพร้อมข้อความ
git stash save "working on login"

# ดู stash ที่เก็บไว้
git stash list

# นำกลับมา
git stash pop

# นำกลับมาแต่ไม่ลบ stash
git stash apply

# ลบ stash
git stash drop stash@{0}
```

**คำอธิบาย:**

- ใช้เมื่อต้องการเปลี่ยน branch แต่ยังไม่พร้อม commit
- `pop`: นำกลับและลบ stash
- `apply`: นำกลับแต่เก็บ stash ไว้

---

## 🏷️ Tag

ทำเครื่องหมาย commit สำคัญ

```bash
# สร้าง tag ไลท์เวท
git tag v1.0

# สร้าง tag พร้อม annotation
git tag -a v1.0 -m "Release version 1.0"

# ดู tag
git tag

# Push tag ไป remote
git push origin v1.0

# Push tag ทุกอัน
git push origin --tags
```

**คำอธิบาย:**

- Tag ใช้สำหรับ version release
- Annotated tag มีข้อมูลเพิ่มเติม
- Lightweight tag เป็น pointer ไปยัง commit เฉยๆ

---

## 🔧 .gitignore

ไฟล์ที่บอก Git ไม่ให้ติดตามไฟล์บางประเภท

สร้างไฟล์ `.gitignore` และใส่:

```
# Logs
*.log
node_modules/
.DS_Store
```

**คำอธิบาย:**

- ไฟล์ที่ match pattern จะไม่ถูก tracked โดย Git
- ใช้สำหรับไฟล์ build, dependencies, หรือไฟล์ส่วนตัว

---

## 📊 Git Statistics

ดูสถิติของ repository

```bash
# ดูจำนวน commit ต่อ author
git shortlog -sn

# ดู contribution
git log --author="Your Name" --oneline | wc -l
```

**คำอธิบาย:**

- `shortlog`: สรุป commit ตาม author
- สามารถใช้ tool เพิ่มเติมเช่น `gitstats` หรือ `git-quick-stats`

---

# 🖥️ GitKraken (พร้อมภาพตัวอย่าง)

## 📌 GitKraken คืออะไร

GUI Git ที่ช่วยให้:

- เห็น graph
- ลด error

---

## 📸 ตัวอย่างหน้าจอ GitKraken

### Graph View

![GitKraken Graph](https://support.gitkraken.com/img/gk-commit-graph.png)

### Commit Panel

![GitKraken Commit](https://support.gitkraken.com/img/gk-commit-panel.png)

### Branch View

![GitKraken Branch](https://support.gitkraken.com/img/gk-branch.png)

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

✨ End

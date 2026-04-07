# ขั้นตอนการอัปโหลด Dashboard ไป GitHub

## ขั้นตอนที่ 1: เตรียมไฟล์

ไฟล์ที่จำเป็น:
- `Helpdesk_CMS_Enhanced_Dashboard.html` (ไฟล์แดชบอร์ดหลัก)
- `abandoned_calls_real_data.json` (ข้อมูลสายที่ยกเลิก)
- `cms_real_data.json` (ข้อมูล KPI และเอเจนต์)
- `README.md` (คำอธิบายโปรเจ็กต์)

## ขั้นตอนที่ 2: สร้าง Repository บน GitHub

### วิธี A: ผ่านเว็บไซต์ GitHub
1. ไปที่ https://github.com/new
2. กรอก Repository name: `helpdesk-dashboard`
3. กรอก Description: `IT Helpdesk Real-time CMS Dashboard`
4. เลือก Public (เพื่อให้ทุกคนเห็น)
5. เลือก "Add a README file"
6. คลิก "Create repository"

### วิธี B: ผ่าน Command Line (Git Bash / Terminal)
```bash
git config --global user.name "ชื่อของคุณ"
git config --global user.email "email@example.com"
```

## ขั้นตอนที่ 3: Clone Repository ลงเครื่อง

```bash
git clone https://github.com/username/helpdesk-dashboard.git
cd helpdesk-dashboard
```

## ขั้นตอนที่ 4: เพิ่มไฟล์โครงการ

```bash
# คัดลอกไฟล์จากโฟลเดอร์ Report Fern ไปที่ helpdesk-dashboard
cp path/to/Helpdesk_CMS_Enhanced_Dashboard.html ./index.html
cp path/to/abandoned_calls_real_data.json ./data/
cp path/to/cms_real_data.json ./data/
```

## ขั้นตอนที่ 5: สร้างไฟล์ README.md

```markdown
# IT Helpdesk CMS Dashboard

ระบบแดชบอร์ดแบบเรียลไทม์สำหรับติดตามประสิทธิภาพศูนย์บริการ

## ลักษณะเด่น
- แสดงข้อมูล 9 KPI ในเวลาจริง
- ตาราง Callbacks และ Abandoned Calls พร้อมชื่อเอเจนต์
- กราฟวิเคราะห์ตามช่วงเวลา
- ธีมสีเข้ม (Dark Theme)

## การใช้งาน
1. เปิดไฟล์ `index.html` ในเบราว์เซอร์
2. ดูข้อมูล KPI 9 ตัวในแถวแรก
3. ดูตารางสายที่ยกเลิกและการเรียกกลับ
4. ดูกราฟวิเคราะห์ข้อมูลตามชั่วโมง

## ไฟล์ข้อมูล
- `data/cms_real_data.json` - ข้อมูล KPI และเอเจนต์ 13 คน
- `data/abandoned_calls_real_data.json` - สายที่ยกเลิก 12 สาย

## เทคโนโลยี
- HTML5
- CSS3 (Dark Theme)
- JavaScript (Vanilla)
- Chart.js v3.9.1

## ผู้พัฒนา
[ชื่อของคุณ]

## สัญญาอนุญาต
MIT
```

## ขั้นตอนที่ 6: Commit และ Push ไป GitHub

```bash
# ตรวจสอบไฟล์ที่เพิ่มเข้ามา
git status

# เพิ่มไฟล์ทั้งหมดเข้า staging
git add .

# สร้าง commit
git commit -m "Initial commit: Add IT Helpdesk Dashboard"

# Push ไปยัง GitHub
git push -u origin main
```

## ขั้นตอนที่ 7: เปิดใช้ GitHub Pages (ทำให้เป็นเว็บไซต์)

### วิธี A: ผ่าน GitHub Web Interface
1. ไปที่ Repository settings
2. ไปที่ "Pages" (ด้านซ้าย)
3. ใน "Source" เลือก "main" branch
4. เลือก folder "/" (root)
5. คลิก "Save"
6. รอ 1-2 นาที
7. URL จะปรากฏเป็น `https://username.github.io/helpdesk-dashboard/`

### วิธี B: ใช้ GitHub Actions
สร้างไฟล์ `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
```

## ขั้นตอนที่ 8: เข้าใช้งาน Dashboard ที่เป็นเว็บไซต์

```
https://username.github.io/helpdesk-dashboard/
```

## ขั้นตอนต่อไป (ปรับปรุง)

### 1. เพิ่ม Live Data Update
- ใช้ API endpoint แทน static JSON
- เพิ่ม WebSocket สำหรับ real-time updates

### 2. เพิ่ม Features
- Export ข้อมูลเป็น PDF/Excel
- Filter ตามวันที่
- User authentication

### 3. เพิ่ม Backend
- ใช้ Node.js/Express
- Database (MongoDB/PostgreSQL)
- REST API

### 4. Deployment ที่ดีกว่า
- ใช้ Vercel, Netlify, หรือ Railway
- ใช้ Docker
- ใช้ CI/CD pipeline

## การอัปเดต Repository

หากต้องการอัปเดตไฟล์:

```bash
# ทำการแก้ไขไฟล์
# ...

# Commit changes
git add .
git commit -m "Update: เพิ่ม feature X"

# Push
git push
```

## การ Clone โปรเจ็กต์ของคุณ

ใครก็ตามที่ต้องการใช้งาน:

```bash
git clone https://github.com/username/helpdesk-dashboard.git
cd helpdesk-dashboard
# เปิด index.html ในเบราว์เซอร์
```

## แก้ไขปัญหา

### Dashboard ไม่เห็นข้อมูล
- ตรวจสอบ path ของ JSON files
- ใช้ browser console (F12) เพื่อดู error

### GitHub Pages ไม่อัปเดต
- ล้าง cache (Ctrl+Shift+Delete)
- รอ 5 นาที
- ตรวจสอบ branch ใน settings

### สำหรับการอัปโหลด Private Repository
- ใช้ SSH key แทน HTTPS
- ตั้งค่า Deploy Key ใน Repository settings

---

## โครงสร้างไฟล์ที่เสร็จ

```
helpdesk-dashboard/
├── index.html (Helpdesk_CMS_Enhanced_Dashboard.html)
├── README.md
├── data/
│   ├── cms_real_data.json
│   └── abandoned_calls_real_data.json
└── .github/
    └── workflows/
        └── deploy.yml (ถ้าใช้ GitHub Actions)
```

---

**หมายเหตุ:** 
- แทนที่ `username` ด้วย GitHub username ของคุณ
- หากไม่มี Git ติดตั้ง ดาวน์โหลดจาก: https://git-scm.com/

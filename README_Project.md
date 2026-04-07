# IT Helpdesk Real-time CMS Dashboard

ระบบแดชบอร์ดแบบเรียลไทม์สำหรับติดตามประสิทธิภาพศูนย์บริการ IT (Call Center)

## 📊 ลักษณะเด่น

- ✅ แสดงข้อมูล **9 KPI** ในเวลาจริง (อัปเดตทีละวินาที)
- ✅ ตาราง **Abandoned Calls** พร้อมเบอร์โทรศัพท์และชื่อเอเจนต์
- ✅ ตาราง **Pending Callbacks** สำหรับการติดตามผล
- ✅ กราฟวิเคราะห์ตามช่วงเวลา (Peak Hours, Abandoned by Hour)
- ✅ ประสิทธิภาพเอเจนต์ 13 คน
- ✅ ธีมสีเข้ม (Dark Theme) เหมาะสำหรับการติดตามตลอด 24 ชั่วโมง
- ✅ ออกแบบให้ใช้ได้กับหลายขนาดหน้าจอ (Responsive)

## 📈 ข้อมูล 9 KPI

| ที่ | ตัวชี้วัด | คำอธิบาย | ค่าปัจจุบัน |
|---|---|---|---|
| 1 | In Call | จำนวนเอเจนต์ที่คุยสายอยู่ | 13 คน |
| 2 | Total Calls | จำนวนสายทั้งหมดในวัน | 709 สาย |
| 3 | Avg AHT | ระยะเวลาคุยเฉลี่ย | 03:28 นาที |
| 4 | Avg ACW | เวลาหลังคุยเฉลี่ย | 00:00 นาที |
| 5 | Queue Waiting | จำนวนสายที่รอเชื่อมต่อ | 24 สาย |
| 6 | Escalated | สายที่โยกย้ายระดับสูง | 7 สาย |
| 7 | Callbacks | การเรียกกลับที่กำหนดการไว้ | 18 ครั้ง |
| 8 | ISL % | แก้ไขในระดับแรก | 92% |
| 9 | Abandoned | สายที่ลูกค้าวางก่อนตอบ | 12 สาย |

## 🎯 ข้อมูลจริงใช้งาน

**วันที่ 31 มีนาคม 2026**

- **ศูนย์บริการ:** VDN 1110
- **เอเจนต์ทั้งหมด:** 13 คน
- **จำนวนสายรวม:** 709 สาย
  - สายที่ตอบรับ: 678 สาย
  - สายที่ยกเลิก: 31 สาย
  - อัตราสายยกเลิก: 8.5%

**ปัญหาหลัก:**
- ช่วง 08:00-09:00 น. มีปัญหามากที่สุด (12 สายยกเลิก)
- เวลารอเฉลี่ย: 0.92 นาที
- ต้องจัดสรรเอเจนต์เพิ่มเติมในช่วงเช้า

## 🚀 วิธีใช้งาน

### ใช้งานในเครื่อง
```bash
# เปิดไฟล์ index.html ในเบราว์เซอร์
# หรือให้ Simple HTTP Server
python -m http.server 8000
# เข้าไปที่: http://localhost:8000
```

### ใช้งานออนไลน์ (GitHub Pages)
```
https://username.github.io/helpdesk-dashboard/
```

## 📁 โครงสร้างไฟล์

```
helpdesk-dashboard/
├── index.html                          # ไฟล์แดชบอร์ดหลัก
├── README.md                          # คำอธิบายโปรเจ็กต์
├── .gitignore                         # ไฟล์ที่ไม่ส่ง Git
│
├── data/
│   ├── cms_real_data.json            # ข้อมูล KPI และเอเจนต์
│   └── abandoned_calls_real_data.json # สายที่ยกเลิก 12 สาย
│
├── docs/
│   ├── GitHub_Upload_Guide.md        # คู่มือการอัปโหลด GitHub
│   ├── IT_Helpdesk_Dashboard_Summary.pdf      # สรุป PDF
│   └── IT_Helpdesk_Dashboard_Guide_Thai.docx  # คู่มือไทย
│
└── .github/
    └── workflows/
        └── deploy.yml                # GitHub Actions (ถ้าใช้)
```

## 🛠️ เทคโนโลยีที่ใช้

- **Frontend:** HTML5, CSS3, JavaScript (Vanilla)
- **Visualization:** Chart.js v3.9.1
- **Data Format:** JSON
- **Theme:** Dark Theme (1F4E78 - 00FF88)
- **Responsive:** Mobile-friendly, All browsers

## 💻 เอเจนต์ 5 อันดับแรก

| อันดับ | ชื่อ | สายทั้งหมด | AHT | ประสิทธิภาพ |
|---|---|---|---|---|
| 1 | Aukarapol Y | 71 | 02:53 | สูง ⭐⭐⭐ |
| 2 | Sutthirat Phaothong | 69 | 03:04 | สูง ⭐⭐⭐ |
| 3 | Phatcha Worasakkulch | 67 | 03:24 | สูง ⭐⭐⭐ |
| 4 | Suwanna Changoram | 64 | 03:12 | สูง ⭐⭐⭐ |
| 5 | Tanawin Suwanprateep | 59 | 03:25 | สูง ⭐⭐⭐ |

## 📞 สายที่ยกเลิก (12 สาย)

| ลำดับ | เบอร์โทร | เอเจนต์ | เวลา | รอ (นาที) | ช่วงเวลา |
|---|---|---|---|---|---|
| 1 | +66 601041 | Aukarapol Y | 08:38 | 1.0 | เช้า |
| 2 | +66 611262 | Sutthirat P. | 08:39 | 1.0 | เช้า |
| ... | ... | ... | ... | ... | ... |
| 12 | +66 600520 | Tawatchai P. | 09:15 | 2.0 | เช้า |

**ข้อเสนอแนะ:**
1. โทรติดตามลูกค้า 12 คน
2. เพิ่มเอเจนต์ในช่วง 8:00-9:00 น.
3. ให้การอบรมแก่เอเจนต์
4. บันทึกผลการติดตาม

## 🎨 การปรับแต่ง

### เปลี่ยนสี
แก้ไขใน `index.html` ส่วน CSS:
```css
--primary-color: #1F4E78  /* สีหลัก */
--accent-color: #00FF88   /* สีสำเน้น */
```

### อัปเดตข้อมูล
แก้ไขไฟล์ JSON ใน `data/` folder

### เพิ่ม Features
- Real-time updates ด้วย WebSocket
- Authentication & Login
- Data export (PDF/Excel)
- Date range filter

## 📚 ฟิลเตอร์วันที่ (ขยาย)

ปรจุบันแสดง 31 มีนาคม 2026 สามารถเพิ่ม:
- Date picker
- Monthly reports
- Trend analysis

## 🔧 ขั้นตอนการพัฒนา

### Phase 1: ✅ สำเร็จ
- Dashboard HTML พร้อมข้อมูลจริง
- 9 KPI metrics
- Abandoned calls table
- Agent performance chart
- Thai language documentation

### Phase 2: In Progress
- Upload to GitHub
- Enable GitHub Pages
- Create documentation

### Phase 3: Next
- Backend API (Node.js/Express)
- Real-time database
- User authentication
- Mobile app

## 📖 เอกสารประกอบ

- **GitHub_Upload_Guide.md** - คู่มือการอัปโหลด GitHub ทีละขั้นตอน
- **IT_Helpdesk_Dashboard_Summary.pdf** - สรุป PDF 6 หน้า
- **IT_Helpdesk_Dashboard_Guide_Thai.docx** - คู่มือเป็นภาษาไทยโดยละเอียด

## ⚙️ การปรับปรุง

เป้าหมายการปรับปรุง:
- [ ] ลดอัตราสายยกเลิกเหลือ 5%
- [ ] เพิ่ม ISL เป็น 95%
- [ ] ลด AHT ลง 5%
- [ ] เรียกกลับให้สำเร็จ 100%

## 🆘 แก้ไขปัญหา

### Dashboard ไม่แสดงข้อมูล
- ตรวจสอบ JSON path
- เปิด browser console (F12)
- ลบ cache และ reload

### GitHub Pages ไม่อัปเดต
- รอ 2-5 นาที
- Ctrl+Shift+Del เพื่อล้าง cache
- ตรวจสอบ settings

## 📞 ติดต่อ

- **ผู้พัฒนา:** BFFBKK
- **Email:** bffaiproject1@gmail.com
- **วันสร้าง:** 7 เมษายน 2026

## 📄 สัญญาอนุญาต

MIT License - สามารถใช้งานและแก้ไขได้อย่างอิสระ

---

**หมายเหตุ:** Dashboard นี้ใช้ข้อมูลจริงจากศูนย์บริการ และสามารถปรับแต่งให้เหมาะสมกับความต้องการของคุณได้

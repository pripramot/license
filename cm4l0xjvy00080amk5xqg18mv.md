---
title: "ค้นหาเเละลบรายการที่ซ้ำกันได้อย่างง่ายดาย ด้วย DUDE (DUplicates DEtector)"
seoTitle: "ลบข้อมูลซ้ำง่าย ๆ ด้วย DUDE"
seoDescription: "ค้นหาและลบไฟล์ซ้ำง่ายๆ ด้วย DUDE แพลตฟอร์มข้าม GUI ซิงค์ ปลอดภัย บน Windows ประหยัดพื้นที่และทรัพยากรของคุณ!"
datePublished: Thu Dec 12 2024 07:54:54 GMT+0000 (Coordinated Universal Time)
cuid: cm4l0xjvy00080amk5xqg18mv
slug: sparesos-duplicates-detector
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1733990004876/00e45464-7821-4b0e-8d31-62b369824e97.jpeg
tags: sparesos, duplicates-detector

---

ค้นหาเเละลบรายการที่ซ้ำกันได้อย่างง่ายดาย ด้วย DUDE (DUplicates DEtector)  
ยูทิลิตี้ GUI ข้ามแพลตฟอร์มสำหรับการค้นหาไฟล์ที่ซ้ำกันลบหรือเชื่อมโยงเพื่อประหยัดพื้นที่

## **หน้าตา:**

* สแกนหาไฟล์ที่ซ้ำกันใน**โฟลเดอร์ที่กำหนดหลายโฟลเดอร์** (สูงสุด 8) โหมดการแสดงผล **"Cross paths"** เสริม
    
* **พารามิเตอร์บรรทัดคำสั่ง**เสริมเพื่อเริ่มการสแกนทันทีหรือรวม **Dude** เข้ากับตัวจัดการไฟล์ที่คุณชื่นชอบ
    
* แผงซิ**งโครไนซ์**สองแผง:
    
    * กลุ่มของรายการที่ซ้ำกัน
        
    * ไดเร็กทอรีของไฟล์ที่เลือก
        
* การประมวลผลสองขั้นตอน:
    
    * การทำเครื่องหมายแบบโต้ตอบของไฟล์ที่มีหลายเกณฑ์
        
    * การดำเนินการกับไฟล์ที่ทำเครื่องหมายไว้ (ย้ายไปยังถังขยะ/ถังรีไซเคิล, ลบ, ฮาร์ดลิงก์, ซอฟต์ลิงก์, สร้างหน้าต่าง.lnk ไฟล์ทางลัด)
        
* รองรับ**นิพจน์ทั่วไป**หรือไวยากรณ์นิพจน์ **glob**
    
* การค้นหารายการที่ซ้ำกันตาม**แฮชของ**เนื้อหาไฟล์ ชื่อไฟล์หรือนามสกุลที่แตกต่างกันจะไม่ส่งผลต่อผลการค้นหา
    
* ทำงานบน **Windows**
    

### **💥 ข่าวสำคัญในเวอร์ชัน 2.x:**

* **โหมดความคล้ายคลึงกันของภาพ** พร้อมการแคช พารามิเตอร์ความไว และการตรวจจับภาพที่หมุน
    
* **หน้าต่างแสดงตัวอย่าง**สำหรับรูปภาพและไฟล์ข้อความ
    
* โหมดการแสดงผล **"ไดเร็กทอรีเดียวกัน"**
    

## **ทำไมต้องมีแอปพลิเคชั่นป้องกันความซ้ำซ้อนอื่น**

* เพราะคุณต้องดูบริบทของไฟล์ที่ถูกลบและใช้แอปพลิเคชันดังกล่าวอย่างชัดเจนปลอดภัยและง่ายดาย
    

## **ภาพหน้าจอ:**

#### **ตัวอย่างการใช้งาน GUI:**

[![ข้อมูลภาพ](https://github.com/PJDude/dude/raw/main/info/dude.gif align="left")](https://github.com/PJDude/dude/blob/main/info/dude.gif)

#### **การสแกนทันทีเริ่มต้นด้วยพารามิเตอร์ CLI ตัวอย่**[**าง:**](https://pyinstaller.org/en/stable)

[![ข้อมูลภาพ](https://github.com/PJDude/dude/raw/main/info/cmd.gif align="left")](https://github.com/PJDude/dude/blob/main/info/cmd.gif)

#### [**กล่อง**](https://pyinstaller.org/en/stable)**โต้ตอบการตั้งค่า:**

[![ข้อมูลภาพ](https://github.com/PJDude/dude/raw/main/info/settings.png align="left")](https://github.com/PJDude/dude/blob/main/info/settings.png)

## ดาวน์โหลด:

คุณสามารถดาวน์โหลด DUDE สำหรับ **Windows** ได้จากหน้า [Releases](https://github.com/PJDude/dude/releases) ซึ่งมีแพ็คเกจที่พร้อมใช้งานทันที

## การใช้งานทั่วไป:

1. สแกนหาไฟล์ที่ซ้ำกัน
    
2. ทำเครื่องหมายไฟล์ที่ต้องการจัดการ
    
3. ดำเนินการกับไฟล์ที่ทำเครื่องหมาย (ลบ, ซอฟต์ลิงก์, ฮาร์ดลิงก์)
    

## เคล็ดลับการใช้งาน:

* ใช้แป้นพิมพ์ลัดเพื่อความสะดวก
    
* จำกัดพื้นที่การสแกนเพื่อประสิทธิภาพ
    
* ปรับปรุงการใช้งานบรรทัดคำสั่งโดยแก้ไขตัวแปรสภาพแวดล้อม **PATH**
    

## แพลตฟอร์มที่รองรับ:

* Windows (10, 11)
    

## ตัวอย่างบรรทัดคำสั่ง:

```bash
# เริ่มสแกนในไดเรกทอรีปัจจุบัน
dude.exe
```

```bash
# สร้างรายงาน CSV
dude.exe --output report.csv
```

```bash
# สแกนโฟลเดอร์เฉพาะ
dude.exe --folder "C:\path\to\folder"
```

```bash
# ลบไฟล์ที่ซ้ำกัน
dude.exe --delete
```

## ปัญหาผลบวกลวง

โปรดทราบถึงปัญหาที่อาจเกิดขึ้นกับ Windows Defender และโปรแกรมป้องกันไวรัสอื่นๆ

## การพกพา

DUDE สามารถทำงานได้โดยไม่ต้องติดตั้งและจัดเก็บข้อมูลในโฟลเดอร์เฉพาะ

## ข้อมูลทางเทคนิค

DUDE ใช้การคำนวณแฮชเพื่อค้นหาไฟล์ที่ซ้ำกันและจัดการไฟล์อย่างปลอดภัย
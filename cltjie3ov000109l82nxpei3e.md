---
title: "MindsDB"
datePublished: Sat Mar 09 2024 03:11:22 GMT+0000 (Coordinated Universal Time)
cuid: cltjie3ov000109l82nxpei3e
slug: mindsdb
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/zwsHjakE_iI/upload/80ee669e57e0ea2f874505b3fed20766.jpeg

---

# การปรับใช้ MindsDB บนแพลตฟอร์ม Google Cloud

[#บทช่วยสอน](https://community.ops.io/t/tutorials)[#เมฆหมอก](https://community.ops.io/t/cloudops)[#ข้อมูล](https://community.ops.io/t/dataops)[#จีซีพี](https://community.ops.io/t/gcp)

[![ปิดบัง](https://community.ops.io/images/Nt2jivMj1vguK1mZtVmGwLBq1iqFgWcv7ZzXlMdcw_w/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL203dDRp/emNiZGtmZWd6ZnBx/MDh3LnBuZw align="left")](https://community.ops.io/images/Nt2jivMj1vguK1mZtVmGwLBq1iqFgWcv7ZzXlMdcw_w/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL203dDRp/emNiZGtmZWd6ZnBx/MDh3LnBuZw)

## การแนะนำ

MindsDB เป็นเลเยอร์ AI ที่ทำงานบนฐานข้อมูลที่มีอยู่เพื่อฝึกฝน พัฒนา และปรับใช้โมเดลการเรียนรู้ของเครื่องที่ดีที่สุดได้อย่างราบรื่น MindsDB ดำเนินการประมวลผลข้อมูลจากภายในฐานข้อมูลล่วงหน้าและป้อนข้อมูลดังกล่าวไปยังโมเดลการเรียนรู้ของเครื่องโดยใช้ SQL มาตรฐานเพื่อทำการคาดการณ์ที่แม่นยำและแม่นยำตามที่ต้องการ

ในบทช่วยสอนนี้ เราจะปรับใช้ MindsDB บนอินสแตนซ์ GCP Compute Engine ดำเนินการผ่าน GUI และตรวจสอบตารางเริ่มต้นที่แสดงหลังจากการปรับใช้

## การปรับใช้ GCP Compute Engine

แพลตฟอร์ม Google Cloud เป็นที่รู้จักของทุกคนและถูกใช้โดยคนจำนวนมากในยุคปัจจุบัน ถึงเวลาที่จะดำเนินการสร้างเครื่องเสมือนบน GCP เพื่อเริ่มต้นใช้งาน คุณสามารถทำตามขั้นตอนด้านล่างเพื่อดำเนินการให้เสร็จสิ้น

**ขั้นตอนที่ 1:** เข้าสู่ระบบบัญชี GCP ของคุณหรือสมัครใช้งาน[ที่นี่](https://cloud.google.com/landing/free-trial) GCP มอบเครดิตมูลค่า 300$ เป็นเวลา 90 วันเพื่อทดลองใช้แพลตฟอร์ม

[![การสมัครสมาชิก GCP](https://community.ops.io/images/PYsHi9OD0HwyJr8puNBOaqmehWcYXGx1JFOvFiOC_bg/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzLzI0NXJ2/Zm9leXJoMGRrbTdt/cHlhLnBuZw align="left")](https://community.ops.io/images/PYsHi9OD0HwyJr8puNBOaqmehWcYXGx1JFOvFiOC_bg/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzLzI0NXJ2/Zm9leXJoMGRrbTdt/cHlhLnBuZw)

**ขั้นตอนที่ 2:**เมื่อคุณลงชื่อเข้าใช้แล้ว ให้คลิกที่`Go to console`ปุ่ม นี่ควรเปิดคอนโซลคลาวด์สำหรับบัญชีของคุณในแท็บใหม่

[![คลาวด์คอนโซล](https://community.ops.io/images/Xpbm4SnrHEztgDFW0IcKMsdRFuyFNFVBhQowNcOTcVs/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2Vja3oy/bzhlaDhlb213eGE1/a2R6LnBuZw align="left")](https://community.ops.io/images/Xpbm4SnrHEztgDFW0IcKMsdRFuyFNFVBhQowNcOTcVs/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2Vja3oy/bzhlaDhlb213eGE1/a2R6LnBuZw)

**ขั้นตอนที่ 3:**บนหน้าจอคอนโซลคลาวด์ เพียงกด`Create a VM`ปุ่ม หากนี่เป็นครั้งแรกที่คุณใช้แพลตฟอร์ม ระบบจะขอให้คุณเปิดใช้งานแพลตฟอร์ม`Compute Engine API`แรก จากนั้นจึงนำคุณไปที่`Create an instance`หน้าดังกล่าว

[![API ของเครื่องยนต์คำนวณ](https://community.ops.io/images/s8SgS6sqwZ2L5uLW38zYLbOcW1mixY1hbXHEnr1PF0U/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3lxNHl4/Z2s4eXRubHAwOTl2/czRiLnBuZw align="left")](https://community.ops.io/images/s8SgS6sqwZ2L5uLW38zYLbOcW1mixY1hbXHEnr1PF0U/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3lxNHl4/Z2s4eXRubHAwOTl2/czRiLnBuZw)

**ขั้นตอนที่ 4:**เราจำเป็นต้องระบุข้อกำหนดสำหรับอินสแตนซ์การประมวลผลบน`Create an instance`หน้า คุณสามารถระบุสิ่งเหล่านี้ได้ตามความต้องการของคุณ แต่เราจะใช้ข้อกำหนดที่ระบุไว้ด้านล่างสำหรับบทช่วยสอนนี้

* **ชื่อ:**ระบุชื่อสำหรับอินสแตนซ์ของคุณ
    
* **ป้ายกำกับ:**ปล่อยให้มันเป็นเหมือนเดิม.
    
* **ภูมิภาค:**เลือกอันที่อยู่ใกล้คุณเพื่อลดเวลาในการตอบสนอง
    
* **โซน:**เลือกโซนใดก็ได้จากที่มีอยู่
    
* **กลุ่มเครื่องจักร:**วัตถุประสงค์ทั่วไป
    
* **ซีรี่ส์:** E2
    
* **ประเภทเครื่อง:** e2-medium (2 vCPU, หน่วยความจำ 4Gb)
    
* **อุปกรณ์แสดงผล:**ปล่อยไว้เหมือนเดิม
    
* **บริการ VM ที่เป็นความลับ:**ปล่อยไว้เหมือนเดิม
    
* **คอนเทนเนอร์:**ปล่อยไว้เหมือนเดิม
    
* **ดิสก์สำหรับบูต:**คลิกที่`Change`ใช้สิ่งต่อไปนี้และคลิกที่`Select`.
    
    * **ระบบปฏิบัติการ:**อูบุนตู
        
    * **เวอร์ชัน:** Ubuntu 22.04 LTS x86/64
        
    * **ประเภทดิสก์สำหรับบูต:** Balanced Persistent Disk
        
    * **ขนาด:** 50
        
* **บัญชีบริการ:**บัญชีบริการเริ่มต้นของ Compute Engine
    
* **ขอบเขตการเข้าถึง:**เลือก`Allow full access to all Cloud APIs`
    
* **ไฟร์วอลล์:**เลือก`Allow HTTP traffic`
    
* **ตัวเลือกขั้นสูง:**ปล่อยไว้เหมือนเดิม
    

ตอนนี้คุณสามารถคลิก`Create`เพื่อสร้างอินสแตนซ์การเปิดตัว VM ได้

[![สร้างแดชบอร์ดอินสแตนซ์](https://community.ops.io/images/-whojGY69BtVKoMbPjHHZRfm3SgPRnasn2jrH65O894/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3Exanh2/dmNtaG5pNXV5cmhj/dHl1LnBuZw align="left")](https://community.ops.io/images/-whojGY69BtVKoMbPjHHZRfm3SgPRnasn2jrH65O894/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3Exanh2/dmNtaG5pNXV5cmhj/dHl1LnBuZw)

**ขั้นตอนที่ 5:**เมื่อคุณกด`Create`ปุ่ม ระบบจะนำคุณไปยัง`VM Instances`แดชบอร์ดซึ่งคุณจะพบอินสแตนซ์ที่คุณเพิ่งสร้างขึ้นในรายการ รอสักครู่จนกระทั่ง`Status`เปลี่ยนเป็นเครื่องหมายถูกสีเขียวและมองเห็นที่อยู่ IP ภายในและภายนอก นี่เป็นการยืนยันว่าอินสแตนซ์พร้อมใช้งานทันที

[![หน้าอินสแตนซ์ Vm](https://community.ops.io/images/aA7BX_2al1g-IR2Mj5TslVjGD0nNLisXX_2j0AUZQGI/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL211Y3J3/MHR5aTEwNm91cjY0/YmxyLnBuZw align="left")](https://community.ops.io/images/aA7BX_2al1g-IR2Mj5TslVjGD0nNLisXX_2j0AUZQGI/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL211Y3J3/MHR5aTEwNm91cjY0/YmxyLnBuZw)

ตอนนี้คุณสามารถกด`SSH`ปุ่มเพื่อเข้าถึงอินสแตนซ์และดำเนินการตามขั้นตอนถัดไป

[![วีเอ็มเอสเอสเอช](https://community.ops.io/images/pInhqk6bp_k9ajD3Hykz0zbdvFcYOKMBseps2AfIvNQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2FybGxn/YTN1YjR6N3BzYXJv/bDhsLnBuZw align="left")](https://community.ops.io/images/pInhqk6bp_k9ajD3Hykz0zbdvFcYOKMBseps2AfIvNQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2FybGxn/YTN1YjR6N3BzYXJv/bDhsLnBuZw)

## การปรับใช้ MindsDB บนอินสแตนซ์การประมวลผล

เมื่อเราพร้อมสำหรับอินสแตนซ์ของเราแล้ว เราจะพยายามติดตั้งและเรียกใช้ MindsDB ภายในอินสแตนซ์ของเราและเข้าถึง GUI ของอินสแตนซ์ อย่าลืมทำตามคำแนะนำด้านล่างเพื่อดำเนินการต่อไป

**ขั้นตอนที่ 1:**ทันทีที่คุณ SSH เข้าสู่อินสแตนซ์ของคุณ ให้รันคำสั่ง apt-update เพื่อรีเฟรชดัชนีแพ็คเกจที่มีอยู่ในระบบ

```plaintext
sudo apt-get update
```

[![คำสั่ง apt-update](https://community.ops.io/images/7BALoqOgxVfPRl5-5TcilUpyPeyexw2mR9ptEZTVPdM/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2hncnEz/aGNhcmpiZ2lkbzM5/OHB5LnBuZw align="left")](https://community.ops.io/images/7BALoqOgxVfPRl5-5TcilUpyPeyexw2mR9ptEZTVPdM/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2hncnEz/aGNhcmpiZ2lkbzM5/OHB5LnBuZw)

**ขั้นตอนที่ 2:**ถึงเวลาตรวจสอบว่ามีการติดตั้ง Docker หรือไม่ เนื่องจากเราจะใช้สิ่งนี้เพื่อติดตั้ง MindsDB เราสามารถทำได้โดยใช้คำสั่งต่อไปนี้

```plaintext
sudo docker run hello-world
```

สิ่งนี้ควรส่งคืน`Hello from Docker`ข้อความที่ยืนยันว่ามี Docker อยู่ในเครื่อง

[![สวัสดีด็อกเกอร์](https://community.ops.io/images/3W_p8kqMWtr8uLXXWRSNx8APXjg3BvBxQ9wQsI4vCLQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2xkM3g3/bmw2N2gxZngwYnNk/c3pwLnBuZw align="left")](https://community.ops.io/images/3W_p8kqMWtr8uLXXWRSNx8APXjg3BvBxQ9wQsI4vCLQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2xkM3g3/bmw2N2gxZngwYnNk/c3pwLnBuZw)

ในกรณีที่เกิดข้อผิดพลาด คุณสามารถติดตั้ง Docker โดยใช้คำสั่งต่อไปนี้ กด`Y`เมื่อระบบขอให้ดำเนินการติดตั้งต่อ

```plaintext
sudo apt-get install docker.io
```

[![การติดตั้งนักเทียบท่า](https://community.ops.io/images/MUqmrTSNPdPu5pozEZCHamzTsrrMxf8y4mSD2c5doMc/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3p0cXdu/dDlxNTR6d29uZDZh/bGhpLnBuZw align="left")](https://community.ops.io/images/MUqmrTSNPdPu5pozEZCHamzTsrrMxf8y4mSD2c5doMc/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3p0cXdu/dDlxNTR6d29uZDZh/bGhpLnBuZw)

**ขั้นตอนที่ 3:**ตอนนี้เราจะต้องดึง MindsDB บิลด์ที่เสถียรล่าสุดมาไว้ในอินสแตนซ์ของเรา เราสามารถทำได้ด้วยคำสั่งด้านล่าง

```plaintext
sudo docker pull mindsdb/mindsdb
```

[![การดึงรูปภาพ MindsDB](https://community.ops.io/images/HvJOiGuqAnPeKeIRmGfpAnDR7HuZGluGSGb7ZNOIwoc/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2EyYWlk/NGg4NjRsbGd4aWp0/d3lnLnBuZw align="left")](https://community.ops.io/images/HvJOiGuqAnPeKeIRmGfpAnDR7HuZGluGSGb7ZNOIwoc/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2EyYWlk/NGg4NjRsbGd4aWp0/d3lnLnBuZw)

บิลด์ที่เสถียรอาจเป็นหรือไม่ใช่บิลด์ล่าสุดที่มีอยู่ หากคุณต้องการทำงานกับรุ่นล่าสุด คุณสามารถดึงเวอร์ชันเบต้าได้ตลอดเวลาโดยใช้คำสั่งด้านล่าง

```plaintext
sudo docker pull mindsdb/mindsdb_beta
```

**ขั้นตอนที่ 4:**ตอนนี้ถึงเวลาเรียกใช้ MindsDB บนอินสแตนซ์ของเราแล้วเปิดพอร์ตเฉพาะเพื่อให้เราสามารถเข้าถึง GUI และ MySQL API สำหรับธุรกรรมข้อมูลได้

```plaintext
sudo docker run -p 47334:47334 -p 47335:47335 mindsdb/mindsdb
```

[![พอร์ตนักวิ่ง MindsDb](https://community.ops.io/images/BXPCBxwoEPZh_cIZO3lBCE3evrYPEs8SX7ET5oVMdjw/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3N5MTMx/ZjRhY2hycmRyNWs0/Y25lLnBuZw align="left")](https://community.ops.io/images/BXPCBxwoEPZh_cIZO3lBCE3evrYPEs8SX7ET5oVMdjw/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3N5MTMx/ZjRhY2hycmRyNWs0/Y25lLnBuZw)

**ขั้นตอนที่ 5:**แม้ว่าเราจะเปิดเผยพอร์ตข้างต้นแล้ว แต่ Compute Engine จะบล็อกการรับส่งข้อมูลตามค่าเริ่มต้น ดังนั้นเราจึงจำเป็นต้องกำหนดกฎไฟร์วอลล์อย่างชัดเจนเพื่ออนุญาตการรับส่งข้อมูลขาเข้าผ่านพอร์ตทั้งสองนี้ กลับไปที่ แด ช`VM Instances`บอร์ดแล้วคลิก`Setup firewall rules`

[![แดชบอร์ดอินสแตนซ์ VM](https://community.ops.io/images/AEu67GUR80dw8qtqBpZi1i5bMuZQqpe4hVGH8oz77hE/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3NqemRu/MWR6MDlqc3poZDl5/cXQ3LnBuZw align="left")](https://community.ops.io/images/AEu67GUR80dw8qtqBpZi1i5bMuZQqpe4hVGH8oz77hE/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3NqemRu/MWR6MDlqc3poZDl5/cXQ3LnBuZw)

เมื่อคุณอยู่บน`Firewall`แดชบอร์ดแล้ว เพียงกดที่`Create Firewall Rule`ด้านบนเพื่อเพิ่มกฎสำหรับพอร์ตเหล่านี้

[![สร้างกฎไฟร์วอลล์](https://community.ops.io/images/xxZuliyMe2AT8orUz5OIjw0OtYRwHBxG0zt3h1Ra_aU/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2E3NTho/enVwYWNvbDB2YXdp/OWZxLnBuZw align="left")](https://community.ops.io/images/xxZuliyMe2AT8orUz5OIjw0OtYRwHBxG0zt3h1Ra_aU/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2E3NTho/enVwYWNvbDB2YXdp/OWZxLnBuZw)

ตอนนี้ใช้ค่าต่อไปนี้เพื่อตั้งค่าและสร้างกฎ

* **ชื่อ:**ระบุชื่อตามที่คุณต้องการ
    
* **คำอธิบาย:**ระบุคำอธิบายหากคุณต้องการ
    
* **บันทึก**`Off` : เลือก
    
* `Default`เครือ ข่าย**:**เลือก
    
* **ลำดับความสำคัญ:** 1,000
    
* **ทิศทางการจราจร:**ทางเข้า
    
* **การดำเนินการกับการแข่งขัน:**อนุญาต
    
* **เป้าหมาย**`Specified Target Tags` : เลือก
    
* **แท็กเป้าหมาย:**ประเภท`http-server`.
    
* `IPv4 ranges`ตัวกรองแหล่งที่ มา**:**เลือก
    
* **ช่วง IPv4 ต้นทาง:** 0.0.0.0/0
    
* **ตัวกรองแหล่งที่สอง:**ไม่มี
    
* **โปรโตคอลและพอร์ต:**เลือก`Specified protocols and ports`
    
    * ตรวจสอบ`TCP`.
        
    * **พอร์ต:** 47334,47335
        

ตอนนี้เราสามารถคลิก`Create`เพื่อใช้กฎไฟร์วอลล์นี้กับอินสแตนซ์ของเราได้แล้ว

[![กฎไฟร์วอลล์](https://community.ops.io/images/401d2wN_fPVmqlwuT7NFE0HUJ3j9SZtuK6zvXbhrUpQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzLzdmaDk0/eGZ0Y3VpMm9kZHU0/bjJwLnBuZw align="left")](https://community.ops.io/images/401d2wN_fPVmqlwuT7NFE0HUJ3j9SZtuK6zvXbhrUpQ/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzLzdmaDk0/eGZ0Y3VpMm9kZHU0/bjJwLnBuZw)

**ขั้นตอนที่ 6:**ถึงเวลาลองเข้าถึง MindsDB GUI แล้ว เราสามารถทำได้โดยกดที่ IP ภายนอกของอินสแตนซ์บนพอร์ต 47334 ซึ่งจะเปิด MindsDB GUI ให้เรา

[![GUI ของ MindDB](https://community.ops.io/images/uYTIqb0w4vz1PAOjAb6Iz-cTit2MwX6CEYM1dyjk05I/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2RrNnhq/b2Q3MmRwdDM4eG9z/N282LnBuZw align="left")](https://community.ops.io/images/uYTIqb0w4vz1PAOjAb6Iz-cTit2MwX6CEYM1dyjk05I/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL2RrNnhq/b2Q3MmRwdDM4eG9z/N282LnBuZw)

ดังที่เราเห็น MindsDB GUI มีโปรแกรมแก้ไข SQL ที่ด้านบน โปรแกรมดูผลลัพธ์ที่ด้านล่าง และแหล่งข้อมูลฮับการเรียนรู้มากมายทางด้านขวาของหน้าจอ

> หมายเหตุ: เราไม่จำเป็นต้องใช้`sudo`ก่อนแต่ละคำสั่งหากเราเข้าสู่ระบบอินสแตนซ์ในฐานะ`root`ผู้ใช้

## การสำรวจตารางใน MindsDB

เนื่องจากเราได้ปรับใช้อินสแตนซ์ MindsDB บนกลไกการประมวลผลเรียบร้อยแล้ว ตอนนี้ให้เราลองสำรวจตารางที่แสดงเป็นค่าเริ่มต้นเมื่อเราติดตั้ง MindsDB

เราสามารถรันคำสั่งนี้ใน GUI SQL Editor เพื่อแสดงรายการตารางที่มีอยู่

```plaintext
Show tables;
```

[![รายชื่อตาราง](https://community.ops.io/images/TfGG9d3GQ4ckxNAvpjM6nzDzNyLpp_qzLtVDbMP_7AY/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3lnN3A4/bHNsdXVxdTJoZ3ox/ZXAyLnBuZw align="left")](https://community.ops.io/images/TfGG9d3GQ4ckxNAvpjM6nzDzNyLpp_qzLtVDbMP_7AY/w:880/mb:500000/ar:1/aHR0cHM6Ly9jb21t/dW5pdHkub3BzLmlv/L3JlbW90ZWltYWdl/cy91cGxvYWRzL2Fy/dGljbGVzL3lnN3A4/bHNsdXVxdTJoZ3ox/ZXAyLnBuZw)

เราจะเห็นได้ว่ามีสองตารางคือ`Predictors`และ`Databases`.

ตาราง`Predictors`จะจัดเก็บแบบจำลองตัวทำนายที่เราฝึกเป็นบันทึกแต่ละรายการ แต่ละคอลัมน์มีรายละเอียดเฉพาะเกี่ยวกับแบบจำลองตัวทำนายที่เกี่ยวข้อง

ตาราง`Databases`ประกอบด้วยรายการฐานข้อมูลที่เชื่อมต่อกับอินสแตนซ์ MindsDB

## บทสรุป

ตอนนี้เรามาถึงจุดสิ้นสุดของบทช่วยสอนนี้แล้ว ถึงเวลาที่จะนึกถึงสิ่งที่เราเพิ่งทำข้างต้นตามลำดับ ในตอนแรกเราสร้างอินสแตนซ์กลไกการคำนวณ ใช้งาน MindsDB บนอินสแตนซ์ สร้างกฎไฟร์วอลล์เพื่ออนุญาตการรับส่งข้อมูลขาเข้าสำหรับ MindsDB และสุดท้ายก็สำรวจ MindsDB Web UI และตารางที่แสดงเป็นค่าเริ่มต้น

ตอนนี้ถึงเวลาที่คุณจะลองใช้อินสแตนซ์ MindsDB ของคุณเองบน Compute Engine และสร้างโมเดล Predictor ที่น่าสนใจเพื่อลองทดสอบความแข็งแกร่งของ MindsDB MindsDB ยังมีเวอร์ชันคลาวด์ของตัวเองซึ่งคุณสามารถใช้ได้ที่[นี่](https://cloud.mindsdb.com/)

สุดท้ายนี้ ก่อนที่คุณจะออกเดินทาง โปรดกดไลค์ หากคุณพบว่าบทช่วยสอนนี้มีประโยชน์ และอย่าลืมแสดงความคิดเห็นของคุณด้วย

> หมายเหตุ: รูปภาพแดชบอร์ดทั้งหมดเป็นคุณสมบัติแต่เพียงผู้เดียวของ Google Cloud Platform และ MindsDB ตามลำดับ และใช้เพื่อจุดประสงค์ในการอธิบายเท่านั้น
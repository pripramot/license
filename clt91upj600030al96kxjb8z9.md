---
title: "แบบฟอร์ม Html"
seoTitle: "Pripramot | ai-jiraphinya"
seoDescription: "Pripramot | ai-jiraphinya"
datePublished: Fri Mar 01 2024 19:30:41 GMT+0000 (Coordinated Universal Time)
cuid: clt91upj600030al96kxjb8z9
slug: html
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709321150182/2edb55f9-54b0-42b7-88d5-948396a6bc17.png

---

## สิ่งแรกที่เราต้องเพิ่มคือตัวบาร์เอง สิ่งนี้ใช้องค์ประกอบ HTML บางอย่าง:

* `<form>`\- องค์ประกอบนี้มีไว้สำหรับการป้อนข้อมูลของผู้ใช้
    
* `<input>`\- องค์ประกอบนี้มีหลายประเภท โดยที่เราจะใช้ในปัจจุบันคือการค้นหา
    
* `<button>`\- องค์ประกอบนี้จะส่งแบบฟอร์มและเริ่มการค้นหา
    

HTML จะมีลักษณะดังนี้:

```html
<form id="form"> 
  <input type="search" id="query" name="q" placeholder="Search...">
  <button>Search</button>
</form>
```

HTML ข้างต้นคือทั้งหมดที่เราต้องการเพื่อสร้างแถบค้นหา มีแอตทริบิวต์บางอย่างที่เราใช้กับ`<input>`แท็ก มาดูรายละเอียดเพิ่มเติมเหล่านี้:

* type - เป็นการตั้งค่าลักษณะอินพุตที่ปรากฏบนหน้าจอ มีหลายประเภทเช่นรหัสผ่าน ช่องทำเครื่องหมาย และวิทยุ แต่ที่นี่เราใช้การค้นหา
    
* id - การตั้งค่า ID ช่วยให้ง่ายต่อการอ้างอิงกล่องอินพุตจาก JavaScript ซึ่งเราจะใช้ในภายหลัง
    
* ชื่อ - เป็นเรื่องปกติที่จะใช้ "q" สำหรับชื่อช่องคำค้นหา
    
* placeholder - นี่คือข้อความบางส่วนที่ให้คำแนะนำแก่ผู้ใช้ว่าอินพุตมีไว้เพื่ออะไร
    

เมื่อ HTML ปรากฏบนเบราว์เซอร์จะมีลักษณะดังนี้:

![แถบค้นหาใน html](https://pagedart.com/images/how-to-add-a-search-bar-in-html/search.webp align="left")

สำหรับการป้อนข้อมูล เราใช้การค้นหาประเภท แต่ก็มีประเภทข้อความด้วย อาจสร้างความสับสนเล็กน้อยว่าคุณควรเลือกอันไหน ประเภทอินพุตทั้งสองประเภทเกือบจะเหมือนกัน ยกเว้นประเภทการค้นหามีฟังก์ชันพิเศษบางอย่าง ตัวอย่างเช่น เบราว์เซอร์บางตัวจะเพิ่มปุ่มลบให้กับแท็กอินพุตให้กับคุณ:

![แถบค้นหาพร้อมการลบ](https://pagedart.com/images/how-to-add-a-search-bar-in-html/delete.webp align="left")

สำหรับช่องค้นหา ควรใช้ประเภทการป้อนข้อมูลการค้นหาและนั่นคือสิ่งที่เราจะใช้ที่นี่

แบบฟอร์มของเรายังไม่เสร็จสมบูรณ์ เราต้องตรวจสอบให้แน่ใจว่าโปรแกรมอ่านหน้าจอสามารถใช้เพื่อการเข้าถึงได้

ในการทำเช่นนี้ เราต้องทำการเปลี่ยนแปลงสองอย่างในแบบฟอร์ม:

1. เราจำเป็นต้องเพิ่ม a `role`ให้กับแบบฟอร์มด้วยค่า "search" การตั้งค่านี้จะทำให้โปรแกรมอ่านหน้าจอประกาศว่าแบบฟอร์มนี้เป็นแบบฟอร์มการค้นหา
    
2. เราเพิ่ม`aria-label`แอตทริบิวต์ให้กับ`<input>`องค์ประกอบ โปรแกรมอ่านหน้าจอจะอ่านออกเสียงค่าของแอตทริบิวต์นี้ ตั้งค่าที่อธิบายว่าข้อความใดที่แบบฟอร์มการค้นหาส่งคืน เช่น “ค้นหาผ่านเนื้อหาเว็บไซต์ของเรา”
    

นี่คือ HTML สุดท้ายของเรา:

```html
<form id="form" role="search">
  <input type="search" id="query" name="q"
   placeholder="Search..."
   aria-label="Search through site content">
  <button>Search</button>
</form>
```

ต่อไป เราจะมาดูการสร้างแบบฟอร์มให้สวยด้วยการกำหนดสไตล์ให้กับแบบฟอร์มด้วย CSS

## **ซีเอสเอส**

CSS เพิ่มสไตล์ให้กับแถบค้นหาโดยเปลี่ยนรูปลักษณ์

นอกจากนี้สิ่งหนึ่งที่สามารถช่วยให้ผู้ใช้ค้นหาช่องค้นหาได้คือการเพิ่มแว่นขยายหรือไอคอนค้นหา เราจะเพิ่มหนึ่งในปุ่มเหล่านี้และสร้างช่องค้นหาที่มีลักษณะดังนี้:

![วิธีเพิ่มแถบค้นหาใน HTML](https://pagedart.com/images/how-to-add-a-search-bar-in-html/how-to-add-a-search-bar-in-html.webp align="left")

น่าทึ่งมากว่าการใช้สีและไอคอนเพียงเล็กน้อยก็สามารถทำได้! ดูดีขึ้นมากใช่ไหม?

มาดูกันว่าเราได้เปลี่ยนอะไรให้เป็นแบบนี้บ้าง

ขั้นแรก เราได้เพิ่มสีให้กับแบบฟอร์ม:

```css
form {
  background-color: #4654e1;
  width: 300px;
  height: 44px;
  border-radius: 5px;
  display: flex;
  flex-direction: row;
  align-items: center;
}
```

เราได้กำหนดความกว้างและความสูงของแบบฟอร์มแล้ว นอกจากนี้เรายังจัดเรียงรายการในแบบฟอร์มโดยใช้`flex`จอแสดงผล

ต่อไป เราเปลี่ยนรูปลักษณ์ของช่องค้นหาอินพุต:

```css
input {
  all: unset;
  font: 16px system-ui;
  color: #fff;
  height: 100%;
  width: 100%;
  padding: 6px 10px;
}
```

บรรทัดแรกด้านบนจะรีเซ็ต`all: unset;`การออกแบบ ช่องค้นหา เบราว์เซอร์จำนวนมากมีการออกแบบของตัวเอง และอาจเป็นเรื่องยากที่จะจัดสไตล์ ซึ่งจะทำให้จัดสไตล์ได้ง่ายขึ้นตามที่เราต้องการ

จากนั้นเราตั้งค่าแบบอักษรและตรวจสอบให้แน่ใจว่าแถบค้นหาเติมช่องว่างด้วยความสูงและความกว้าง สุดท้ายเราได้เพิ่มช่องว่างภายในเล็กน้อย

กฎ CSS ถัดไปค่อนข้างแปลก! ช่วยให้เราสามารถกำหนดรูปแบบของข้อความตัวยึดตำแหน่งภายในช่องค้นหาได้ ค่าเริ่มต้นคือข้อความสีเทา หากต้องการเปลี่ยน เราจำเป็นต้องใช้กฎนี้:

```css
::placeholder {
  color: #fff;
  opacity: 0.7; 
}
```

กฎ CSS สุดท้ายจะเปลี่ยนรูปลักษณ์ของปุ่ม คุณจะเห็นได้ว่าเราได้เปลี่ยนปุ่มค้นหาเป็นไอคอนค้นหาแล้ว

เมื่อต้องการทำสิ่งนี้ ฉันได้เปลี่ยน HTML ของปุ่มให้รวมนามสกุล`svg`. คือ`svg`รูปภาพของไอคอนค้นหา ซึ่งขณะนี้มีลักษณะดังนี้:

```html
<form role="search" id="form">
  <input type="search" id="query" name="q"
   placeholder="Search..."
   aria-label="Search through site content">
  <button>
    <svg viewBox="0 0 1024 1024"><path class="path1" d="M848.471 928l-263.059-263.059c-48.941 36.706-110.118 55.059-177.412 55.059-171.294 0-312-140.706-312-312s140.706-312 312-312c171.294 0 312 140.706 312 312 0 67.294-24.471 128.471-55.059 177.412l263.059 263.059-79.529 79.529zM189.623 408.078c0 121.364 97.091 218.455 218.455 218.455s218.455-97.091 218.455-218.455c0-121.364-103.159-218.455-218.455-218.455-121.364 0-218.455 97.091-218.455 218.455z"></path></svg>
  </button>
</form>
```

จากนั้นเราสามารถจัดสไตล์องค์ประกอบ html ทั้งสองนี้ได้ดังนี้:

```css
button {
  all: unset;
  cursor: pointer;
  width: 44px;
  height: 44px;
}

svg {
  color: #fff;
  fill: currentColor;
  width: 24px;
  height: 24px;
  padding: 10px;
}
```

เราได้ใช้`all: unset;`กฎอีกครั้งเพื่อรีเซ็ตปุ่มเป็นค่าเริ่มต้น แล้วกำหนดความสูงและความกว้างของ`44px`รุ่นนี้ให้เหมาะกับนิ้วบนหน้าจอสัมผัส

จากนั้นเราตั้งค่าความสูงและความกว้างของไอคอนและตั้งค่าสีเป็นสีขาว ("#fff")

ตอนนี้แถบค้นหาของเราเกือบจะพร้อมแล้ว! ยกเว้นไม่มีอะไรเกิดขึ้นเมื่อเรากดปุ่มค้นหา

ขั้นตอนสุดท้ายสำหรับเราคือการเชื่อมต่อปุ่มกับ JavaScript

## **จาวาสคริปต์**

เราจะทำการค้นหาโดย Google เมื่อมีคนค้นหาในแถบค้นหาของเรา

ในการทำเช่นนี้เราจำเป็นต้องเขียนโค้ดที่จะ:

* เพิ่มผู้ฟังเหตุการณ์ลงในแบบฟอร์ม เพื่อให้เราทราบเมื่อมีคนกดปุ่มค้นหา
    
* รับค่าข้อความจากกล่องแบบสอบถาม
    
* สร้าง URL ของ Google ที่ค้นหาไซต์เฉพาะ
    
* เปิดแท็บใหม่ด้วย Google และคำค้นหา
    

Google อนุญาตให้คุณค้นหาไซต์ใดไซต์หนึ่งหากคุณเพิ่มลง`site:`ในข้อความค้นหา ตัวอย่างเช่น หากคุณต้องการค้นหา PageDart ด้วยคำว่า Lazy Loading คุณสามารถเพิ่มสิ่งนี้ใน Google:

`site:`[https://mint-butterfly.vercel.app](https://mint-butterfly.vercel.app/)

สิ่งที่ยอดเยี่ยมเกี่ยวกับคำค้นหานี้คือมันจะส่งคืนผลลัพธ์สำหรับไซต์ที่คุณระบุเท่านั้น คุณกรองผลลัพธ์ของ Google และไม่มีไซต์อื่นใดที่จะปรากฏในผลลัพธ์ เราสามารถใช้เคล็ดลับนี้เพื่อสร้างหน้าผลการค้นหาจากแถบค้นหาของเรา

นี่คือรหัสที่สามารถทำได้:

```javascript
const f = document.getElementById('form');
const q = document.getElementById('query');
const google = 'https://www.google.com/search?q=site%3A+';
const site = 'https://mint-butterfly.vercel.app';
function submitted(event) {
  event.preventDefault();
  const url = google + site + '+' + q.value;
  const win = window.open(url, '_blank');
  win.focus();
}

f.addEventListener('submit', submitted);
```

สิ่งแรกที่เราทำคือแนบตัวแปรบางตัวเข้ากับแบบฟอร์มและช่องป้อนข้อมูลการค้นหา จากนั้นเราตั้งค่า Google URL และตั้งค่าตัวแปรไซต์:

```javascript
const f = document.getElementById('form');
const q = document.getElementById('query');
const google = 'https://www.google.com/search?q=site%3A+';
const site = 'https://mint-butterfly.vercel.app';
```

หากคุณต้องการค้นหาเว็บไซต์ของคุณให้เปลี่ยนไป`const site = '`mint-butterfly.vercel.app`';`ยังเว็บไซต์ของคุณ`const site = 'example.com';`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709320410101/c5b7e790-e370-411b-ae08-20a8cac9b254.png align="center")

จากนั้นเรา[จะสร้างฟังก์ชั่น](https://pagedart.com/blog/how-to-call-a-function-in-javascript/)ที่จะทำงานทุกครั้งที่มีคนกดปุ่มค้นหา ฟังก์ชั่นจะเปิด Google ในแท็บใหม่ในเบราว์เซอร์:

```javascript
function submitted(event) {
  event.preventDefault();
  const url = google + site + '+' + q.value;
  const win = window.open(url, '_blank');
  win.focus();
}
```

บรรทัดสุดท้ายในโค้ด:

```javascript
f.addEventListener('submit', submitted);
```

เพิ่มผู้ฟังในแบบฟอร์ม มันจะฟังการกดปุ่มส่งและเรียกใช้ฟังก์ชั่นแต่ละครั้ง

ตอนนี้เมื่อคุณป้อนคำค้นหาและกดไอคอนค้นหา แท็บใหม่จะเปิดขึ้นพร้อมกับไซต์ของคุณและคำค้นหา

## **โซลูชั่นที่สมบูรณ์**

ตอนนี้เราได้ครอบคลุมทุกส่วนของแถบค้นหาแล้ว:

* HTML ของแบบฟอร์ม
    
* CSS เพื่อเพิ่มสีสันและการออกแบบ
    
* JavaScript เพื่อประมวลผลอินพุตแบบฟอร์ม
    

นี่คือ HTML ที่สมบูรณ์:

```html
<!DOCTYPE html>
<html lang='en' class=''>
  <head>
    <meta charset='UTF-8'>
    <title>Search Bar Demo</title>
    <style>
        body {
        background-color: #3745c2;
        margin: 200px 40%;
      }

      form {
        background-color: #4654e1;
        width: 300px;
        height: 44px;
        border-radius: 5px;
        display:flex;
        flex-direction:row;
        align-items:center;
      }

      input {
        all: unset;
        font: 16px system-ui;
        color: #fff;
        height: 100%;
        width: 100%;
        padding: 6px 10px;
      }

      ::placeholder {
        color: #fff;
        opacity: 0.7; 
      }

      svg {
        color: #fff;
        fill: currentColor;
        width: 24px;
        height: 24px;
        padding: 10px;
      }

      button {
        all: unset;
        cursor: pointer;
        width: 44px;
        height: 44px;
      }
    </style>
  </head>
  <body>
    <form role="search" id="form">
      <input type="search" id="query" name="q" placeholder="Search..." aria-label="Search through site content">
      <button>
        <svg viewBox="0 0 1024 1024"><path class="path1" d="M848.471 928l-263.059-263.059c-48.941 36.706-110.118 55.059-177.412 55.059-171.294 0-312-140.706-312-312s140.706-312 312-312c171.294 0 312 140.706 312 312 0 67.294-24.471 128.471-55.059 177.412l263.059 263.059-79.529 79.529zM189.623 408.078c0 121.364 97.091 218.455 218.455 218.455s218.455-97.091 218.455-218.455c0-121.364-103.159-218.455-218.455-218.455-121.364 0-218.455 97.091-218.455 218.455z"></path></svg>
      </button>
    </form>
    <script>
      const f = document.getElementById('form');
      const q = document.getElementById('query');
      const google = 'https://www.google.com/search?q=site%3A+';
      const site = 'https://mint-butterfly.vercel.app';

      function submitted(event) {
        event.preventDefault();
        const url = google + site + '+' + q.value;
        const win = window.open(url, '_blank');
        win.focus();
      }

      f.addEventListener('submit', submitted);
    </script>
  </body>
</html>
```

## **วิธีเพิ่มแถบค้นหา**

คุณได้เรียนรู้ในบทช่วยสอนนี้ถึงวิธีเพิ่มแถบค้นหาใน HTML ได้ครอบคลุม:

* วิธีสร้างฟอร์ม HTML ขนาดเล็ก
    
* วิธีการออกแบบแบบฟอร์มโดยใช้ CSS
    
* วิธีเขียน JavaScript เพื่อโต้ตอบกับแบบฟอร์ม
    

คุณยังได้เรียนรู้วิธีการใช้ JavaScript เพื่อเชื่อมต่อแบบฟอร์มกับ Google อีกด้วย ทำการค้นหาเฉพาะบนเว็บไซต์ของคุณเท่านั้น

การใช้การค้นหาไซต์แบบพิเศษบน Google จะทำให้คุณได้รับผลลัพธ์ของ Google สำหรับไซต์ของคุณเท่านั้น

---

CDN: ส่วนตัวฉัน.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709320098585/ad7c1903-a3fb-4d9b-8408-dcba8d278bbf.png align="center")

%[https://youtu.be/ZL36vDp6esc?si=Yh3eLeaZxBGhw1nS] 

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709491299443/0a566963-b4dc-42c4-ae4a-1b0bd0317275.png align="center")

%[https://youtu.be/w8tKWR45OUo?si=tsMGcYDVyomFB7dO] 

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710001539644/bcd4a554-f71f-4829-8298-ab484104a845.png align="center")
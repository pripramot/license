---
title: "Spotify with Python"
datePublished: Sun Mar 17 2024 07:27:28 GMT+0000 (Coordinated Universal Time)
cuid: cltv729nw000108id8afhd2n2
slug: spotify-with-python
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/I3ZzOkiAbTI/upload/aa7431b42e500e17ba90a5dbccd11191.jpeg

---

# ลำเต้ยของงูเหลือม.By Mint

Spotify เป็นหนึ่งในผู้ให้บริการสตรีมเพลงที่ใหญ่ที่สุดในโลก เเต่ฉันเป็นเพียงสาวน้อยตัวเล็กเเสนบอบบาง อุ๊ย(เสียงพี่หนุ่มกรรชัย) วันนี้ฉันจะทำบางอย่างเกี่ยวกับ Spotify โดยใช้ Spotipy Web API ให้สามารถเข้าถึงข้อมูลเพลงทั้งหมดที่ได้รับจากแพลตฟอร์ม Spotify ได้อย่างเต็มที่ นอกจากนี้ยังสามารถดึงเนื้อหา Spotify เช่น ข้อมูลอัลบั้ม เพลย์ลิสต์ และแม้แต่เพลงโดยใช้ API

## REST API คืออะไร

REST ย่อมาจาก Representational State Transfer และปฏิบัติตามข้อจํากัดของสถาปัตยกรรม REST ที่อนุญาตให้โต้ตอบกับบริการเว็บ RESTful กําหนดชุดของฟังก์ชัน (GET, PUT, POST, DELETE) ที่ไคลเอนต์ใช้เพื่อเข้าถึงข้อมูลเซิร์ฟเวอร์ ฟังก์ชั่นที่ใช้คือ:

* GET (ดึงเรกคอร์ด)
    
* PUT (อัปเดตระเบียน)
    
* POST (สร้างเรกคอร์ด)
    
* DELETE (ลบระเบียน)
    

คุณสมบัติหลักของมันคือ REST API เป็นแบบไร้สถานะ กล่าวคือ เซิร์ฟเวอร์จะไม่บันทึกข้อมูลของลูกค้าระหว่างคําขอ

## Web API คืออะไร

Web API เป็นเพียง API สําหรับเว็บ เป็น API ที่สามารถเข้าถึงได้โดยใช้โปรโตคอล HTTP สามารถสร้างได้โดยใช้ Java, .nET เป็นต้น มีการใช้งานเพื่อขยายฟังก์ชันการทํางานของเบราว์เซอร์ลดความซับซ้อนของฟังก์ชันที่ซับซ้อนและให้ไวยากรณ์ที่ง่ายสําหรับโค้ดที่ซับซ้อน

API เว็บสี่ประเภทหลักคือ:

* เปิด API
    
* API พาร์ทเนอร์
    
* API ภายใน
    
* API คอมโพสิต
    

ฉันรู้เเค่นี้ละ เข้าเรื่องกันดีกว่า

## **แพ็คเกจที่จําเป็น**

```basic
pip install spotipy
```

## การตั้งค่าแอพ Spotify

**ขั้นตอนที่ 1:** สร้างบัญชีหรือเข้าสู่ระบบบัญชี Spotify Developers

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710276446353/2f7a14c9-6072-485d-8541-6f54eedc197f.png align="center")

**ขั้นตอนที่ 2:** สร้างแอป

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710276493068/a2ec4354-d9c8-4ad8-b8d4-ec16607dd902.png align="center")

**ขั้นตอนที่ 3:** แดชบอร์ดจะเปิดขึ้น ตอนนี้บันทึก **รหัสลูกค้า-ความลับของลูกค้า** ซึ่งจะใช้ในภายหลังในโปรแกรม

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710277095186/b366313e-8228-447e-878f-d420cac24362.png align="center")

**ขั้นตอนที่ 4:** คลิกที่ปุ่ม "**แก้ไขการตั้งค่า**" และเพิ่ม URI เปลี่ยนเส้นทางดังต่อไปนี้

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710277240735/f5065b64-ed77-4ac5-90cf-6da86a6c5c3d.png align="center")

```basic
http://google.com/callback/
```

**ขั้นตอนที่ 5:** คลิกที่เพิ่มและบันทึกการเปลี่ยนแปลง

## ขั้นตอน Dev.

**ขั้นตอนที่ 1:** ทําตามขั้นตอนด้านล่างเพื่อตั้งค่าสภาพแวดล้อมเสมือน

* สร้างโฟลเดอร์สําหรับโครงการนี้
    
* ไปที่พรอมต์คําสั่งและกําหนดเส้นทางไปยังโฟลเดอร์ที่สร้างขึ้น
    
* คําสั่งด้านล่างใช้เพื่อตั้งค่าสภาพแวดล้อมเสมือนเพื่อให้โครงการของเราทํางาน
    

```basic
python -m venv .env
```

* คําสั่งด้านล่างคือการเปิดใช้งานสภาพแวดล้อมเสมือน
    

```basic
.env\Scripts\activate
```

**ขั้นตอนที่ 2:**

ในขั้นตอนนี้เราจะนําเข้า Spotify เว็บเบราว์เซอร์ถูกนําเข้าดังนั้นหลังจากการตรวจสอบสิทธิ์เราจะถูกเปลี่ยนเส้นทางไปยัง URL ที่ระบุผ่านเบราว์เซอร์ เรานําเข้า JSON เพื่อยอมรับการตอบกลับจากเบราว์เซอร์ซึ่งอยู่ในรูปแบบโค้ด JSON

```python
import json 
import spotipy 
import webbrowser
```

**ขั้นตอนที่ 3:**

ในขั้นตอนนี้ เราจะเพิ่มข้อมูลประจําตัวที่จําเป็นที่นี่แทนข้อมูลประจําตัว Your\_Client\_Id และ Your\_Client\_Secret ที่คุณจดบันทึกไว้ในขั้นตอนที่ 3 [**คลิกที่นี่** เพื่อทรา](https://www.spotify.com/us/account/overview/)บชื่อ[ผู้ใช้ของค](https://www.spotify.com/us/account/overview/)ุณและแทนที่ Your\_Username

```python
username = 'Your user name'
clientID = 'your client ID'
clientSecret = 'Your client secret'
redirect_uri = 'http://google.com/callback/'
```

**ขั้นตอนที่ 4:**

บรรทัดต่อไปนี้ใช้เพื่อตรวจสอบข้อมูลของเราและให้การเข้าถึงบัญชี Spotify ของเรา

* **oauth\_object** เป็นวัตถุที่เราสร้างขึ้นเพื่อเข้าถึงฟังก์ชัน SpotifyOAuth จากไลบรารีที่ติดตั้งของเรา ที่นี่เราส่ง clientID, clientSecret และเปลี่ยนเส้นทาง URI ฟังก์ชันนี้จะตรวจสอบว่า clientID, clientSecret และ URI เปลี่ยนเส้นทางถูกต้องหรือไม่
    
* **token\_dict** ที่ได้รับโทเค็นเป็นหลักฐานการเข้าถึง Spotify ที่ได้รับอนุญาตของเรา
    
* **สปอยปี้ Spotify(auth=token)** นี่คือขั้นตอนจริงที่โทเค็นที่สร้างขึ้นในขั้นตอนก่อนหน้าได้รับอนุญาต
    
* **ผู้ใช้ = spotifyObject.current\_user()** บรรทัดนี้ได้รับรายละเอียดทั้งหมดของผู้ใช้และรวมเข้าด้วยกัน
    
* ข้อมูลผู้ใช้นี้ใช้เพื่อดึงการตอบกลับ JSON ที่ส่งโดยเบราว์เซอร์ไปยังระบบของเรา คําสั่งการพิมพ์ที่นี่ใช้เพื่อพิมพ์การตอบกลับ JSON นี้
    
* ```python
      oauth_object = spotipy.SpotifyOAuth(clientID, clientSecret, redirect_uri) 
      token_dict = oauth_object.get_access_token() 
      token = token_dict['access_token'] 
      spotifyObject = spotipy.Spotify(auth=token) 
      user_name = spotifyObject.current_user() 
      
      # To print the response in readable format. 
      print(json.dumps(user_name, sort_keys=True, indent=4))
    ```
    

**ขั้นตอนที่ 5:**

ในขั้นตอนนี้ เราจะสร้างลูปฟังก์ชันการทํางานของผู้ใช้

* เมื่อให้ **1** เป็นอินพุต ชื่อเพลงที่จะค้นหาจะถูกพิมพ์ และเล่นเพลงที่ต้องการ
    
* เมื่อกําหนด **0** เป็นอินพุต จะออกจากโปรแกรม
    
    ```python
    while True: 
    	print("Welcome to the project, " + user_name['display_name']) 
    	print("0 - Exit the console") 
    	print("1 - Search for a Song") 
    	user_input = int(input("Enter Your Choice: ")) 
    	if user_input == 1: 
    		search_song = input("Enter the song name: ") 
    		results = spotifyObject.search(search_song, 1, 0, "track") 
    		songs_dict = results['tracks'] 
    		song_items = songs_dict['items'] 
    		song = song_items[0]['external_urls']['spotify'] 
    		webbrowser.open(song) 
    		print('Song has opened in your browser.') 
    	elif user_input == 0: 
    		print("Good Bye, Have a great day!") 
    		break
    	else: 
    		print("Please enter valid user-input.")
    ```
    

**ขั้นตอนที่ 6:**

สร้างไฟล์ python และเพิ่มโค้ดด้านล่างในไฟล์ ([spotify.py](http://spotify.py))

**โน้ต:** ตรวจสอบให้แน่ใจว่าตําแหน่งของไฟล์ python และตําแหน่งสภาพแวดล้อมเสมือนเหมือนกัน

```python
import json 
import spotipy 
import webbrowser 

username = 'Your user name'
clientID = 'your client ID'
clientSecret = 'Your client secret'
redirect_uri = 'http://google.com/callback/'
oauth_object = spotipy.SpotifyOAuth(clientID, clientSecret, redirect_uri) 
token_dict = oauth_object.get_access_token() 
token = token_dict['access_token'] 
spotifyObject = spotipy.Spotify(auth=token) 
user_name = spotifyObject.current_user() 

# To print the JSON response from 
# browser in a readable format. 
# optional can be removed 
print(json.dumps(user_name, sort_keys=True, indent=4)) 

while True: 
	print("Welcome to the project, " + user_name['display_name']) 
	print("0 - Exit the console") 
	print("1 - Search for a Song") 
	user_input = int(input("Enter Your Choice: ")) 
	if user_input == 1: 
		search_song = input("Enter the song name: ") 
		results = spotifyObject.search(search_song, 1, 0, "track") 
		songs_dict = results['tracks'] 
		song_items = songs_dict['items'] 
		song = song_items[0]['external_urls']['spotify'] 
		webbrowser.open(song) 
		print('Song has opened in your browser.') 
	elif user_input == 0: 
		print("Good Bye, Have a great day!") 
		break
	else: 
		print("Please enter valid user-input.")
```

**ขั้นตอนที่ 7:**

รันโปรแกรมของคุณในพรอมต์คําสั่งโดยใช้คําสั่งต่อไปนี้

```bash
python spotify.py
```

## การดําเนินการของโปรแกรม

**ขั้นตอนที่ 1:** หลังจากการดําเนินการครั้งแรกของโปรแกรมคุณจะถูกนําไปยังหน้าต่อไปนี้ ยอมรับเงื่อนไขเพื่อดําเนินการต่อไป

![](https://media.geeksforgeeks.org/wp-content/uploads/20220514201114/Screenshot419.jpg align="center")

**ขั้นตอนที่ 2:** หลังจากตกลงแล้ว มันจะถูกเปลี่ยนเส้นทางไปยังหน้า Google เพียงคัดลอก URL ของหน้าแล้ววางลงในพรอมต์คําสั่งแล้วคลิก Enter

**ขั้นตอนที่ 3:** คุณจะเห็นโค้ด JSON ดังกล่าวปรากฏบนหน้าจอพรอมต์คําสั่งของคุณ

**ขั้นตอนที่ 4:** ตอนนี้เรียกใช้ไฟล์ python ของคุณอีกครั้งในพรอมต์คําสั่งโดยใช้คําสั่ง **python**[**spotify.py**](http://spotify.py) มันจะขอข้อมูลจากผู้ใช้

* **กด 0** เพื่อออก
    

**กด 1** เพื่อป้อนชื่อเพลงที่จะเล่น

## ยังไม่จบ
# sample-1_Serial-Monitor
![1](https://user-images.githubusercontent.com/98943425/153701608-0b9d78a3-f7a9-4be8-942d-acd927f777e4.png)

#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

int cnt คือ การนับแบบจำนวนเต็ม

void setup() คือ ฟังก์ชั่นใช้ในการประกาศค่าเริ่มต้น เป็นฟังก์ชั่นที run ครั้งเดียว

Serial.begin() ใช้เพื่อตั้งค่าความเร็วในการสื่อสารเป็นบิตต่อวินาที 

void loop()  คือ ฟังก์ชั่นใช้ในการเขียนโค้ดให้โปรแกรม run วนลูปไปเรื่อย ๆ

ตัวแปร++ คือ การบวกเพิ่มทีละ 1 ดังนั้น cnt++ คือการนับเพิ่มทีละ 1

serial.printf("PATTANI" :%d\n",cnt)  คือ แสดงผลข้อมูลออกมาในที่นี้ก็จะหมายถึงเลขที่นับ

%d คือ ใช้กับตัวแปรที่เก็บค่าเป็นจำนวนเต็ม 

\n คือ ขึ้นบรรทัดใหม่

delay(1000) คือ หน่วงเวลา 1000 ms หรือ 1 s

---

# sample-2_Scan-Wifi
![2 1](https://user-images.githubusercontent.com/98943425/153701628-537e7b56-6160-430d-a5ad-ada6c7ac47aa.png)
![2 2](https://user-images.githubusercontent.com/98943425/153701620-e064909f-ac86-43e7-a468-37c55fd9c3ab.png)

#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

int cnt คือ การนับแบบจำนวนเต็ม

void setup() คือ ฟังก์ชั่นใช้ในการประกาศค่าเริ่มต้น เป็นฟังก์ชั่นที run ครั้งเดียว

Serial.begin() ใช้เพื่อตั้งค่าความเร็วในการสื่อสารเป็นบิตต่อวินาที 


WiFi.mode(WIFI_STA);  คือ  เป็นการตั้งค่า WiFi เป็นโหมดสถานี

WiFi.disconnect();    คือ  ตัดการเชื่อมต่อจากเครื่อข่ายหากเชื่อมต่อไว้ก่อนหน้านี้

delay() คือ  หน่วงเวลา (ms) 

void loop()  คือ ฟังก์ชั่นใช้ในการเขียนโค้ดให้โปรแกรม run วนลูปไปเรื่อย ๆ

serial.println()  คือ แสดงผลข้อมูลออกมาแล้วขึ้นบรรทัดใหม่

WiFi.scanNetworks() คือ สแกนเครื่อยข่าย wifi

WiFi.SSID() คือ ชื่อ wifi

WiFi.RSSI() คือ ความแรงของสัญญาณ 

---

# sample-3_Output-Port
![3](https://user-images.githubusercontent.com/98943425/153701653-a2186aa3-749e-465d-a719-7c5f1c966923.png)    

#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

int cnt คือ การนับแบบจำนวนเต็ม

void setup() คือ ฟังก์ชั่นใช้ในการประกาศค่าเริ่มต้น เป็นฟังก์ชั่นที run ครั้งเดียว

Serial.begin() ใช้เพื่อตั้งค่าความเร็วในการสื่อสารเป็นบิตต่อวินาที 

pinMode() คือคำสั่งที่มีไว้สำหรับกำหนดการทำงานของ pin

void loop()  คือ ฟังก์ชั่นใช้ในการเขียนโค้ดให้โปรแกรม run วนลูปไปเรื่อย ๆ

ตัวแปร++ คือ การบวกเพิ่มทีละ 1 ดังนั้น cnt++ คือการนับเพิ่มทีละ 1

digitalWrite() ใช้สำหรับสั่งให้ Arduino เขียนค่า HIGH หรือ LOW ที่ขา digital ของบอร์ด

delay() คือ  หน่วงเวลา (ms) 

---

# sample-4-Input-Port
![4](https://user-images.githubusercontent.com/98943425/153701659-327e0dcc-7b16-483a-a9cf-d9c70eee069b.png)
#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

int cnt คือ การนับแบบจำนวนเต็ม

void setup() คือ ฟังก์ชั่นใช้ในการประกาศค่าเริ่มต้น เป็นฟังก์ชั่นที run ครั้งเดียว

Serial.begin() ใช้เพื่อตั้งค่าความเร็วในการสื่อสารเป็นบิตต่อวินาที 

pinMode() คือคำสั่งที่มีไว้สำหรับกำหนดการทำงานของ pin

void loop()  คือ ฟังก์ชั่นใช้ในการเขียนโค้ดให้โปรแกรม run วนลูปไปเรื่อย ๆ

val คือ ตัวแปร int สำหรับเก็บค่า สัญญาณ

digitalRead() คือ เป็นคำสั่งที่ใช้อ่านค่าสถานะของขาดิจิตอล

digitalWrite() ใช้สำหรับสั่งให้ Arduino เขียนค่า HIGH หรือ LOW ที่ขา digital ของบอร์ด

delay() คือ  หน่วงเวลา (ms) 


---

# sample 5-Wifi-Web-Server
![5](https://user-images.githubusercontent.com/98943425/153701663-4975b48e-4dd8-4cf3-9fc1-ef5bf6cede60.png)
![5 2](https://user-images.githubusercontent.com/98943425/153701665-8cbfa52e-cb03-4730-89d3-808435668f4b.png)

#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

const char* ssid = "Username" คือ การประกาศสร้างตัวแปรเก็บ Username เครื่อข่าย WiFi ชื่อว่า ssid 

const char* password = "Password" คือ การประกาศสร้างตัวแปรเก็บ Password ของเครื่อข่าย WiFi ชื่อว่า password

ESP8266WebServer server(80) คือ เปิด WebServer ที่ port 80

void setup() คือ ฟังก์ชั่นใช้ในการประกาศค่าเริ่มต้น เป็นฟังก์ชั่นที run ครั้งเดียว

Serial.begin() ใช้เพื่อตั้งค่าความเร็วในการสื่อสารเป็นบิตต่อวินาที 

WiFi.mode(WIFI_STA);  คือ  เป็นการตั้งค่า WiFi เป็นโหมดสถานี

WiFi.begin(ssid, pass) คือ สำหรับเชื่อมต่อไวไฟ โดยใช้ชื่อไวไฟ และ รหัสผ่านของเครื่อยข่าย

delay() คือ  หน่วงเวลา (ms) 

---

# sample-6_Wifi-AP-Web-Server
![6](https://user-images.githubusercontent.com/98943425/153701768-6590a70e-8b12-4db6-9eda-84f709791137.png)
![6 2](https://user-images.githubusercontent.com/98943425/153701771-ee7d1346-d494-4b04-b268-123175decffe.png)

#include เป็นคำสั่งที่ใช้อ้างอิงไฟล์ภายนอก เพื่อเรียกใช้ฟังก์ชั่น หรือตัวแปรที่มีการสร้างหรือกำหนดไว้ในไฟล์นั้น รูปแบบการใช้งาน

const char* ssid = "Username" คือ การประกาศสร้างตัวแปรเก็บ Username เครื่อข่าย WiFi ชื่อว่า ssid 

const char* password = "Password" คือ การประกาศสร้างตัวแปรเก็บ Password ของเครื่อข่าย WiFi ชื่อว่า password

local_ip คือ สำหรับตั้ง IP

gateway คือ สำหรับตั้ง gateway

subnet คือ สำหรับตั้ง subnet

ESP8266WebServer server(80) คือ เปิด WebServer ที่ port 80

WiFi.softAP(ssid,passwaord) คือ ฟังก์ชันสำหรับตั้งค่า Access Point ใช้งานในโหมด AP mode 

WiFi.softAPConfig(IPAddress local_ip, IPAddress gateway, IPAddress subnet) คือ ฟังก์ชันสำหรับตั้งค่า IP , gateway , subnet ใน AP mode

delay() คือ  หน่วงเวลา (ms) 

---

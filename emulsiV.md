# เขียนโปรแกรม แสดงตัวอักษร (ตัวย่อ ชื่อ สกุล)
---
## นายธนบดี บุญช่วย 6310610032
### อธิบายคำสั่ง

 1. addi x1, x0, 32
  
        add immediate
        
        เอาเลข 32 ฐาน 10 ไปบวกกับ X0(ซึ่งมีค่าเป็น 0 เสมอไม่สามารถเปลี่ยนได้) แล้วนำผลลัพธ์ไปแทนใน x1  
        
       ![1](https://user-images.githubusercontent.com/98943425/160077986-cde10fa3-9bfc-40eb-936f-50428347028f.png)
       
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 00000000 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ 00000020 (คือเลข 32 ฐาน 10 ที่แปลงเป็นฐาน 16) + x0 แล้วเก็บใน x1
        
        สังเกตุที่ ALU จะเห็น 32 + x0 แล้วดู ที่ General-purpose regs จะเห็นว่าที่ x1 จะเท่ากับ 00000020
---

 2. lui x2, 0xc0000000
 
        load upper immediate 
        
        นำค่าที่อยู่ทางขวา 1 word ไปใส่ใน x2 แต่ใส่แค่ 20 bit แรกก็คือ(c0000000)

       ![2](https://user-images.githubusercontent.com/98943425/160079575-30997a20-b1fa-4631-8f9d-dfaf3ed094cd.png)
       
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 00000004 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ c0000000 เก็บใน x2 
        
        สังเกตุที่ General-purpose regs จะเห็นว่าที่ x2 จะเท่ากับ c0000000

---
 3. lbu x3, 0(x1)

        load byte unsigned
        
        นำข้อมูลจาก หน่วยความจำ x1 แล้วไปอ่านมาค่า 1 byte มาใส่ใน x3
        
       ![3](https://user-images.githubusercontent.com/98943425/160078952-664f81e0-704c-4a81-a1b2-7d346c33116b.png)
        
        โดยเริ่ม Bus ดึง word มาจาก address 00000008 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะนำข้อมูลจาก adress x1 มา 1 byte แล้วไปเก็บใน x3
        
        สังเกตุที่ ALU จะเห็น 00000020 
        
        สังเกตุที่ Bus จะพบว่าดึง data 1 byte (54) ที่ address 00000020 (address x1) แล้วไปเก็บที่ x3
        
        จะเห็นว่าที่ General-purpose regs จะเห็นว่าที่ x3 จะเท่ากับ 00000054
---
        
 4. beq x3, x0, +16
 
        branch on equal
        
        ถ้า x3 = x0 ให้ กระโดดไป +16 
       
       ![4](https://user-images.githubusercontent.com/98943425/160079336-838d3d74-4cf9-4e28-9d2b-6c82244b327b.png)
       
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 0000000c เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ ถ้า x3 = x0(มีค่าเป็น 0 เสมอ) จะกระโดดไป +16 ฐาน 10 (หรือ 10 ฐาน 16) address
        
        จะเห็นว่าที่ ALU จะมีการบวก 0000000c + 00000010 จะได้ 0000001c ก็คือจะกระโดดจาก addresss c ไป 1c เงื่อนไข ถ้า x3 = x0
        
        เมื่อดูที่ Comparator จะมีการเช็คเงื่อนไข x3 = x0 ได้คำตอบ false จึงไม่ไปที่ address 1c 
        
        แล้วดูที่ Program counter ที่ PC address ต่อที่จะไปคือ  00000010 
        
---

 5. sb x3, 0(x2)
        
        store byte
        
        นำข้อมูลใน x3 ไปเก็บไว้ใน address x2
       ![5](https://user-images.githubusercontent.com/98943425/160080101-424ab0d5-0599-4213-ad4b-e99b69c0769d.png)
        
        โดยเริ่ม Bus ดึง word มาจาก address 00000010 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะนำ x3 ไปเก็บใน address x2
        
        สังเกตุที่ Bus จะพบว่าดึง data 00000054 (x3) เก็บที่ address c0000000 (address x2) 
        
        และสังเกตุที่จอสีดำด้านซ้ายล่างคือ address x2 ซึ่งจะพบว่ามีตัว T แสดงขึ้นมา 
        
        เพราะว่าหากเปิด ascii table เลข 54 ฐาน 16 คือ ตัวอักษร T
---
 
6. addi x1, x1, 1

        add immediate
        
        เอา 1 บวกกับ x1 แล้วนำไปใส่ใน x1
      ![6](https://user-images.githubusercontent.com/98943425/160080965-601b2a3a-4779-4023-8ebc-77fcc8e059cb.png)

        จะเห็นว่า Bus ดึง word มาจาก address 00000014 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ 00000001 (คือเลข 1 ฐาน 10 ที่แปลงเป็นฐาน 16) + x1 แล้วเก็บใน x1
        
        สังเกตุที่ ALU จะเห็น 1 + x1(ก่อนเปลี่ยน 00000020 ) และได้ r คือ 00000021 แล้วดู ที่ General-purpose regs จะเห็นว่าที่ x1 จะเท่ากับ 00000021
---

7. jal x0, -16

        jump and link
        
        กระโดดไป -16

      ![7](https://user-images.githubusercontent.com/98943425/160081167-e84d99e3-100f-40e2-894c-93e77f503817.png)
      
        จะเห็นว่า Bus ดึง word มาจาก address 00000018 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ กระโดดจาก address 00000018 ไป -16 ฐาน 10( -10 ฐาน 16)
        
        สังเกตุที่ ALU จะเห็น r คือ 00000008 แล้วดูที่ Program counter ที่ PC address ต่อไปคือ  00000008 

---
8. lbu x3, 0(x1)

        load byte unsigned
        
        นำข้อมูลจาก หน่วยความจำ x1 แล้วไปอ่านมาค่า 1 byte มาใส่ใน x3
      ![8](https://user-images.githubusercontent.com/98943425/160081700-00d7a11e-a3fc-482d-b1e1-7b8255017a64.png)

        โดยเริ่ม Bus ดึง word มาจาก address 00000008 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะนำข้อมูลจาก adress x1 มา 1 byte แล้วไปเก็บใน x3
        
        สังเกตุที่ ALU จะเห็น 00000021 
        
        สังเกตุที่ Bus จะพบว่าดึง data 1 byte (42) ที่ address 00000021 (address x1) แล้วไปเก็บที่ x3
        
        จะเห็นว่าที่ General-purpose regs จะเห็นว่าที่ x3 จะเท่ากับ 00000042
---
9. beq x3, x0, +16
 
        branch on equal
        
        ถ้า x3 = x0 ให้ กระโดดไป +16 
      ![9](https://user-images.githubusercontent.com/98943425/160081966-5d75650d-e74f-4929-b4d0-19e1051c5bc2.png)
      
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 0000000c เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ ถ้า x3 = x0(มีค่าเป็น 0 เสมอ) จะกระโดดไป +16 ฐาน 10 (หรือ 10 ฐาน 16) address
        
        จะเห็นว่าที่ ALU จะมีการบวก 0000000c + 00000010 จะได้ 0000001c ก็คือจะกระโดดจาก addresss c ไป 1c เงื่อนไข ถ้า x3 = x0
        
        เมื่อดูที่ Comparator จะมีการเช็คเงื่อนไข x3 = x0 ได้คำตอบ false จึงไม่ไปที่ address 1c 
        
        แล้วดูที่ Program counter ที่ PC address ต่อไปที่จะไปคือ  00000010 

---
10. sb x3, 0(x2)
        
        store byte
        
        นำข้อมูลใน x3 ไปเก็บไว้ใน address x2
       ![10](https://user-images.githubusercontent.com/98943425/160082228-ed4db6a0-0f36-4b99-996e-f5adbdd74b08.png)
        
        โดยเริ่ม Bus ดึง word มาจาก address 00000010 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะนำ x3 ไปเก็บใน address x2
        
        สังเกตุที่ Bus จะพบว่าดึง data 00000042 (x3) เก็บที่ address c0000000 (address x2) 
        
        และสังเกตุที่จอสีดำด้านซ้ายล่างคือ address x2 ซึ่งจะพบว่ามีตัว B แสดงเพิ่มขึ้นมา กลายเป็น TB
        
        เพราะว่าหากเปิด ascii table เลข 42 ฐาน 16 คือ ตัวอักษร B

---
11. addi x1, x1, 1
        
        add immediate
        
        เอา 1 บวกกับ x1 แล้วนำไปใส่ใน x1
       ![11](https://user-images.githubusercontent.com/98943425/160082616-71c520cb-792e-4b84-98eb-85497706a82d.png)
       
        จะเห็นว่า Bus ดึง word มาจาก address 00000014 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ 00000001 (คือเลข 1 ฐาน 10 ที่แปลงเป็นฐาน 16) + x1 แล้วเก็บใน x1
        
        สังเกตุที่ ALU จะเห็น 1 + x1(ก่อนเปลี่ยน 00000021) และได้ r คือ 00000022 แล้วดู ที่ General-purpose regs จะเห็นว่าที่ x1 จะเท่ากับ 00000022

---
12. jal x0, -16

        jump and link
        
        กระโดดไป -16
       ![12](https://user-images.githubusercontent.com/98943425/160083007-525ba66c-a798-4f4b-a938-74deee860c59.png)
       
        จะเห็นว่า Bus ดึง word มาจาก address 00000018 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ กระโดดจาก address 00000018 ไป -16 ฐาน 10( -10 ฐาน 16)
        
        สังเกตุที่ ALU จะเห็น r จะเห็น 00000008 แล้วดูที่ Program counter ที่ PC address ต่อไปที่จะไปคือ  00000008
---
13. lbu x3, 0(x1)

        load byte unsigned
        
        นำข้อมูลจาก หน่วยความจำ x1 แล้วไปอ่านมาค่า 1 byte มาใส่ใน x3
       ![ๅ-](https://user-images.githubusercontent.com/98943425/160083579-9072045e-e80d-4fd8-b3b2-cd85df8ca950.png)
       
        โดยเริ่ม Bus ดึง word มาจาก address 00000008 เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะนำข้อมูลจาก adress x1 มา 1 byte แล้วไปเก็บใน x3
        
        สังเกตุที่ ALU ที่ r จะเห็น 00000022 
        
        สังเกตุที่ Bus จะพบว่าดึง data 1 byte (00) ที่ address 00000021 (address x1) แล้วไปเก็บที่ x3
        
        จะเห็นว่าที่ General-purpose regs จะเห็นว่าที่ x3 จะเท่ากับ 00000000
---
14. beq x3, x0, +16
 
        branch on equal
        
        ถ้า x3 = x0 ให้ กระโดดไป +16 
       ![14](https://user-images.githubusercontent.com/98943425/160083928-80191f07-8afd-41c0-ab15-c8bae1d741d1.png)
        
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 0000000c เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ ถ้า x3 = x0(มีค่าเป็น 0 เสมอ) จะกระโดดไป +16 ฐาน 10 (หรือ 10 ฐาน 16) address
        
        จะเห็นว่าที่ ALU จะมีการบวก 0000000c + 00000010 จะได้ 0000001c ก็คือจะกระโดดจาก addresss c ไป 1c เงื่อนไข ถ้า x3 = x0
        
        เมื่อดูที่ Comparator จะมีการเช็คเงื่อนไข x3 = x0 ได้คำตอบ true จึงไปที่ address 1c 
        
        แล้วดูที่ Program counter ที่ PC address ต่อไปที่จะไปคือ  0000001c 

---
15. jal x0, 0
        
        กระโดดอยู่กับที่
       ![15](https://user-images.githubusercontent.com/98943425/160084148-80a72439-d49b-405f-baba-efff82d84849.png)
        
        จากรูปจะเห็นว่า Bus ดึง word มาจาก address 0000000c เสร็จแล้วจะส่ง data ไป Instruction reg.
        
        Instruction reg. จะวิเคราห์ว่า data ให้ทำอะไร ในกรณีนี้คือ จะกระโดดอยู่กับที่
        
        สังเกตุ ALU ที่ r จะเห็น 0000001c 
        
        ดูที่ Program counter ที่ PC address ต่อไปที่จะไปคือ  0000001c  ทำให้วนลูป


 

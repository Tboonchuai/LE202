# เขียนโปรแกรม แสดงตัวอักษร (ตัวย่อ ชื่อ สกุล)
---
### อธิบายคำสั่ง

 1. addi x1, x0, 32
  
        add immediate
        
        เอาเลข 32 ฐาน 10 ไปบวกกับ X0(ซึ่งมีค่าเป็น 0) แล้วนำผลลัพธ์ไปแทนใน x1  
        
       ![1](https://user-images.githubusercontent.com/98943425/160077986-cde10fa3-9bfc-40eb-936f-50428347028f.png)


---

 2. lui x2, 0xc0000000
 
        load upper immediate 
        
        นำค่าที่อยู่ทางขวา 1 word ไปใส่ใน x2 แต่ใส่แค่ 20 bit แรกก็คือ(c0000000)

       ![2](https://user-images.githubusercontent.com/98943425/160079575-30997a20-b1fa-4631-8f9d-dfaf3ed094cd.png)

---
 3. lbu x3, 0(x1)

        load byte unsigned
        
        นำข้อมูลจาก หน่วยความจำ x1 แล้วไปอ่านมาค่า 1 byte มาใส่ใน x3
        
       ![3](https://user-images.githubusercontent.com/98943425/160078952-664f81e0-704c-4a81-a1b2-7d346c33116b.png)
---
        
 4. beq x3, x0, +16
 
        branch on equal
        
        ถ้า x3 = x0 ให้ กระโดดไป +16 
       
       ![4](https://user-images.githubusercontent.com/98943425/160079336-838d3d74-4cf9-4e28-9d2b-6c82244b327b.png)

---

 5. sb x3, 0(x2)
        
        store byte
        
        นำข้อมูลใน x3 ไปเก็บไว้ใน address x2
       ![5](https://user-images.githubusercontent.com/98943425/160080101-424ab0d5-0599-4213-ad4b-e99b69c0769d.png)

---
 
6. addi x1, x1, 1

        เอา 1 บวกกับ x1 แล้วนำไปใส่ใน x1
      ![6](https://user-images.githubusercontent.com/98943425/160080965-601b2a3a-4779-4023-8ebc-77fcc8e059cb.png)

---

7. jal x0, -16

        jump and link
        
        กระโดดไป -16

      ![7](https://user-images.githubusercontent.com/98943425/160081167-e84d99e3-100f-40e2-894c-93e77f503817.png)

---
8. lbu x3, 0(x1)

        load byte unsigned
        
        นำข้อมูลจาก หน่วยความจำ x1 แล้วไปอ่านมาค่า 1 byte มาใส่ใน x3
      ![8](https://user-images.githubusercontent.com/98943425/160081700-00d7a11e-a3fc-482d-b1e1-7b8255017a64.png)

---
9. beq x3, x0, +16
 
        branch on equal
        
        ถ้า x3 = x0 ให้ กระโดดไป +16 
      ![9](https://user-images.githubusercontent.com/98943425/160081966-5d75650d-e74f-4929-b4d0-19e1051c5bc2.png)

---
10. sb x3, 0(x2)
        
        store byte
        
        นำข้อมูลใน x3 ไปเก็บไว้ใน address x2
       ![10](https://user-images.githubusercontent.com/98943425/160082228-ed4db6a0-0f36-4b99-996e-f5adbdd74b08.png)

---
11. addi x1, x1, 1

        เอา 1 บวกกับ x1 แล้วนำไปใส่ใน x1
       ![11](https://user-images.githubusercontent.com/98943425/160082616-71c520cb-792e-4b84-98eb-85497706a82d.png) 

---
12. jal x0, -16

        jump and link
        
        กระโดดไป -16
       ![12](https://user-images.githubusercontent.com/98943425/160083007-525ba66c-a798-4f4b-a938-74deee860c59.png)

---
x. jal x0, 0
        
        กระโดดอยู่กับที่




 

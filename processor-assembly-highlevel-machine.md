Processor 
-  ตัวประมวลผล หรือในที่นี้คือ microcontroller

High level language

- ภาษาระดับสูงเป็นภาษาที่สร้างขึ้นเพื่อช่วยอำนวยความสะดวกในการเขียนโปรแกรมกล่าวคือลักษณะของคำสั่ง
จะประกอบด้วยคำต่าง ๆ ในภาษาอังกฤษ ซึ่งผู้อ่านสามารถเข้าใจความหมายได้ทันที ผู้เขียนโปรแกรมจึงเขียนโปรแกรมด้วยภาษาระดับสูงได้ง่ายกว่าเขียนด้วยภาษาแอสเซมบลีหรือภาษาเครื่อง

Assembly (low level language) 

- ภาษาที่ใช้ในการเขียนโปรแกรมภาษาหนึ่งซึ่งจะตรงเข้าไปจัดการกับตัวไมโครโพรเซสเซอร์ หรือ "ตัวประมวลผล" ของเครื่องคอมพิวเตอร์ 
   และจะทำการประมวลผลโดยตรงได้เลย โดยปกติภาษานี้จะเรียนยากและต้องเขียนยาวกว่าภาษา C หรือภาษา BASIC 
   แต่จะทำให้ได้ผลลัพธ์ (result) เร็วกว่า และใช้เนื้อที่เก็บน้อยกว่าโปรแกรมภาษาอื่นมาก นิยมใช้ภาษานี้เมื่อต้องการประหยัดเวลาทำงานของเครื่องคอมพิวเตอร์ 
   และเพิ่มประสิทธิภาพของโปรแกรม โดยไม่ต้องพะวงถึงความชัดเจนมากนัก และที่สำคัญก็คือ โปรแกรมภาษานี้จะเขียนขึ้นมาเพื่อใช้เฉพาะกับเครื่องใดเครื่องหนึ่ง 
   หากจะนำไปใช้กับเครื่องคนละรุ่น ก็จะต้องมีการปรับแก้ก่อน (ขึ้นกับหน่วยประมวลผลหรือ CPU)

Machine language 

- ภาษาคอมพิวเตอร์ที่สามารถทำให้เครื่องรับรู้และเข้าใจได้ เขียนโดยใช้รหัสเลขฐานสองเป็นหลัก คำสั่งแต่ละคำสั่งจะหมายถึงการทำงานอย่างหนึ่ง แต่ละโปรแกรมจึงจะยาวค่อนข้างมาก ไม่ว่าเราจะสั่งให้เครื่องทำงานด้วยโปรแกรมภาษาอะไรก็ตาม ตัวแปลโปรแกรม (compiler) ก็จะต้องทำหน้าที่แปลภาษาที่เราใช้ให้เป็นภาษาเครื่องก่อนเสมอ คอมพิวเตอร์จึงจะเข้าใจจนสามารถปฏิบัติตามคำสั่ง นั้น ๆ ได้

ความสัมพันธ์

Hight level language เป็นภาษาที่ใช้ง่ายในการเขียนโปรแกรมเป็นภาษาที่มนุษย์สามารถเข้าใจได้ จะถูกแปลงไปเป็นภาษา Assebly หรือ Machine language เพื่อให้ microcontroller เข้าใจและทำงานได้

---

# 1.RISC-V
Processor: RISC-V rv64gc clang 14.0.0

Hight level language: C
    
    int square(int num) 
    {
    return num * num;
    }
Assembly: RISC-V rv64gc clang 14.0.0
      
    square(int):                             # @square(int)
     addi    sp, sp, -32
     sd      ra, 24(sp)                      # 8-byte Folded Spill
     sd      s0, 16(sp)                      # 8-byte Folded Spill
     addi    s0, sp, 32
     sw      a0, -20(s0)
     lw      a0, -20(s0)
     mulw    a0, a0, a0
     ld      ra, 24(sp)                      # 8-byte Folded Reload
     ld      s0, 16(sp)                      # 8-byte Folded Reload
     addi    sp, sp, 32
     ret

    
machine language:

![1](https://user-images.githubusercontent.com/98943425/161390292-aa672a81-c922-4ccf-aea1-a77952845a9d.png)

![2](https://user-images.githubusercontent.com/98943425/161390325-c8f2b53b-0448-4d37-9b22-9c93a87f985b.png)

![3](https://user-images.githubusercontent.com/98943425/161390393-32019850-0b16-4023-b6c9-472e99e30eee.png)

---
# 2.x86

Processor: x86-64 gcc (contract labels)

Hight level language: C++

    int square(int num) {
    return num * num;
    }

Assembly: x86-64 gcc (contract labels)

      square(int):
              push    rbp
              mov     rbp, rsp
              mov     DWORD PTR [rbp-4], edi
              mov     eax, DWORD PTR [rbp-4]
              imul    eax, eax
              pop     rbp
              ret

Machine language:

![4](https://user-images.githubusercontent.com/98943425/161390497-eacda805-3ad8-49d0-abd6-e606d826e626.png)


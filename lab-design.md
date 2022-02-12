# เครื่องรดน้ำต้นไม้อัติโนมัติโดยวัดจากความชื้นในดิน
#### วัตถุประสงค์ 

    เพื่อลดน้ำต้นไม้อัติโนมัติ เพื่อลดปัญหาการลืมรดน้ำต้นไม้หรือไม่มีเวลา
  
#### อุปกรณ์ที่ใช้ 
    
    microcontroller
    
    ปั๊มน้ำ
    
    แผงโซลล่าร์เซลล์
    
    อุปกรณ์วัดความชื้นในดิน
    
    สายางขนาดเล็ก
    
    แบตเตอรี่
    
#### ศึกษาข้อมูลเบื้องต้น 
        
    https://www.cybertice.com/article/209/%E0%B8%AA%E0%B8%AD%E0%B8%99%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-nodemcu-esp8266-%E0%B9%80%E0%B8%8B%E0%B9%87%E0%B8%99%E0%B9%80%E0%B8%8B%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A7%E0%B8%B1%E0%B8%94%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%8A%E0%B8%B7%E0%B9%89%E0%B8%99%E0%B9%83%E0%B8%99%E0%B8%94%E0%B8%B4%E0%B8%99-soil-moisture-sensor-module?gclid=Cj0KCQiA0p2QBhDvARIsAACSOON2v1hj34LsmzaGS84qnQ93re_EhUUNWdTqLJIwLxxJypGetw04LIYaAkYpEALw_wcB
    
    https://www.ab.in.th/article/10/%E0%B9%82%E0%B8%9B%E0%B8%A3%E0%B9%80%E0%B8%88%E0%B8%84%E0%B9%80%E0%B8%84%E0%B8%A3%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%87%E0%B8%A3%E0%B8%94%E0%B8%99%E0%B9%89%E0%B8%B3%E0%B8%95%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%A1%E0%B9%89%E0%B8%AD%E0%B8%B1%E0%B8%95%E0%B9%82%E0%B8%99%E0%B8%A1%E0%B8%B1%E0%B8%95%E0%B8%B4-%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2-arduino-%E0%B8%A3%E0%B8%B2%E0%B8%84%E0%B8%B2%E0%B8%96%E0%B8%B9%E0%B8%81-%E0%B8%9E%E0%B8%A3%E0%B9%89%E0%B8%AD%E0%B8%A1-code-%E0%B8%95%E0%B8%B1%E0%B8%A7%E0%B8%AD%E0%B8%A2%E0%B9%88%E0%B8%B2%E0%B8%87
    
    https://www.spsmartplants.com/blog/detail/%E0%B8%A3%E0%B8%B9%E0%B9%89%E0%B8%AB%E0%B8%A3%E0%B8%B7%E0%B8%AD%E0%B9%84%E0%B8%A1%E0%B9%88-%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%8A%E0%B8%B7%E0%B9%89%E0%B8%99%E0%B9%83%E0%B8%99%E0%B8%94%E0%B8%B4%E0%B8%99%E0%B8%A1%E0%B8%B5%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B3%E0%B8%84%E0%B8%B1%E0%B8%8D%E0%B8%81%E0%B8%B1%E0%B8%9A%E0%B8%9E%E0%B8%B7%E0%B8%8A%E0%B8%A1%E0%B8%B2%E0%B8%81/5#:~:text=2.%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%8A%E0%B8%B7%E0%B9%89%E0%B8%99%2070%25%20%2D%2079,%E0%B9%83%E0%B8%AB%E0%B9%89%E0%B8%9E%E0%B8%B7%E0%B8%8A%E0%B9%80%E0%B8%88%E0%B8%A3%E0%B8%B4%E0%B8%8D%E0%B9%80%E0%B8%95%E0%B8%B4%E0%B8%9A%E0%B9%82%E0%B8%95%E0%B9%84%E0%B8%94%E0%B9%89
    
    http://cheqa.rmuti.ac.th/rmuti_2200/SAR%202559/%E0%B8%A3%E0%B8%B0%E0%B8%94%E0%B8%B1%E0%B8%9A%E0%B8%84%E0%B8%93%E0%B8%B0/%E0%B8%AD%E0%B8%87%E0%B8%84%E0%B9%8C%202/2.3-18.pdf

#### วิธีการทำการทดลอง
    
    1.เขียนโปรแกรมลงใน microcontroller
    
    2.ต่อท่อจากแหล่งน้ำแล้วนำปั้มน้ำไปวางนำอุปกรณ์วัดความชื้นปักลงในดิน ต่อโซลล่าเซลล์กับแบตเตอรี่และอุปกรณ์ต่าง ๆ เข้ากับไมโครคอนโทรลเลอร์
![image](https://user-images.githubusercontent.com/98943425/153719252-7887c459-42c1-42c2-a123-b27c49b03c6a.png)

    
    3.เมื่อความชื้นในดินต่ำกว่า 50% ให้ลดน้ำ เพื่อคงสภาวะความชื้นให้อยู่ในระดับ 50% - 60%
![image](https://user-images.githubusercontent.com/98943425/153719297-fdaa1f82-2fb4-4e73-86e1-54668953e164.png)


# ระบบบันทึกข้อมูลงานซ่อม
เป็นระบบสำหรับร้านรับซ่อมทั่วไป เช่น ร้านซ่อมมือถือ ร้านซ่อมเครื่องใช้ไฟฟ้า หรือแม้แต่ร้านซ่อมรถ ตัวระบบสามารออก (สั่งพิมพ์) ใบรับซ่อมได้
และลูกค้าสามารถติดตามสถานะการซ่อมได้ด้วยตัวเองผ่าน QRCode บนมือถือ สามารถมีช่างซ่อมได้หลายคน
และ สามารถมีพนักงานรับเครื่องซ่อมแยกต่างหากได้ด้วย ระบบเว็บไซต์รองรับมือถือ

## การติดตั้ง
### 1. สร้างฐานข้อมูล ```repair``` และ นำเข้าข้อมูลจากไฟล์ ```repair.sql```
### 2. แก้ไขค่าติดตั้งของฐานข้อมูลให้ถูกต้อง ไฟล์ settings/database.php

```
<?php
/* settings/database.php */
return array(
  'mysql' => array(
    'dbdriver' => 'mysql',
    'username' => 'root',
    'password' => '',
    'dbname' => 'repair',
    'prefix' => 'rp',
  ),
  'tables' => array(
    'user' => 'user',
    'category' => 'category',
    'repair' => 'repair',
    'inventory' => 'inventory'
  )
);
```

### 3. สร้างไดเร็คทอรี่ ```datas/``` ถ้ายังไม่มีและปรับ chmod ให้สามารถเขียนได้หรือปรับ chmod ให้เป็น 777

## การใช้งาน
* เข้าระบบเป็นผู้ดูแลระบบ : ```admin@localhost``` และ Password : ```admin```
* เข้าระบบเป็นช่างซ่อม : ```demo@localhost``` และ Password : ```demo```
* เข้าระบบเป็นช่างซ่อม : ```demo2@localhost``` และ Password : ```demo```

## ข้อตกลงการนำไปใช้งาน
เป็นระบบที่พัฒนาขึ้นเพื่อทดสอบการทำงาน และการเรียนรู้การใช้งาน Kotchasan PHP Framework
โดยมีจุดประสงค์หลักเพื่อให้ตื่นตัวในการใช้งานคชสาร และ สามารถพัฒนาต่อยอดได้ ```ห้ามมิให้นำระบบที่แจกไปขาย```
แต่หากมีการพัฒนาต่อเติมแล้วให้สิทธิต่างๆในซอร์สโค้ดเป็นไปตามที่ผู้พัฒนากำหนด
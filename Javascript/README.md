# สรุปเนื้อหา Javascript

เอกสารชุดนี้ครอบคลุมพื้นฐาน JavaScript สำหรับใช้งานกับหน้าเว็บ ตั้งแต่ตัวแปร, โครงสร้างควบคุม, การจัดการข้อมูล ไปจนถึงการเข้าถึงและอัปเดต DOM

## 1) พื้นฐานภาษา (จาก `js_basic.md`)
- **ตัวแปรหลัก**: `string`, `number`, `boolean`, `object`, `array`
- **Operator**: `+ - * / %` และเงื่อนไข `&& || !`
- **เงื่อนไข**: ใช้ `if / else if / else` ในการตัดสินใจ (เช่นคำนวณเกรด)
- **Loop**: `while` และ `for`
- **Array methods**:
	- `push()` เพิ่มข้อมูลท้ายลิสต์
	- `pop()` ลบข้อมูลท้ายลิสต์
	- `sort()` เรียงข้อมูล
	- `includes()` เช็คว่ามีค่านั้นหรือไม่
- **Function 3 แบบ**:
	- function ปกติ
	- arrow function
	- parameter function (callback)
- **Callback ที่ใช้บ่อย**:
	- `map()` แปลงค่าทุกสมาชิก
	- `forEach()` วนลูปเพื่อทำงาน
	- `filter()` คัดข้อมูลตามเงื่อนไข
- **Object**:
	- เข้าถึงด้วย dot notation เช่น `std.name`
	- ประยุกต์ใช้ `map()/filter()/find()` กับ array ของ object

## 2) การเลือก DOM และ Event (จาก `js_selector.md`)

### Selector DOM
- `getElementById()` เลือก element เดียวจาก `id`
- `getElementsByClassName()` ได้หลาย element (ลักษณะคล้าย array)
- `querySelector()` เลือกตัวแรกที่ match (รองรับ `#id`, `.class`, `tag[attr]`)
- `querySelectorAll()` เลือกทุกตัวที่ match (ได้รายการหลายตัว)

### Event พื้นฐาน
- `onclick` เมื่อคลิก
- `onchange` เมื่อค่าของ input เปลี่ยน
- `onkeydown / onkeyup / onkeypress` จับเหตุการณ์แป้นพิมพ์
- `onmouseover / onmouseup / onmousedown` จับเหตุการณ์เมาส์
- `addEventListener()` เป็นอีกวิธีที่ยืดหยุ่นในการผูก event

## 3) การอ่าน/อัปเดต DOM (จาก `js_updateDOM.md`)

### การอ่านค่าใน element
- `textContent` ดึงข้อความทั้งหมด (รวมที่ซ่อน)
- `innerText` ดึงเฉพาะข้อความที่ผู้ใช้เห็น
- `innerHTML` ดึงโครงสร้าง HTML ภายใน

### การอัปเดตค่า
- ใช้ `element.innerHTML = ...` เพื่อเขียน HTML ใหม่ลง DOM
- ตัวอย่างการสร้าง `<ul><li>...</li></ul>` จากค่าที่เลือกใน checkbox แล้วแสดงใน `div`

### จัดการ Attribute
- `getAttribute()` อ่านค่า attribute
- `setAttribute()` เปลี่ยนค่า attribute (เช่นเปลี่ยนลิงก์ หรือ `disabled` ปุ่ม)

### ใช้ `event` ให้โค้ดสั้นลง
- ส่ง `event` เข้า function แล้วใช้ `event.target` เพื่ออ้าง element ต้นทางโดยตรง

## 4) แบบฝึกหัด: Filter images (จาก `exercise_1.html`)
- มีปุ่มกรองรูป: `All`, `Dog`, `Cat`, `Bunny`
- เมื่อกดปุ่ม จะเลือกภาพตามประเภทด้วย `querySelectorAll()`
- ประกอบ HTML เป็น string แล้วแสดงผ่าน `innerHTML` ที่ `#display`
- แนวคิดสำคัญ: **อ่าน DOM → ประมวลผลข้อมูล → อัปเดต DOM**

## 5) ไฟล์ `main.js`
- ตัวอย่างประกาศตัวแปรพื้นฐานและแสดงผลด้วย template literal
- ใช้ `console.log()` ตรวจสอบค่าระหว่างเรียนรู้

---

## สรุปภาพรวม
หลังเรียนชุดนี้ควรทำได้:
1. เขียน JavaScript พื้นฐานและจัดการข้อมูลแบบ array/object
2. เลือก DOM ได้หลายรูปแบบตามสถานการณ์
3. รับ event จากผู้ใช้และตอบสนองได้
4. อัปเดตหน้าเว็บแบบ dynamic ด้วย `innerHTML` และ attribute
5. ทำแบบฝึกหัดเชิงโต้ตอบง่าย ๆ เช่นระบบกรองรูป

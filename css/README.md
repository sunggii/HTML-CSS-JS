# สรุปเนื้อหา CSS

ไฟล์ชุดนี้รวบรวมพื้นฐาน CSS สำหรับมือใหม่ ตั้งแต่การเลือก element, การจัด layout, การตกแต่งองค์ประกอบ ไปจนถึง responsive design

## 1) CSS พื้นฐาน (จาก `css_basic.md`)

### Selector ที่ต้องรู้
- เลือกด้วย `tag`, `#id`, `.class`
- รูปแบบการเลือกที่ใช้บ่อย:
	- ลูกหลาน: `.parent .child`
	- class ร่วม: `.button.active`
	- เลือกลูกตรง: `.parent > .child`
	- เพื่อนติดกัน: `.item1 + .item2`
	- attribute: `input[type=text]`

### Pseudo
- **Pseudo class**: `:hover`, `:active`, `:focus`, `:first-child`, `:nth-child()`, `:last-child`
- **Pseudo element**: `::before`, `::after`, `::first-letter`

### แนวคิดที่มักสับสน
- `<div>` (block) vs `<span>` (inline)
- `margin` (ระยะนอกกล่อง) vs `padding` (ระยะในกล่อง)
- เส้นคั่นทำได้ทั้ง `<hr>` และ class ที่กำหนดเอง

### Position
- `static`, `relative`, `absolute`, `fixed`, `sticky`

### ขนาดและหน่วย
- ขนาดหัวข้อ `<h1>` ถึง `<h6>` มีขนาด default ต่างกัน
- หน่วยสำคัญ: `%`, `vw/vh`, `em`, `rem`

### การจัดวาง
- พื้นฐาน Flexbox: `display: flex`, `justify-content`, `align-items`, `align-content`, `align-self`
- ภาพรวมเทคนิค layout: `Flexbox`, `Grid`, `Float`, `Position`, `Inline-block`, `Multi-column`

## 2) CSS Kit ที่ใช้บ่อย (จาก `css_kit.md`)
- ตั้งค่าเริ่มต้น (`reset`) ด้วย `* { margin: 0; padding: 0; box-sizing: border-box; }`
- import ฟอนต์จาก Google Fonts
- ปรับค่า default ของ `a` และ `ul` เช่น `text-decoration: none`, `list-style: none`
- ไล่สีด้วย `linear-gradient(...)`
- จัดหน้าแบบกึ่งกลางด้วย `.container` หรือกำหนดที่ `body`
- ใช้ `title="..."` บน `<a>`/`<img>` เพื่อแสดง tooltip
- ทำปุ่ม/แท็กทรงโค้ง เช่น `.highlight`, `.btn`
- ใส่ภาพพื้นหลังด้วย `background-image`, `background-size: cover`, `background-position: center`
- โครงช่วยจัดหน้า `.row` และ `.col`
- เอฟเฟกต์ hover ภาพด้วย `transform: scale(...)` + `transition`

## 3) Responsive Design (จาก `css_responsive.md`)
- ใช้ `@media screen` เพื่อเปลี่ยน style ตามขนาดหน้าจอ
- ตัวอย่างหลัก: `@media screen and (max-width: 768px)`
	- จอ `<= 768px` ใช้ style สำหรับมือถือ/แท็บเล็ต
	- จอใหญ่กว่าใช้ style desktop
- แนวคิด breakpoint อ้างอิงได้จาก Material และ Tailwind

## สรุปภาพรวม
หลังเรียนชุดนี้ควรทำได้:
1. เลือก element และเขียน selector ได้ถูกต้อง
2. ใช้ pseudo class/element เพื่อเพิ่มพฤติกรรมและลูกเล่น
3. เข้าใจ spacing, position, หน่วยวัด และการจัด layout
4. ใช้ชุด CSS utility พื้นฐานเพื่อเริ่มโปรเจกต์ได้เร็ว
5. ทำหน้าเว็บให้ responsive ด้วย media query

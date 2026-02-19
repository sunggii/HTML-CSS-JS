# สรุป Component (HTML + CSS)

เอกสารชุดนี้รวมตัวอย่าง component ที่นำไปใช้ทำหน้าเว็บได้ทันที เน้นโครงสร้างง่าย, responsive และมี interaction พื้นฐาน

## 1) Card Component (จาก `card.md`)

### โครงสร้างหลัก
- ใช้โครง `#card-area > .box-area > .box`
- ในแต่ละ `.box` มี:
	- รูปภาพ (`img`)
	- ชั้นข้อมูลซ้อนทับ (`.overlay`) เช่น ชื่อ, คำอธิบาย, ปุ่ม

### เทคนิคสำคัญ
- จัดเรียงการ์ดด้วย **CSS Grid**
	- `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`
- การ์ดทำเอฟเฟกต์ hover ด้วย `transform`
- ซ่อน overlay ไว้ด้านล่างก่อน (`translateY(100%)`) แล้วเลื่อนขึ้นเมื่อ hover
- ใช้ `overflow: hidden` + `border-radius` เพื่อคุมขอบรูปและ overlay

### จุดเด่น
- responsive อัตโนมัติตามขนาดหน้าจอ
- ใช้โครงเดียว แต่เปลี่ยนข้อมูลได้หลายใบ

## 2) Pinterest-style Display (จาก `pinterest_display.md`)

### โครงสร้างหลัก
- ใช้ `section#columns` ครอบ `figure`
- ใน `figure` มี `img` + `figcaption`

### เทคนิคสำคัญ
- ใช้ **CSS Multi-column** แทน grid:
	- `column-width: 320px`
	- `column-gap: 15px`
- แต่ละ `figure` เป็น `inline-block` เพื่อเรียงต่อคอลัมน์
- เพิ่มความเด่นของรูปที่ชี้เมาส์ด้วย:
	- `#columns:hover figure:not(:hover) { opacity: 0.4; }`

### จุดเด่น
- เหมาะกับ gallery ที่รูปสูงไม่เท่ากัน
- ได้ฟีล masonry/pinterest แบบ CSS ล้วน

## 3) Slide Image (จาก `slide_img.md`)

### โครงสร้างหลัก
- `.slider-wrapper` ครอบ `.slider` และ `.slider-nav`
- `.slider` มีรูปหลายรูปที่กำหนด id (`#slide-1`, `#slide-2`, ...)
- `.slider-nav a` ลิงก์ไปยังแต่ละ slide ด้วย anchor

### เทคนิคสำคัญ
- ใช้ `display: flex` + `overflow-x: auto` ทำแนวนอน
- ใช้ `scroll-snap-type: x mandatory` และ `scroll-snap-align: start` ให้สไลด์ล็อกตำแหน่ง
- ใช้ `scroll-behavior: smooth` ให้เลื่อนนุ่ม
- ใช้ `aspect-ratio` คุมสัดส่วนรูป (เช่น `3 / 4`)
- ซ่อน scrollbar เพื่อความสะอาดของ UI

### จุดเด่น
- ทำ image slider ได้โดยไม่ต้องพึ่ง JavaScript
- เหมาะกับงานโชว์ภาพ, โปรไฟล์ผลงาน, hero section แบบเล็ก

## สรุปภาพรวม
หลังเรียนชุด component นี้ควรทำได้:
1. ทำ card grid ที่มี overlay และปุ่ม action
2. จัด gallery แบบ pinterest ด้วย CSS columns
3. สร้าง slider แบบ snap-scroll ด้วย HTML/CSS ล้วน
4. เลือกเทคนิค layout ให้เหมาะกับชนิดคอนเทนต์ (Grid / Columns / Flex)

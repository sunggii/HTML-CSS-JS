# Responsive
เอาไว้เป็นแนวทาง 
- [material.io](https://m3.material.io/foundations/layout/applying-layout/window-size-classes)
- [tailwindcss](https://tailwindcss.com/docs/responsive-design)
    - 640px  mobile
    - 768px  tablet
    - มากกว่า 768px destop(1024)  desingหลัก


## breakpoint (@media screen)
จะใช้คำสั่งนี้เป็นตัวกำหนด css ของแต่ละขนาดหน้าจอ
- ```(max-width: 768px)``` แปลว่าหน้าจอที่ใหญืที่สุดที่ยังทำ cssนั้น 

**ตัวอย่าง** แสดงให้เห็นถึง style ที่เปลี่ยนไปตามขนาดของหน้าจอ
 -  768px จอเป็นสีน้ำเงิน
 -  มากกว่า 768px จอเป็นสีแดง

![alt text](ex_responsive.gif)

## Html
```html
<div class="container">
    breakpoint 768px is blue
</div>
```
## CSS
```css
.container{
    background-color: red; /* ความต่าง */

    min-height: 100vh;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}

/*หน้าจอที่ใหญ่ที่สุดที่จอเป็นสีน้ำเงิน*/
@media screen and (max-width: 768px){
    .container{
        background-color: blue; /*ความต่าง*/

        min-height: 100vh;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
    }
}
```
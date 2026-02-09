# CSS kit
รวบ tip css ที่ใช้บ่อย

## set up
- import font จาก [google font](https://fonts.google.com/)
![alt text](/img/font.png)

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap'); /*ก้อปมาวาง*/

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /*กำหนดให้กล่องเป็นขนาดจริง ไม่รวม margin padding*/
    font-family: 'Poppins'; /*ชื่อ font ที่ import มา*/
}

a {
    text-decoration: none; /*a ไม่มีเส้นใต้*/
}
ul {
    list-style: none; /*li ไม่มีตุ่ม*/
}

```

## css ไล่สี
```css
background: linear-gradient(135deg, #ff9a9e, #fecfef);
```

## .container vs กำหนดที่ ```<body>```
* เป็นกสรกำหนดกล่องใช้เอง จะได้ไม่ต้องใช้ .container ของ boostrap
```css
section {
    width: 80%;
    margin: 80px auto;
}
```
หรือ

```css
.container{
    width: 80%;
    margin: 80px auto;
}
```

* ส่วนตัวคิดว่าแบบนี้ไม่เปลือง class ดี
```css
 body {
    max-width: 800px; /*กำหนดให้ content อยู่กลาง*/
    margin: 0 auto;
}
```

## เอา mouse ไปจ่อแล้วขึ้นคำ ด้วย ```title=```
* ใช้ได้กับทั้ง ```<img>``` และ ```<a>```
```html
    <a href="https://www.google.com/" 
                onclick="alert('คลิกแล้ว! ปกติจะไปที่ pixel google');" 
                target="_blank"
                title="กด"  
        > click
    </a>
```
**result**

![alt text](/img/click.png)


## .highlight vs .btn
ไอเดียการใช้ปุ่มขอบโค้ง
* ```.highlight ``` ใช้กับ ```<span></span>```
* ```.btn``` ใช้กับ ```<a></a>```
```css
.highlight , .btn{
    background-color: #3573b7;
    border-radius: 20px;
    
    padding: 4px 8px; /* เพิ่มช่องว่างเล็กน้อยรอบข้อความ */
    align-items: center;
}

```
```html
    <span class="highlight">hello</span>
    <span class="highlight">hello apin</span>

    <a href="#" class="btn">button</a>
```
**result**

![alt text](/img/btn.png)


## ใส่รูปพื้นหลังบางส่วน
```html
  <section class="section-1">
    <div class="explore-content">
      <h1>EXPLORE THE WORLD</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe, dignissimos nisi quas similique, quod dicta
        veritatis commodi sapiente temporibus laboriosam odit itaque iure corrupti praesentium.</p>
      <a href="#" class="btn">Show more </a>
    </div>
  </section>
```

```css
.section-1 {
    width: 100%;  /*กว้างเต็มจอ*/
    height: 100vh; /*ยาวเต็มจอ ณ จังหวะเปิด*/

    background-image: url(img/bg.jpg);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;

    display: flex;
    align-items: center;
    margin-top: 0px;
}
```

## .row and .col
* เราสามารถเขียน ```.row , .col``` ไว้ใช้จัดหน้าได้ สะดวกดี
```css
.row {
    display: flex;
    align-items: center;
    width: 100%;
    justify-content: space-between;
    
}
.row .col {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

## ทำรูปดึ้บๆ
```css
/*Animations*/
img {
    transition: tranform .3s ease;
}
img:hover {
    transform: scale(1.1);
    cursor: pointer;
}
```
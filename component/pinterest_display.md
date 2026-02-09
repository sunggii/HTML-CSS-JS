# จัดรูป แบบ pinteres ด้วย css
ref code: [youtube](https://youtu.be/iweHJ7Gqjxs?si=I95vDPVxQlXVtcBG)
![alt text](/img/pin_img.png)

## Html
```html
<section id="columns">
    <figure>
        <a href="https://pixabay.com/th/" target="_blank">
            <img src="img/hik.jpg" />
        </a>
        <!-- ให้ coppy figcaption ตามจำนวนรูปที่ต้องการ -->
        <figcaption>Lorem ipsum, dolor sit amet consectetur adipisicing elit.
         Dignissimos animi natus reprehenderit asperiores veritatis voluptas 
            sint inventore mollitia quos impedit!
        </figcaption>
    </figure>
</section>
```

## CSS
```css
#columns {
    column-width: 320px;
    column-gap: 15px;
    width: 90%;
    max-width: 1100px;
    margin: 50px auto;
}
       
#columns figure {
    background: #efefef;
    border: 2px solid #fcfcfc;
    box-shadow: 0 1px 2px rgba(35, 25, 25, .4);
    margin: 0 2px 15px;
    padding: 15px;
    padding-bottom: 10px;
    transition: .4s ease-in-out;
    display: inline-block;
    /*column-break-inside: avoid; ไม่ใส่ก็ได้*/
}

#columns figure img {
    width: 100%;
     height: auto;
    border-bottom: 1px solid #ccc;
    padding-bottom: 15px;
    margin-bottom: 5px;
}

#columns:hover figure:not(:hover) {
    opacity: 0.4;
}
```
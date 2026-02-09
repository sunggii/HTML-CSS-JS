# slide image
ref code: [youtube](https://youtu.be/McPdzhLRzCg?si=XgigkiKUb4Yeb-wx)

![alt text](/img/slide.png)

| อัตราส่วน | ใช้กับอะไรบ่อย                    |
| --------- | --------------------------------- |
| `16 / 9`  | วิดีโอ YouTube, หน้าจอทีวี        |
| `4 / 3`   | จอเก่า, รูปถ่ายบางประเภท          |
| `1 / 1`   | กรอบรูปสี่เหลี่ยมจัตุรัส, โปรไฟล์ |
| `3 / 4`   | รูปแนวตั้ง                        |
| `21 / 9`  | จอกว้างพิเศษ (Ultra-Wide)         |

## Html
```html
    <section class="container">
        <div class="slider-wrapper">
            <div class="slider">
                <img id="slide-1" src="https://cdn.pixabay.com/photo/2025/06/16/14/06/ring-necked-parakeet-9663360_1280.jpg" alt="parakeet">
                <img id="slide-2" src="https://cdn.pixabay.com/photo/2025/04/28/17/02/acacia-9565430_1280.jpg" alt="acacia">
                <img id="slide-3" src="https://cdn.pixabay.com/photo/2025/06/18/08/31/wheat-9666681_1280.jpg" alt="wheat">
            </div>

            <div class="slider-nav">
                <a href="#slide-1"></a>
                <a href="#slide-2"></a>
                <a href="#slide-3"></a>
            </div>
        </div>
    </section>
```

## CSS
```css
        /*max-width จำเป็นไม่งั้นใหญ่เกิน*/
        .container {
            max-width: 400px;
            width: 100%;
        }

        .slider {
            display: flex;
            aspect-ratio: 3 / 4; /* ขนาดรูป*/
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            box-shadow: 0 1.5rem 3rem -0.75rem hsla(0, 0%, 0%, 0.25);
            border-radius: 12px;
            overflow-x: auto;

            /* ซ่อนแถบเลื่อน */
            scrollbar-width: none;
            -ms-overflow-style: none;
        }

        /* ซ่อนแถบเลื่อน */
        .slider::-webkit-scrollbar {
            display: none;
        }

        .slider img {
            flex: 1 0 100%;
            scroll-snap-align: start;
            object-fit: cover;
            border-radius: 12px;
        }

        /* ตุ่มเลื่อน */
        .slider-wrapper {
            position: relative;
            margin: 0 auto;
        }

        .slider-nav {
            display: flex;
            column-gap: 1rem;
            position: absolute;
            bottom: 1.25rem;
            left: 50%;
            transform: translate(-50%);
            z-index: 1;
        }

        .slider-nav a {
            /* ขนาดตุ่มเลื่อน  */
            width: 0.4rem;
            height: 0.4rem;
            border-radius: 50%;
            background-color: #fff;
            opacity: 0.7;
            transition: all ease 250ms;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .slider-nav a:hover {
            opacity: 1;
            transform: scale(1.2);
        }

        /* เพิ่มเอฟเฟกต์เมื่อคลิก */
        .slider-nav a:active {
            transform: scale(0.9);
        }
        /*--------------*/
```
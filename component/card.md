# card component
![alt text](/img/card.png)

## Html
```html
      <div id="card-area"> 
        <div class="box-area">
            <div class="box">
                <img src="https://cdn.pixabay.com/photo/2023/01/08/09/36/mountain-7704817_1280.jpg" alt="Kayaking">
                <div class="overlay">
                    <h3>Kayaking</h3>
                    <p>Paddle through crystal clear waters and discover hidden coves and wildlife.</p>
                    <a href="#">Book now</a>
                </div>
            </div>

            <div class="box">
                <img src="https://cdn.pixabay.com/photo/2022/10/07/11/02/autumn-7504820_1280.jpg" alt="Rock Climbing">
                <div class="overlay">
                    <h3>Rock Climbing</h3>
                    <p>Challenge yourself with our rock climbing adventures suitable for all skill levels.</p>
                    <a href="#">Book now</a>
                </div>
            </div>

            <div class="box">
                <img src="https://cdn.pixabay.com/photo/2025/05/21/15/08/classic-cars-9614046_1280.jpg" alt="Cycling">
                <div class="overlay">
                    <h3>Mountain Biking</h3>
                    <p>Ride through scenic mountain trails with our high-quality bikes and safety equipment.</p>
                    <a href="#">Book now</a>
                </div>
            </div>

        </div>
    </div>
```

## CSS
```css
        /*--------------*/
         #card-area { /*กำหนดไว้เหมือน container*/
            max-width: 1200px;
            margin: 0 auto;
        }

        .box-area {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /*กำหนดขนาด card*/
            grid-gap: 40px;
            margin-top: 50px;
        }
        
        .box {
            position: relative;
            height: 300px; /*กำหนดขนาดรูป*/
            border-radius: 10px;
            overflow: hidden; /*ทำให้มองไม่ของที่อยู่ใน div ย่อย*/
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;
        }

        /*กรณีใช้ flex
       .box-area {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
            margin-top: 50px;
        }
        
        .box {
            position: relative;
            height: 300px;  /*กำหนดขนาดรูป
            border-radius: 10px;
            overflow: hidden; /*ทำให้มองไม่ของที่อยู่ใน div ย่อย
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;

            flex: 1 1 250px;
            min-width: 250px;
        }
        /*-------------*/
        .box:hover {
            transform: translateY(-5px);
        }

        .box img {
            width: 100%;  /*ตีเต็ม 100% ของ 300px ที่กำหนดไว้ใน .box*/
            height: 100%;
            object-fit: cover;
        }

        .overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
            color: white;
            padding: 20px;
            transform: translateY(100%);  /*พลักให้อยู่ล่างกล่อง*/
            transition: transform 0.3s ease;
        }

        .box:hover .overlay {
            transform: translateY(0);  /*popup ขึ้นมา*/
        }

        .overlay h3 {
            font-size: 1.5em;
            margin-bottom: 10px;
        }

        .overlay p {
            margin-bottom: 15px;
            line-height: 1.4;
        }

        .overlay a {
            display: inline-block;
            background-color: #007bff;
            color: white;
            padding: 8px 16px;
            text-decoration: none;
            border-radius: 15px;
            transition: background-color 0.3s ease;
        }

        .overlay a:hover {
            background-color: #0056b3;
        }
        /*--------------*/
```
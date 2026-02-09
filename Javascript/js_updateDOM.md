# Update HTML (DOM)
- เมื่อเราเข้าใจการ access ไปยัง html แล้ว
- ในหัวข้อนี้จะพูดถึงการ update html

**step** การ update HTM มี 2 step คือ
## 1. ทำการดึงข้อความทั้งหมดของ element นั้นออกมา เพื่ออ่าน
หรืออาจจะใช้ดูค่า DOM ที่ไม่ได้กำหนด value

โดยมีการอ่าน 3 แบบ 
- textContent
- innerText
- innerHTML ใช้กับการ update

```html
<div id="hello">
        Hello <span style="display: none;">Mike</span>
    </div>

    <script>
        let helloDom = document.getElementById('hello')
        
        console.log(helloDom.textContent) //ดึงข้อความทั้งหมดออกมา
        console.log(helloDom.innerText)   //ดึงข้อความที่ User เห็น
        console.log(helloDom.innerHTML)   //ดึงมาทั้ง html
    </script>
```
**result**

 ![alt text](/img/innertext.png)

## 2. การ update 
**example 1**
- ใช้ ```.innerHTML``` เพื่อเขียนข้อความที่ต้องการ update
```html
    <div id="hello">
        Hello <span style="display: none;">Mike</span> <!-- ข้อความเดิม -->
    </div>

    <script>
        let helloDom = document.getElementById('hello') //เข้าถึง DOM input
        helloDom.innerHTML ='Hello <b>P</b>' //เขียนข้อความใหม่ทับ DOM เดิม
        
        //ข้อความถูก update จาก Mike -> hello
        console.log(helloDom.textContent) 
        console.log(helloDom.innerText)   
        console.log(helloDom.innerHTML)   
    </script>
```

**example 2**
- ใช้ script เพื่อประกอบ tag html
- จะยังไม่แสดง Interest list ในตอนแรก
- เมื่อคลิ๊กสิ่งที่สนใจจะมาแสดงเป็น list ที่ ```div id="content>```
```html
    <div>
        <h2>Interest</h2>
        <div id="content">
            <!--แสดงสิ่งที่ user สนใจ -->
        </div>
    </div>

    <input type="checkbox" name="Interest" value="book"> book
    <input type="checkbox" name="Interest" value="coding"> coding
    <input type="checkbox" name="Interest" value="cooking"> cooking
    <input type="checkbox" name="Interest" value="sport"> sport

    <button onclick="submitInterest()">submit</button>

    <script>
        function submitInterest () {
            //เลือกไปยัง checkbox ทั้งหมด
            let interestDom = document.querySelectorAll('input[name = Interest]')
            let contentHTML = '<ul>'

            for (let index = 0; index < interestDom.length; index++) {
                //if เอาต่า value ออกมาเฉพาะตัวที่เลือก 
                if (interestDom[index].checked) {
                    contentHTML += '<li>' + interestDom[index].value + '</li>' //มัดรวมก้อนนนี้ไปต่อ contentHTML
                } 
            }
            //วนค่าตัวที่เลือก ใส่ html กลับไป
            contentHTML += '</ul>' //จะได้ List ออกมา

            //ใส่ html กลับเข้าไป
            let contentDom = document.getElementById('content') //เข้าถึง div id="content"
            contentDom.innerHTML = contentHTML //เอา list ที่ได้ใส่กลับเข้าไป
        }
    </script>
```

## ตัวอย่างการใช้ ```getAttribute('')``` , ```setAttribute(' ' , ' ')```
* ใช้ ```getAttribute('')``` เพื่อเข้าถึง
* ใช้ ```setAttribute(' ' , ' ')``` เพื่ออัพเดท

**ตัวอย่าง** การ get, set

```html
    <a id="thislink" href="https://google.com" target="_blank">Google</a>

    <script>
        //let thislinkDom = document.getElementById('thislink')
        let thislinkDom = document.querySelector('#thislink')

        //ดูข้อมูลใน att ต่างๆ
        console.log(thislinkDom.getAttribute('id')) 
        console.log(thislinkDom.getAttribute('href'))
        console.log(thislinkDom.getAttribute('target'))
        
                                //เปลี่ยนอะไร , เป็นอะไร
        thislinkDom.setAttribute('href' , 'https://yahoo.com')
  
    </script>
```

**ตัวอย่าง** การใช้ get, set กับ button ให้กดแล้วจะ disabled

```html
    <button id="thisbutton" onclick="submitData()">submit</button>

    <script>
        function submitData() {
            let thisbuttonDOM = document.getElementById('thisbutton')
            thisbuttonDOM.setAttribute('disabled', 'true')
            //thisbuttonDOM.style.backgroundColor = 'red' //.style จะเปลี่ยน css ได้
        }
  
    </script>
```

**ตัวอย่าง** การใช้ตัวแปร ```even```

* ```even``` เป็นตัวแปรที่ชี้ตัวเองว่าเกิดอะไรขึ้นที่ตัวเอง code สั้นลงและได้ผลลัพธ์เหมือนข้างบน

```html
    <button onclick="submitData(event)">submit</button>

    <script>
        function submitData(event) {
            let thisbuttonDOM = event.target
            thisbuttonDOM.style.backgroundColor = 'red' 
            console.log(thisbuttonDOM.style.backgroundColor)
        }
  
    </script>
```

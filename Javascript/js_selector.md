# Javascript selector
- link lec พี่ไมค์ [ep.6](https://docs.mikelopster.dev/c/web101/chapter-6/selectdom)
- javascript สามารถสื่อสารกับ html (DOM) ปกติเราจะแบ่งไอเดียง่ายๆออกเป็น 2 แบบคือ
    - javascript access ไปยัง html (Selector DOM)
    - html ส่ง Event ไปยัง javascript (Javascript Event)
- วิธี run (Test code) 
    - สร้างไฟล์ .html เช่น ```test.html```
    - เปิดไฟล์ที่สร้าง
    - คลิ๊กขวา
    - แล้วดู output ที่ console

## Selector DOM มี 4 แบบ
ไอเดียของ Selector DOM (javascript access) เหมือนกับ CSS Selector คือ
- เลือกใคร (html element ตัวไหน)
- ทำอะไร (เช่น ดึงค่าออกมา, แทนค่า)

### 1. getElementById 
**step**
* ```id="firstname" ``` เข้าถึง id 
* สร้างตัวแปรมาเก็บค่าที่ select ```let firstnameDOM = document.getElementById('firstname')```
* ```firstnameDOM.value``` ใช้  ```.value``` เพื่อเข้าถึงค่าใน DOM ออกมา

```html
<body>
    first name: 
    <input 
        id="firstname" 
        type="text" 
        name="firstname" 
        value="ทดสอบ" 
    >
    
    <script>
        console.log('Hello wolrd')

        let firstnameDOM = document.getElementById('firstname')

        // สำหรับแสดง DOM html ออกมา
        console.log('firstname DOM', firstnameDOM)

        // สำหรับการดึงค่า value ออกมา
        console.log('firstname DOM', firstnameDOM.value)
    </script>
</body>
```
**result**

![alt text](/img/select-id.png)

------

### 2. getElementByClassname
- ไอเดียเหมือน CSS เราจะใช้ classname ก็ต่อเมื่อเราอยากเข้าถึงทีละหลายๆตัว 
- แต่สิ่งที่ได้มาจะเป็น arr ดังนั้นเราต้อง loop เพื่อเข้าถึง value

**step** เหมือน id 
```html
<body>
    first name: <input class="input" id="firstname" type="text" name="firstname" value="ทดสอบ">
    last name: <input class="input" id="lastname" type="text" name="firstname" value="last">
    
    <script>
        let inputsDOM = document.getElementsByClassName('input')

        // สำหรับแสดง DOM html ออกมา
        console.log(inputsDOM)
        
        // สำหรับการดึงค่า value ออกมา
        for (let i = 0; i < inputsDOM.length; i++) {
            console.log(inputsDOM[i].value)
        }
    </script>
</body>
```

**result**

![alt text](/img/select-class.png)

### 3. querySelector จะหยิบตัวเดียว
- ใช้ไอเดีย CSS
- select ได้ 3 แบบ
    - selet ไปที่ id (#) 
    ```html
    <body>
    first name: <input class="input" id="firstname" type="text" name="firstname" value="ทดสอบ">
    
    <script>
        let firstnameDOM = document.querySelector('#firstname')
        
        // สำหรับการดึงค่า value ออกมา
        console.log(firstnameDOM.value)
    </script>
    </body>
    ```
    ------

    - selet ไปที่ class (.) จะไม่ออกมาเป็น arry เหมือน ```getElementByClassname```
    ```html
    <body>
    first name: <input class="input" id="firstname" type="text" name="firstname" value="ทดสอบ">
    
    <script>
        let firstnameDOM = document.querySelector('.input')
        
        // สำหรับการดึงค่า value ออกมา
        console.log(firstnameDOM.value)
    </script>
    </body>
    ```
    ------

    - selet ไปที่ tag  ชื่อ tag[attribute name] ```.querySelector('input[name=firstname]')```

    **result(1-3)**
    - จะเห็นว่าทั้ง 3 แบบได้ output เหมือนกัน
    
    ![alt text](/img/query.png)


### 4. querySelectorAll เหมือน querySelecto 
- แต่จะหยิบหลายตัว และผลลัพธ์จะออกมาเป็น arry
```html
interst:
    <input class="input" type="checkbox" name="interst" value="book"> book
    <input class="input" type="checkbox" name="interst" value="code"> code
    <input class="input" type="checkbox" name="interst" value="JS"> JS

    <script>
        //ได้ arr มาเก็บที่ checkboxDOM
        let checkboxDOM = document.querySelectorAll('input[name=interst]')

        // สำหรับการดึงค่า value ออกมา
        for (let i = 0; i < checkboxDOM.length; i++) {
            console.log('checkbox value', checkboxDOM[i].value)
        }
    </script>
```
**result**

![alt text](/img/queryAll.png)

## Javascript Event
เป็นการทำให้ html ส่ง Event ไปยัง javascript

### 1. onclick 
* การดักจับ event เมื่อ user มีการคลิกที่ element ใน htm

**stepe**
1. ใส่ ``` onclick="userClick()"``` ใน DOM ที่ต้องการดัก
2. ไปสร้าง function ที่ js ให้ชื่อเหมือนกัน ```userClick()```

```html
    <button onclick="userClick()">ทดลองกด</button>
    
    <script>
        // สร้าง function สำหรับการรับ Event ชื่อ userClick และ function นี้จะถูกเรียกเมื่อ onclick ทำงาน
        function userClick() {
            console.log('user clicked')
        }
    </script>
```
----

### 2. onchange
* การดักจับเมื่อ input มีการเปลี่ยนแปลงค่า (ปกติใช้ได้กับ input อย่าง ```text```, ```radio```, ```checkbox```)
* radio ต้องใช้ name เดียวกันไม่งั้นจะเลือกได้ > ค่า ซึ่งผิดหลัก ```radio```

**stepe** เหมือน onclick

**ตัวอย่าง** การใช้ querySelectorAll กับ onChenge
```html
    <input type="radio" name="gender" value="male" onchange="changeGender()"> male
    <input type="radio" name="gender" value="female" onchange="changeGender()"> female

    <script>
        function changeGender() {
            let genderInputs = document.querySelectorAll('input[name=gender]')
            let gender = ''

            //ใช้ for เพื่อวนเข้าถึงข้อมูล เพราะ querySelectorAll จะได้ของออกมาเป็น array
            for (let index = 0; index < genderInputs.length; index++) {
                //if check ว่าใครถูกติ้ก ถ้าถูกติ้ก ก็จะเอาไปเก็บที่ gender
                if (genderInputs[index].checked) {
                    gender = genderInputs[index].value
                } 
            }

            console.log('selected gender', gender) //ดูค่า
        }
    </script>
```
-----

### 3. onkeydown, onkeyup, onkeypress
- onkeydown -> เมื่อ user กดลงบน keyboard (จังหวะกด)
- onkeyup -> เมื่อ user กดปล่อยมือจากปุ่ม keyboard (จังหวะปล่อยหลังกด) จะได้ค่าที่ update แล้ว
- onkeypress -> จังหวะที่ตัวอักษรถูกส่งออกมา (เกิดหลัง onkeydown, เกิดก่อน onkeyup)

**ตัวอย่าง** การใช้ 
```html
<body>
    first name <input type="text" name="firstname" onkeyup="changeFirstname()">
    <script>
        function changeFirstname() {
            //เข้าถึง input firstname
            let firstNameDom = document.querySelector('input[name = firstname]')
            //เอาค่า firstname ออกมา
            console.log('change first name:', firstNameDom.value)
        }
    </script>
</body>
```
------

### 4. onmouseover, onmouseup, onmousedown 
**ตัวอย่าง** การใช้ 
```html
    <div 
    onmouseover="overItem()"
    onmouseup="upItem()"
    onmousedown="dowItem()"
    >click</div>

    <script>
        function overItem() {
            console.log('mouse over')
        }

        function upItem() {
            console.log('mouse up')
        }

        function dowItem() {
            console.log('mouse dow')
        }

    </script>
```
----

### 5. addEventListener 
- เป็นอีกท่าของ event
- จะได้ผลลัพธ์เหมือน ```onclick``` เลือกใช้ตามที่ถนัด
```html
<button id="testbutton">ปุ่มที่ 1</button>
<button onclick="clickButton()">ปุ่มที่ 2</button>

<script>
document.getElementById('testbutton').addEventListener('click', function() {
  console.log('คลิกปุ่มที่ 1')
})
function clickButton () {
  console.log('คลิกปุ่มที่ 2')
}
</script>
```
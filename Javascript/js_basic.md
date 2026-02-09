# Basic Javascript
- doc พี่ไมค์ [ep.5](https://docs.mikelopster.dev/c/web101/chapter-5/intro)
- วิธี run (Test code) 
    - สร้างไฟล์ .js เช่น ```main.js```
    - run บน vscode เพื่อดู output ได้เลย

## 1. Variabel
### string
```js
let firstname = 'apin' 
```

### number
```js
let age = 20 
```

### bool
```js
let isThai = true
```

### object
- วิธีประกาศ obj ธรรมดา

    ```js
    let std = {
        age: 30,
        name: 'mike',
        grade: 'A'
    }
    ```

- วิธีประกาศ obj array

    ```js
    let std = [{
        age: 30,
        name: 'mike',
        grade: 'A'
    },{
        age: 20,
        name: 'mm',
        grade: 'B'
    }]
    ```

## 2. Operator
### operator +, -, *, /, %

```js
let num1 = 'test'
let num2 = 'num'

let num3 = num1 + num2 //+ ใช้ต่อ string 
console.log('new number is', num3)
```


### condition &&, ||, ! ใช้เหมือน c++

```js
let score = prompt('input your score') //input
console.log('your score ', score)      //output

if (score >= 80) {
    console.log('GRAD : A')
} else if (score >= 50) {
    console.log('GRAD : D')
} else {
    console.log('GRAD : F')
}
```

## 3. Loop

```js
console.log('------ while  loop -----')
let count1 = 0
while (count1 < 10) {
    console.log(count1)
    count1 = count1 + 1 
}

console.log('------ for loop -----')
for (let count2= 0; count2 < 10; count2++) {
    console.log(count2)
    
}
```

## 4.Array
มี function ไว้เรียกใช้งานเช่น
* push 
* pop
* sort     เรียงจาก น้อย-> มาก
* includes เช็คว่ามีสิ่งนั้นอยู่ในลิสหรือป่าว

```js
let ages = [22,20,24]

console.log('length of list:' ,ages.length)
for (let index = 0; index < ages.length; index++) {
    console.log(ages[index])
    
}
//ใช้แบบนี้ในการเข้าถึงง่ายกว่า ถ้าจะแค่ output
console.log(ages) 

```

**ตัวอย่าง** array.push()

```js
ages.push(28)
console.log(ages) 
```

**ตัวอย่าง** ages.pop()

```js
ages.pop()
console.log(ages)
```


**ตัวอย่าง** .ages.sort

```js
console.log('----- sort -----')
console.log(ages)
ages.sort()
console.log(ages)
```

**ตัวอย่าง**  ages.includes 

```js
if (ages.includes(22)) {
    console.log('you have 22 in list')
}
```

## 5. function มี 3 แบบ
### 5.1 function ปกติ
**ตัวอย่าง** function ปกติ

```js
function calculation(score) {
    
    if (score >= 80) {
        grade = 'A'
    } else if (score >= 50) {
        grade = 'D'
    } else {
        grade = 'F'
    }

    return grade
}

let score1 = 80
let score2 = 50

let grade1 = calculation(score1)
let grade2 = calculation(score2)

console.log('grade:', grade1 , grade2)
```

### 5.2 arrow function
คือ function ปกติ ที่เอามาเขียนในรูปย่อ จะเห็นความแตกต่างและตัวอย่างการใช้งานได้ชัดเจนขึ้นในหัวข้อที่ **6.Object**

**ตัวอย่าง** arrow function

```js
let calculation = (score) => {
    
    if (score >= 80) {
        grade = 'A'
    } else if (score >= 50) {
        grade = 'D'
    } else {
        grade = 'F'
    }

    return grade
}
```

### 5.3 parameter function
คือ functon ที่มี parametor เป็น function อีกที ในหัวข้อนี้จะแนะนำอีก 3 function ที่จะเอามาเป็นตัวอย่างการใช้ parameter function ได้แก่
* .map( ) -> เข้าถึงและทำอะไรบางอย่างกับค่าของ obj
* .forEach( ) -> เข้าถึง ใช้แทน for-loop
* .filter( ) -> จะ คืนค่า array ใหม่ ที่มีเฉพาะสมาชิกที่ตรงตามเงื่อนไข

**ตัวอย่าง** parameter function (.map() +.forEach( ))
```js
let score = [10,20,30,40]

for (let index = 0; index < score.length; index++) {
    console.log('score:', score[index])
    
}

//map 
score = score.map((s) => {
    return s * 2
})

//forEach
score.forEach((s) => {
    console.log('new score', s)
})
```
-------

**ตัวอย่าง** parameter function (.filter +.forEach( ))
```js
let score = [10,20,30,40]

for (let index = 0; index < score.length; index++) {
    console.log('score:', score[index])
    
}

let newScore = score.filter((s) =>{
    return s >= 30    //อันนีี้คือย่อของแบบล่าง ภ้า if เช็ค true false เขียนบรรทัดเดียวแบบนี้ได้
    /*if (s >= 30) {
        return true
    } else {
        return false
    }*/
})

newScore.forEach((i) => {
    console.log('new score:', i)
})
```

## 6.Object
### ทวนวิธีประกาศและ การเข้าถึง attribute ด้วย . (dot)
```js
let std = {
    age: 30,
    name: 'mike',
    grade: 'A'
}

console.log(std.age) 
console.log(std.name)
console.log(std.grade)
```

- ใช้การ loop เพื่อเข้าถึงหรือดู output
    ```js
    for (let index = 0; index < std.length; index++) {
        console.log('\nstd no.', (index+1))
        console.log('name :', std[index].name)
        console.log('age  :', std[index].age)
        console.log('grade:', std[index].grade)
        
    }
    ```

- ใช้ push, pop ได้เหมือน array
    ```js
    std.push({ 
        age:25,
        name: 'AA',
        grade: 'C'
    })
    ```
### นอกจากนี้ยังมี function ที่เอามาใช้จัดการกับ obj อีกเช่น
- find   หาว่ามีค่านั้นๆอยู่ใน obj ไหม

    **ตัวอย่าง** .find()
    ```js
    let stds = [
        {
            name: 'mike',
            score: 80,
            grade: 'A'
        },
        {
            name: 'AA',
            score: 50,
            grade: 'D' 
        }
    ]
    ```


* map    

    **ตัวอย่าง** .map()
    ```js
        let doubleScore = stds.map((s) => {
            s.score =  s.score * 2
            return s
        })
        console.log('double Score:', doubleScore)
    ```

* filter 

    **ตัวอย่าง** .filter ()
    ```js
    let hightScore = stds.filter((s) => {
        if(s.score >= 60){
            return true
        }
    })
    console.log('hight Score:', hightScore)
    ```
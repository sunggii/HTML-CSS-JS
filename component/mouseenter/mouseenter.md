# mouseenter
- mouse จะหนีไปเรื่อยๆตอนที่เอา cursor ไปจอ
![alt text](mouseenter.gif) 

## Code
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        #noBtn {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            transition: all 0.2s ease; /* ขยับลื่น */
        }
    </style>

</head>
<body>
    <button id="noBtn">no</button>

    <script>
        const noBtn = document.getElementById("noBtn");

        noBtn.addEventListener("mouseenter", () => {
            //getBoundingClientRect() เอาไว้คำนวณขนาดปุ่ม
            const btnRect = noBtn.getBoundingClientRect(); 

            const maxX = window.innerWidth - btnRect.width;
            const maxY = window.innerHeight - btnRect.height;

            const randomX = Math.random() * maxX;
            const randomY = Math.random() * maxY;

            noBtn.style.left = randomX + "px";
            noBtn.style.top = randomY + "px";
        });
    </script>

</body>
</html>
```
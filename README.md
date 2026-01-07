กดดูเลยย
<!DOCTYPE html>
<html lang="th">

<head>
    <meta charset="UTF-8">
    <title>เซอร์ไพรส์ของเธอ ❤️</title>

    <style>
        body {
            margin: 0;
            height: 100vh;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', sans-serif;
            color: #fff;
            text-align: center;
            overflow: hidden;
        }
        /* ================= FLOAT HEART BACKGROUND ================= */
        
        .hearts-bg {
            position: fixed;
            inset: 0;
            overflow: hidden;
            z-index: 1;
        }
        
        .floating-heart {
            position: absolute;
            width: 26px;
            height: 26px;
            background: rgba(255, 255, 255, 0.9);
            transform: rotate(45deg);
            animation: floatUp linear infinite;
        }
        
        .floating-heart::before,
        .floating-heart::after {
            content: "";
            position: absolute;
            width: 26px;
            height: 26px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 50%;
        }
        
        .floating-heart::before {
            top: -13px;
            left: 0;
        }
        
        .floating-heart::after {
            left: -13px;
            top: 0;
        }
        
        @keyframes floatUp {
            from {
                transform: translateY(110vh) rotate(45deg);
                opacity: 1;
            }
            to {
                transform: translateY(-120px) rotate(45deg);
                opacity: 0;
            }
        }
        /* ================= HEART FALL ================= */
        
        .falling-heart {
            position: fixed;
            top: -50px;
            font-size: 2em;
            animation: fall 2.5s linear forwards;
            z-index: 4;
        }
        
        @keyframes fall {
            to {
                transform: translateY(110vh);
            }
        }
        /* ================= CARD ================= */
        
        .card {
            position: relative;
            z-index: 2;
            background: rgba(255, 255, 255, 0.25);
            padding: 30px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            max-width: 420px;
            width: 90%;
            backdrop-filter: blur(6px);
        }
        
        .page {
            display: none;
        }
        
        .display {
            font-size: 1.8em;
            letter-spacing: 8px;
        }
        
        .keypad {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-top: 15px;
        }
        
        button {
            padding: 15px;
            border-radius: 15px;
            border: none;
            background: #ff6f91;
            color: white;
            font-size: 1.2em;
            cursor: pointer;
        }
        
        button:hover {
            background: #ff4f7a;
        }
        
        .heart {
            font-size: 3em;
            animation: beat 1s infinite;
            cursor: pointer;
        }
        
        @keyframes beat {
            0%,
            100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }
        /* ================= LETTER ================= */
        
        .letter-overlay {
            position: fixed;
            inset: 0;
            background: rgba(255, 105, 135, 0.95);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 5;
        }
        
        .letter {
            background: white;
            color: #ff4f7a;
            padding: 30px;
            border-radius: 20px;
            width: 280px;
            cursor: pointer;
            animation: pop 0.6s ease;
        }
        
        @keyframes pop {
            from {
                transform: scale(0);
            }
            to {
                transform: scale(1);
            }
        }
    </style>
</head>

<body>

    <div class="hearts-bg"></div>

    <!-- LOGIN -->
    <div class="card" id="login">
        <h1>🔐 ใส่รหัสลับ</h1>
        <p>กดตัวเลขที่เธอรู้ดีที่สุด 💕</p>
        <div class="display" id="display">________</div>

        <div class="keypad">
            <button onclick="press(1)">1</button>
            <button onclick="press(2)">2</button>
            <button onclick="press(3)">3</button>
            <button onclick="press(4)">4</button>
            <button onclick="press(5)">5</button>
            <button onclick="press(6)">6</button>
            <button onclick="press(7)">7</button>
            <button onclick="press(8)">8</button>
            <button onclick="press(9)">9</button>
            <button onclick="clearCode()">⌫</button>
            <button onclick="press(0)">0</button>
            <button onclick="check()">✔</button>
        </div>
    </div>

    <!-- PAGES -->
    <div class="card page" id="page1">
        <h1>หน้า 1 💖</h1>
        <p>ขอบคุณที่เข้ามาเป็นความสุขของเค้า</p>
        <button onclick="next(2)">ถัดไป ➡️</button>
    </div>

    <div class="card page" id="page2">
        <h1>หน้า 2 🌷</h1>
        <p>ตั้งแต่วันที่ 8 สิงหา 2567<br>หัวใจเค้าก็มีแค่เธอ</p>
        <button onclick="next(3)">ถัดไป ➡️</button>
    </div>

    <div class="card page" id="page3">
        <h1>หน้า 3 ✨</h1>
        <p>ไม่ว่าจะวันดีหรือวันร้าย<br>เค้าก็ยังจับมือเธอไว้</p>
        <button onclick="next(4)">ถัดไป ➡️</button>
    </div>

    <div class="card page" id="page4">
        <h1>หน้า 4 💞</h1>
        <p>เราคบกันมาเกินหนึ่งปีแล้ว<br>และเค้าอยากให้นานกว่านี้</p>
        <button onclick="next(5)">ถัดไป ➡️</button>
    </div>

    <div class="card page" id="page5">
        <h1>หน้า 5 ❤️</h1>
        <p>เค้ารักเธอมากนะ</p>
        <div class="heart" onclick="heartRain()">❤️</div>
    </div>

    <!-- LETTER -->
    <div class="letter-overlay" id="letterBox">
        <div class="letter" onclick="openLetter()">
            <h2>💌 จดหมาย</h2>
            <p>กดเพื่อเปิด</p>
        </div>
    </div>

    <script>
        /* BACKGROUND HEART */
        setInterval(() => {
            const h = document.createElement("div");
            h.className = "floating-heart";
            h.style.left = Math.random() * 100 + "vw";
            h.style.animationDuration = (5 + Math.random() * 5) + "s";
            document.querySelector(".hearts-bg").appendChild(h);
            setTimeout(() => h.remove(), 10000);
        }, 400);

        /* PASSWORD */
        const correctCode = "08082567";
        let input = "";

        function press(n) {
            if (input.length < 8) {
                input += n;
                update();
            }
        }

        function clearCode() {
            input = input.slice(0, -1);
            update();
        }

        function update() {
            display.innerText = "•".repeat(input.length) + "_".repeat(8 - input.length);
        }

        function check() {
            if (input === correctCode) {
                login.style.display = "none";
                page1.style.display = "block";
            } else {
                alert("รหัสไม่ถูกนะ 💔");
                input = "";
                update();
            }
        }

        function next(n) {
            document.querySelectorAll(".page").forEach(p => p.style.display = "none");
            document.getElementById("page" + n).style.display = "block";
        }

        /* HEART RAIN + LETTER */
        function heartRain() {
            for (let i = 0; i < 120; i++) {
                const h = document.createElement("div");
                h.className = "falling-heart";
                h.innerText = "❤️";
                h.style.left = Math.random() * 100 + "vw";
                h.style.animationDelay = Math.random() * 1.5 + "s";
                document.body.appendChild(h);
                setTimeout(() => h.remove(), 3000);
            }
            setTimeout(() => letterBox.style.display = "flex", 2500);
        }

        function openLetter() {
            document.querySelector(".letter").innerHTML =
                "<h2>💖</h2><p style='font-size:1.2em'>ดูตอรี่ใน IG น้าาา💌</p>";
        }
    </script>

</body>

</html>

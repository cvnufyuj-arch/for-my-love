<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Special Story ❤️</title>
    <style>
        body { font-family: 'Helvetica Neue', sans-serif; background: #fff5f5; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; overflow: hidden; }
        .container { text-align: center; background: white; padding: 30px; border-radius: 25px; box-shadow: 0 15px 30px rgba(255, 182, 193, 0.3); width: 85%; max-width: 400px; min-height: 350px; display: flex; flex-direction: column; justify-content: center; align-items: center; transition: all 0.5s ease; position: relative; }
        h1 { color: #ff4d6d; font-size: 22px; margin-bottom: 10px; font-weight: 600; }
        p { font-size: 15px; color: #666; line-height: 1.6; }
        .page { display: none; width: 100%; animation: fadeIn 0.8s ease forwards; }
        .active { display: block; }
        .buttons { margin-top: 25px; display: flex; justify-content: center; gap: 15px; position: relative; height: 50px; width: 100%; }
        button { padding: 12px 28px; font-size: 16px; border: none; border-radius: 25px; cursor: pointer; font-weight: bold; transition: all 0.3s ease; box-shadow: 0 5px 10px rgba(0,0,0,0.05); }
        button:active { transform: scale(0.95); }
        .btn-pink { background: linear-gradient(135deg, #ff4d6d, #ff758f); color: white; }
        .btn-gray { background: #f7f7f7; color: #555; border: 1px solid #eee; }
        #noBtn { background: #999; color: white; position: absolute; }
        .typewriter { text-align: left; background: #fffafb; padding: 20px; border-radius: 15px; border-left: 5px solid #ff4d6d; min-height: 120px; margin-top: 15px; font-size: 15px; color: #444; box-shadow: inset 0 2px 5px rgba(0,0,0,0.02); }
        .gift-box { font-size: 75px; cursor: pointer; margin: 20px 0; transition: transform 0.3s; animation: float 3s ease-in-out infinite; }
        .heart-badge { font-size: 65px; margin: 15px; animation: pulse 2s infinite; }
        .days-counter { font-size: 32px; font-weight: bold; color: #ff4d6d; margin: 15px 0; background: #fff5f5; padding: 10px 20px; border-radius: 15px; display: inline-block; }
        
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
        @keyframes pulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.08); } }
        @keyframes fall { to { transform: translateY(105vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>
    <div class="container">
        <!-- หน้า 1: ด่านเปิดตัวชวนลุ้น -->
        <div id="page1" class="page active">
            <div class="heart-badge">💌</div>
            <h1>เค้ามีอะไรจะบอกแหละ...</h1>
            <p>แอบทำสิ่งนี้ตั้งนานเพื่อเธอคนเดียวเลยนะ ลองกดดูสิ</p>
            <button class="btn-pink" style="margin-top: 20px; width: 100%;" onclick="nextPage(2)">เปิดอ่านจดหมาย ➔</button>
        </div>

        <!-- หน้า 2: ด่านปุ่มวิ่งหนีพิสูจน์รัก -->
        <div id="page2" class="page">
            <h1>ถามจริง ๆ วันนี้รักเค้าไหม? 🥰</h1>
            <div class="buttons">
                <button class="btn-pink" onclick="nextPage(3)">รักที่สุดเลย</button>
                <button id="noBtn" onmouseover="moveButton()" onclick="moveButton()">ไม่รักแล้ว</button>
            </div>
        </div>

        <!-- หน้า 3: หน้ากวน ๆ ล้อเลียน -->
        <div id="page3" class="page">
            <div class="heart-badge">😜</div>
            <h1>เย้! รู้อยู่แล้วว่าต้องตอบข้อนี้</h1>
            <p>เพราะปุ่มนู้นเค้าตั้งค่าไม่ให้กดไงล่ะ ฮ่า ๆ แฟนใครเนี่ยน่ารักจัง</p>
            <button class="btn-pink" style="margin-top: 20px; width: 100%;" onclick="nextPage(4)">ไปด่านต่อไปกัน ➔</button>
        </div>

        <!-- หน้า 4: ด่านคำถามวัดใจคู่รัก -->
        <div id="page4" class="page">
            <h1>คำถามวัดใจ: ใครดื้อกว่ากัน? 🤔</h1>
            <p id="quizHint" style="color:#999;">(ตอบให้ถูกต้องน้าถึงจะผ่านด่านได้)</p>
            <div class="buttons" style="flex-direction: column; height: auto; gap: 10px;">
                <button class="btn-gray" onclick="alert('มั่วแล้ววว เค้าออกจะเรียบร้อย คิดใหม่ ๆ 😜')">แฟนดื้อ (ตัวเธอเอง)</button>
                <button class="btn-pink" onclick="document.getElementById('quizHint').innerText='ถูกต้องที่สุด! คุณนั่นแหละดื้อ 🏆'; document.getElementById('to5').style.display='block';">เค้าดื้อเอง (ตัวลูกค้าเอง)</button>
            </div>
            <button class="btn-pink" id="to5" style="display:none; margin-top:20px; width: 100%;" onclick="nextPage(5)">ผ่านด่านแล้ว! ไปต่อ ➡️</button>
        </div>

        <!-- หน้า 5: หน้านับวันครบรอบ (จุดขายทำเงิน) -->
        <div id="page5" class="page">
            <h1>เวลาที่เราเดินร่วมกันมา ⏳</h1>
            <div class="days-counter">365 วัน</div>
            <p>ขอบคุณทุกช่วงเวลาดี ๆ ที่มีให้กันตั้งแต่วันแรกจนถึงวันนี้นะ</p>
            <button class="btn-pink" style="margin-top: 20px; width: 100%;" onclick="nextPage(6)">อ่านความในใจต่อ ➔</button>
        </div>

        <!-- หน้า 6: จดหมายรักพิมพ์ดีดอัตโนมัติ -->
        <div id="page6" class="page">
            <h1>ความในใจจากก้นบึ้งของหัวใจ ✍️</h1>
            <div class="typewriter" id="secretLetter"></div>
            <button class="btn-pink" id="to7" style="display:none; margin-top:20px; width: 100%;" onclick="nextPage(7)">ไปหน้าถัดไปกัน 💖</button>
        </div>

        <!-- หน้า 7: สไลด์ความทรงจำหัวใจเด้ง -->
        <div id="page7" class="page">
            <h1>กล่องความทรงจำของเรา 📸</h1>
            <div style="font-size: 65px; margin: 20px 0; cursor: pointer;" onclick="popHeart()">👩‍❤️‍👨</div>
            <p>จิ้มที่อีโมจิรูปคู่รัว ๆ สิ มีหัวใจซ่อนอยู่ด้วยนะ</p>
            <button class="btn-pink" style="margin-top:20px; width:100%;" onclick="nextPage(8)">ด่านสุดท้ายแล้ว 🎁</button>
        </div>

        <!-- หน้า 8: กล่องของขวัญและเอฟเฟกต์พลุหัวใจ -->
        <div id="page8" class="page">
            <h1>จิ้มเปิดกล่องของขวัญชิ้นสุดท้ายสิ! 🎉</h1>
            <div class="gift-box" id="gift" onclick="openGift()">🎁</div>
            <div id="surpriseText" style="display:none;">
                <h2 style="color: #ff4d6d; margin: 10px 0; font-size: 24px;">Happy Anniversary นะงับ ❤️</h2>
                <p>อยู่เป็นรอยยิ้ม รอยดื้อ และเป็นความสุขของกันและกันแบบนี้ไปนาน ๆ เลยนะคนเก่ง ✨</p>
                <div style="font-size: 40px; margin-top: 15px;">💕👑🎂🥂🎁</div>
            </div>
        </div>
    </div>

    <script>
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            const randomX = Math.floor(Math.random() * 140) - 70;
            const randomY = Math.floor(Math.random() * 100) - 50;
            noBtn.style.left = `calc(50% - 45px + ${randomX}px)`;
            noBtn.style.top = `${randomY}px`;
        }
        function nextPage(pageNum) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(`page${pageNum}`).classList.add('active');
            if(pageNum === 6) startTyping();
        }
        const textToType = "ขอบคุณสำหรับทุก ๆ วันที่ผ่านมาเลยนะ การมีเธออยู่ในชีวิตมันเป็นเรื่องที่ดีที่สุดในโลกเลย ขอบคุณที่คอยดูแล เอาใจใส่ และน่ารักกับเค้าเสมอมานะ อยากบอกว่ารักเธอมาก ๆ และจะรักเพิ่มขึ้นในทุก ๆ วันเลยนะคนดีของเค้า ❤️";
        let index = 0;
        function startTyping() {
            if (index < textToType.length) {
                document.getElementById("secretLetter").innerHTML += textToType.charAt(index);
                index++;
                setTimeout(startTyping, 55);
            } else {
                document.getElementById("to7").style.display = "inline-block";
            }
        }
        function popHeart() {
            for (let i = 0; i < 6; i++) {
                const heart = document.createElement('div');
                heart.innerText = '💖';
                heart.style.position = 'fixed';
                heart.style.left = (Math.random() * 50 + 25) + 'vw';
                heart.style.top = '50vh';
                heart.style.fontSize = '30px';
                heart.style.animation = `fall 1.5s linear forwards`;
                document.body.appendChild(heart);
            }
        }
        function openGift() {
            document.getElementById("gift").innerText = "🔓💝";
            document.getElementById("gift").style.animation = "none";
            document.getElementById("surpriseText").style.display = "block";
            for (let i = 0; i < 60; i++) {
                const heart = document.createElement('div');
                heart.innerText = '❤️';
                heart.style.position = 'fixed';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.top = '-5vh';
                heart.style.fontSize = Math.random() * 20 + 15 + 'px';
                heart.style.animation = `fall ${Math.random() * 2 + 2}s linear forwards`;
                document.body.appendChild(heart);
            }
        }
    </script>
</body>
</html>

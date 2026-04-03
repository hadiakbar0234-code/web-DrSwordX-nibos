<!DOCTYPE html>
<html lang="id">
 <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Aesthetic</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f0f23, #1a1a2e);
            color: #ffffff;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }
        .container {
            text-align: center;
            max-width: 600px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        h2 {
            color: #4ecdc4;
            margin-top: 20px;
        }
        p {
            font-size: 1.2em;
            margin: 10px 0;
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 15px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        button {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            border-radius: 25px;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            margin-top: 20px;
        }
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(99, 224, 255, 0.397);
        }
        .popup-overlay {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(2px);
            justify-content: center;
            align-items: center;
            z-index: 999;
        }
        .popup-box {
            background: rgba(15, 15, 35, 0.96);
            border-radius: 16px;
            padding: 24px;
            max-width: 90%;
            width: 360px;
            box-shadow: 0 14px 30px rgba(0,0,0,0.5);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.15);
        }
        .popup-box h3 {
            margin-top: 0;
            color: #4ecdc4;
        }
        .popup-box p {
            color: #fff;
            margin: 12px 0;
        }
        .popup-box button {
            margin-top: 10px;
            background: linear-gradient(45deg, #006eff, #0084ff);
        }
        .popup-overlay.active {
            display: flex;
        }
    </style>
 </head>
<body>
    <div class="container">
        <h2>Selamat Datang di Webku</h2>
        <h1>Halo Wak, Tes sikit lohya</h1>
        <p>ini adalah web tes buatanku</p>
        <img src="gambartes.jpg" alt="Gambar Tes">
        <button id="popupBtn">Klik Gw</button>
        <p>keren kan?</p>
    </div>
    <div id="popup" class="popup-overlay" role="dialog" aria-modal="true" aria-labelledby="popupTitle">
        <div class="popup-box">
            <h3 id="popupTitle">Halo Wak!</h3>
            <p>ndada apa-apa disini!</p>
            <div style="margin: 12px 0; color: #ffffff; font-size: 1.4em;">Skor: <span id="scoreValue">0</span></div>
            <button id="popBtn" style="background: linear-gradient(45deg, #6cc9ff, #7152ff); color: #0000008f;">pop</button>
            <button id="closePopup">Tutup</button>
        </div>
    </div>
    <script>
        const popupBtn = document.getElementById('popupBtn');
        const popup = document.getElementById('popup');
        const closePopup = document.getElementById('closePopup');
        const popBtn = document.getElementById('popBtn');
        const scoreValue = document.getElementById('scoreValue');
        let score = 0;

        popupBtn.addEventListener('click', () => {
            popup.classList.add('active');
        });

        popBtn.addEventListener('click', () => {
            score += 1;
            scoreValue.textContent = score;
        });

        closePopup.addEventListener('click', () => {
            popup.classList.remove('active');
        });

        popup.addEventListener('click', (event) => {
            if (event.target === popup) {
                popup.classList.remove('active');
            }
        });

        document.addEventListener('keydown', (event) => {
            if (event.key === 'Escape') {
                popup.classList.remove('active');
            }
        });
    </script>
 </body>
 </html>

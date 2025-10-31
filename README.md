<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Selamat Ulang Tahun 💖</title>

  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: radial-gradient(circle at top, #ffe3e3, #ffafbd);
      overflow: hidden;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      color: #4d2d2d;
      transition: opacity 0.8s ease; /* efek transisi */
    }

    body.fade-out {
      opacity: 0;
    }

    h1 {
      font-family: 'Dancing Script', cursive;
      font-size: 3em;
      color: #ff4b5c;
      opacity: 0;
      animation: slideIn 2.5s ease forwards 0.5s;
    }

    p {
      font-size: 1.2em;
      margin-top: 10px;
      opacity: 0;
      animation: fadeInText 2s ease forwards 2.5s;
    }

    button {
      margin-top: 40px;
      padding: 12px 24px;
      font-size: 1.1em;
      border: none;
      border-radius: 25px;
      background: #ff758c;
      color: white;
      cursor: pointer;
      opacity: 0;
      animation: fadeInText 2s ease forwards 4s;
      transition: 0.3s;
    }

    button:hover { background: #ff4b5c; transform: scale(1.05); }

    @keyframes slideIn {
      0% { transform: translateY(-40px); opacity: 0; }
      100% { transform: translateY(0); opacity: 1; }
    }

    @keyframes fadeInText {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .heart {
      position: absolute;
      color: rgba(255, 255, 255, 0.8);
      font-size: 20px;
      animation: float 6s linear infinite;
    }

    @keyframes float {
      0% { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <div>
    <h1>🎂 Selamat Ulang Tahun 🎂</h1>
    <p>Hari ini adalah hari spesial untukmu, Ippang Turner 💞</p>
    <button onclick="lanjut()">Buka Surat 🎁</button>
  </div>

  <!-- Musik lembut -->
  <audio id="music" src="https://cdn.pixabay.com/download/audio/2023/02/21/audio_b03cb67c9a.mp3?filename=romantic-piano-ambient-139542.mp3" autoplay loop></audio>

  <script>
    // Efek hati melayang
    function buatHati() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.textContent = '💖';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = 3 + Math.random() * 4 + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }
    setInterval(buatHati, 300);

    // Fungsi transisi ke surat
    function lanjut() {
      document.body.classList.add('fade-out');
      setTimeout(() => {
        window.location.href = 'surat.html';
      }, 800); // waktu tunggu sebelum pindah (0.8 detik)
    }
  </script>
</body>
</html>

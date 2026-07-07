# bubub
ucapan semoga lekas sembuh 
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cepat Sembuh, Bubub Sayang ❤️</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      background: linear-gradient(to bottom, #ffe5ec, #ffc2d1);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      position: relative;
    }
    /* Efek Hujan Hati */
    .heart-fall {
      position: absolute;
      color: #ff4d6d;
      font-size: 20px;
      animation: fall linear forwards;
      z-index: 1;
      user-select: none;
    }
    @keyframes fall {
      0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }
    /* Kotak Pesan */
    .container {
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(10px);
      padding: 30px;
      border-radius: 25px;
      box-shadow: 0 15px 35px rgba(255, 77, 109, 0.2);
      text-align: center;
      max-width: 450px;
      width: 90%;
      z-index: 10;
      border: 2px solid #fff;
      transition: all 0.5s ease;
    }
    .foto-container {
      width: 120px;
      height: 120px;
      margin: 0 auto 20px;
      border-radius: 50%;
      border: 4px solid #ff4d6d;
      overflow: hidden;
      background: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 50px;
    }
    h1 {
      color: #ff4d6d;
      font-size: 24px;
      margin-bottom: 15px;
    }
    .typing-text {
      color: #4a4a4a;
      font-size: 16px;
      line-height: 1.6;
      min-height: 80px;
      margin-bottom: 25px;
      font-weight: 500;
    }
    /* Tombol Interaktif */
    .btn-container {
      display: flex;
      justify-content: center;
      gap: 15px;
      position: relative;
      height: 50px;
    }
    .btn {
      padding: 12px 28px;
      border: none;
      border-radius: 50px;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }
    .btn-yes {
      background: linear-gradient(135deg, #ff4d6d, #ff758f);
      color: white;
    }
    .btn-yes:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(255, 77, 109, 0.4);
    }
    .btn-no {
      background: #a3b18a;
      color: white;
      position: absolute;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="foto-container" id="emoticon">
      🥺
    </div>
    
    <h1 id="headline">GWS Bubub Kesayanganku... 💕</h1>
    
    <!-- Teks otomatis mengetik khusus Bubub -->
    <div class="typing-text" id="text-space"></div>

    <div class="btn-container">
      <button class="btn btn-yes" onclick="sembuh()">Udah Enakan Kok!</button>
      <button class="btn btn-no" id="btnNo" onmouseover="hindari()" onclick="hindari()">Masih Lemas Badannya 🥺</button>
    </div>
  </div>

  <script>
    // Konfigurasi Pesan Berjalan Khusus Panggilan Bubub
    const pesan = [
      "Bubub... Aku sedih banget pas tahu Bubub lagi lemas dan sakit hari ini. 🥺",
      "Rasanya pengen ada di samping Bubub terus buat jagain sama ngusap kepalanya.",
      "Jangan lupa diminum ya obatnya, jangan bandel, dan harus istirahat total pokoknya!",
      "Aku kangen banget sama tawa manja dan senyuman manisnya Bubub.",
      "Semoga cepat pulih ya kesayanganku tercinta! Kalau udah baikan, klik tombol di bawah ya ❤️"
    ];

    let barisIndex = 0;
    let hurufIndex = 0;
    const space = document.getElementById("text-space");

    function ketikTeks() {
      if (barisIndex < pesan.length) {
        if (hurufIndex < pesan[barisIndex].length) {
          space.innerHTML += pesan[barisIndex].charAt(hurufIndex);
          hurufIndex++;
          setTimeout(ketikTeks, 40);
        } else {
          setTimeout(() => {
            space.innerHTML = "";
            hurufIndex = 0;
            barisIndex++;
            if(barisIndex === pesan.length) {
              space.innerHTML = pesan[pesan.length - 1];
            } else {
              ketikTeks();
            }
          }, 2500);
        }
      }
    }

    window.onload = function() {
      ketikTeks();
      setInterval(buatHati, 300);
    };

    function hindari() {
      const btnNo = document.getElementById('btnNo');
      const x = Math.random() * (window.innerWidth - 150);
      const y = Math.random() * (window.innerHeight - 80);
      
      btnNo.style.position = 'fixed';
      btnNo.style.left = x + 'px';
      btnNo.style.top = y + 'px';
    }

    // Aksi saat klik tombol sembuh
    function sembuh() {
      document.getElementById('emoticon').innerHTML = "🥰";
      document.getElementById('headline').innerHTML = "Alhamdulillah, Sayangnya Aku! 💕";
      space.innerHTML = "Makasih ya Bubub udah kuat lawan sakitnya demi aku. Habis ini kabari aku ya, kita *deep talk* atau *video call* sepuasnya. I love you so much, Bubub! ❤️";
      document.querySelector('.btn-container').style.display = 'none';
    }

    function buatHati() {
      const heart = document.createElement('div');
      heart.classList.add('heart-fall');
      heart.innerText = ['❤️','💖','🧸','✨'][Math.floor(Math.random() * 4)];
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 3 + 2 + "s";
      heart.style.fontSize = Math.random() * 15 + 15 + "px";
      document.body.appendChild(heart);
      
      setTimeout(() => { heart.remove(); }, 5000);
    }
  </script>
</body>
</html>

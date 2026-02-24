<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>Für Jess ❤️</title>
  <style>
    body {
      margin: 0;
      background: #b3e5fc;
      overflow: hidden;
      font-family: Arial, sans-serif;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    h1 {
      color: white;
      margin-top: 30px;
      font-size: 50px;
    }

    /* Otter als Emoji */
    .otter {
      position: absolute;
      font-size: 80px;
      cursor: pointer;
      animation: float 3s ease-in-out infinite, flyIn 1.5s forwards;
      user-select: none;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
      100% { transform: translateY(0); }
    }

    @keyframes flyIn {
      from { transform: translateY(-150px) scale(0.5); opacity: 0; }
      to { transform: translateY(0) scale(1); opacity: 1; }
    }

    .shake {
      animation: shake 0.5s;
    }
    @keyframes shake {
      0% { transform: rotate(0deg); }
      25% { transform: rotate(10deg); }
      50% { transform: rotate(-10deg); }
      75% { transform: rotate(10deg); }
      100% { transform: rotate(0deg); }
    }

    #message {
      display: none;
      font-size: 42px;
      color: #ff4d6d;
      margin-top: 80px;
      animation: glow 1.5s infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px white; }
      to { text-shadow: 0 0 25px pink; }
    }

    .heart {
      position: absolute;
      color: red;
      font-size: 24px;
      animation: fall 3s linear forwards;
    }

    @keyframes fall {
      to { transform: translateY(100vh); opacity: 0; }
    }
  </style>
</head>

<body>

  <h1>Klicke alle Otter 🦦</h1>

  <!-- 2 Otter Emojis -->
  <div class="otter" style="top:80px; left:100px;" onclick="clickOtter(this)">🦦</div>
  <div class="otter" style="top:200px; left:300px;" onclick="clickOtter(this)">🦦</div>

  <div id="message">Jess ich liebe dich über alles! ❤️❤️❤️</div>

  <script>
    let count = 0;

    function clickOtter(otter) {
      // Wackeln beim Klick
      otter.classList.add('shake');
      setTimeout(() => otter.style.display = 'none', 500);

      // Herz-Explosion
      for (let i = 0; i < 2; i++) {
        let heart = document.createElement("div");
        heart.innerHTML = "❤️";
        heart.className = "heart";
        heart.style.left = otter.offsetLeft + "px";
        heart.style.top = otter.offsetTop + "px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 3000);
      }

      count++;
      if (count === 2) {
        document.getElementById("message").style.display = "block";
        setTimeout(() => {
          document.body.style.background = "#ffc0cb";
          heartRain();
        }, 1200);
      }
    }

    function heartRain() {
      setInterval(() => {
        let heart = document.createElement("div");
        heart.innerHTML = "❤️";
        heart.className = "heart";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = "-20px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 3000);
      }, 200);
    }
  </script>

</body>
</html>
# Sykrx.github1.io

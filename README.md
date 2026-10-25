

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday!</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ff758c, #ff7eb3, #a18cd1);
      color: white;
      text-align: center;
    }

    .card {
      width: 90%;
      max-width: 450px;
      padding: 35px 20px;
      border-radius: 25px;
      background: rgba(255, 255, 255, 0.17);
      border: 1px solid rgba(255, 255, 255, 0.4);
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
      backdrop-filter: blur(10px);
      animation: appear 1.5s ease;
      z-index: 2;
    }

    h1 {
      font-size: clamp(2rem, 8vw, 3rem);
      margin-bottom: 15px;
      text-shadow: 2px 3px 10px #ff4d6d;
      animation: glow 2s infinite alternate;
    }

    .cake {
      font-size: 90px;
      margin: 15px 0;
      animation: bounce 1.5s infinite;
    }

    p {
      font-size: 18px;
      line-height: 1.7;
      margin: 12px 0;
    }

    .name {
      color: #fff176;
      font-weight: bold;
    }

    button {
      margin-top: 20px;
      padding: 13px 25px;
      border: none;
      border-radius: 30px;
      background: #fff;
      color: #e84373;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: transform 0.3s;
    }

    button:hover {
      transform: scale(1.08);
    }

    #surprise {
      margin-top: 20px;
      font-size: 20px;
      font-weight: bold;
    }

    .balloon {
      position: absolute;
      bottom: -150px;
      font-size: 45px;
      animation: floatUp 8s linear infinite;
      z-index: 1;
    }

    .balloon:nth-child(1) { left: 5%; animation-delay: 0s; }
    .balloon:nth-child(2) { left: 25%; animation-delay: 2s; }
    .balloon:nth-child(3) { left: 70%; animation-delay: 1s; }
    .balloon:nth-child(4) { left: 90%; animation-delay: 3s; }

    @keyframes floatUp {
      from { transform: translateY(0) rotate(0deg); }
      to { transform: translateY(-120vh) rotate(25deg); }
    }

    @keyframes bounce {
      50% { transform: translateY(-12px); }
    }

    @keyframes glow {
      from { text-shadow: 0 0 8px #fff; }
      to { text-shadow: 0 0 25px #fff176; }
    }

    @keyframes appear {
      from { opacity: 0; transform: scale(0.7); }
      to { opacity: 1; transform: scale(1); }
    }
  </style>
</head>

<body>

  <div class="balloon">🎈</div>
  <div class="balloon">🎈</div>
  <div class="balloon">🎈</div>
  <div class="balloon">🎈</div>

  <div class="card">
    <h1>🎉 Happy Birthday! 🎉</h1>

    <p>Dear <span class="name">Your Name</span>,</p>

    <div class="cake">🎂</div>

    <p>
      Wishing you a day filled with love, laughter,
      happiness, and beautiful memories!
    </p>

    <p>
      May all your dreams come true and may your
      life shine brighter every day. 💖
    </p>

    <button onclick="showSurprise()">
      🎁 Click for a Surprise
    </button>

    <div id="surprise"></div>
  </div>

  <script>
    function showSurprise() {
      document.getElementById("surprise").innerHTML =
        "🥳 You are amazing! 💖<br>" +
        "May your birthday be magical! ✨🎉";

      // Create floating hearts
      for (let i = 0; i < 15; i++) {
        const heart = document.createElement("div");
        heart.innerHTML = "💖";
        heart.style.position = "absolute";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.bottom = "-40px";
        heart.style.fontSize = "25px";
        heart.style.transition = "transform 4s ease, opacity 4s";
        heart.style.zIndex = "3";
        document.body.appendChild(heart);

        requestAnimationFrame(() => {
          heart.style.transform =
            `translateY(-${window.innerHeight + 100}px) rotate(360deg)`;
          heart.style.opacity = "0";
        });

        setTimeout(() => heart.remove(), 4200);
      }
    }
  </script>

</body>
</html>
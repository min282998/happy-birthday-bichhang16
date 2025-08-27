# happy-birthday-bichhang16<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: radial-gradient(circle at center, #ffdde1, #ee9ca7);
      overflow: hidden;
      font-family: 'Arial', sans-serif;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }
    .message {
      position: absolute;
      top: 20%;
      width: 100%;
      text-align: center;
      font-size: 2em;
      font-weight: bold;
      color: white;
      opacity: 0;
      text-shadow: 0 0 10px #fff, 0 0 20px #ff00de, 0 0 30px #ff00de;
      animation: fadeInOut 12s linear infinite;
    }
    @keyframes fadeInOut {
      0%, 20% { opacity: 0; }
      25%, 45% { opacity: 1; }
      50%, 100% { opacity: 0; }
    }
    .gift {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 6em;
      opacity: 0;
      animation: giftAppear 12s linear infinite;
    }
    @keyframes giftAppear {
      0%, 70% { opacity: 0; transform: translate(-50%, -50%) scale(0.5) rotate(0deg); }
      75% { opacity: 1; transform: translate(-50%, -50%) scale(1.2) rotate(10deg); }
      80% { transform: translate(-50%, -50%) scale(1) rotate(-10deg); }
      85% { transform: translate(-50%, -50%) scale(1.3) rotate(0deg); }
      90% { opacity: 0; }
      100% { opacity: 0; }
    }
    .happy {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 4.5em;
      font-weight: bold;
      color: #fff;
      text-shadow: 0 0 20px #ff00de, 0 0 40px #00eaff, 0 0 60px #ff00de;
      opacity: 0;
      animation: happyAppear 12s linear infinite;
    }
    @keyframes happyAppear {
      0%, 85% { opacity: 0; transform: translate(-50%, -50%) scale(0.5); }
      90% { opacity: 1; transform: translate(-50%, -50%) scale(1.3); }
      95% { transform: translate(-50%, -50%) scale(1); }
      100% { opacity: 0; }
    }
    canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }
  </style>
</head>
<body>
  <div class="message" style="animation-delay:0s">Happy Birthday Bích Hằng</div>
  <div class="message" style="animation-delay:3s">Chúc mừng tuổi 16</div>
  <div class="message" style="animation-delay:6s">Ngày càng xinh đẹp</div>
  <div class="message" style="animation-delay:9s">Wishing You All The Best!</div>

  <div class="gift">🎁</div>
  <div class="happy">HAPPY BIRTHDAY 🎉</div>

  <canvas id="sparkles"></canvas>

  <script>
    const canvas = document.getElementById('sparkles');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    let sparkles = [];
    function random(min, max) { return Math.random() * (max - min) + min; }
    function createSparkle() {
      return {
        x: random(0, canvas.width),
        y: random(0, canvas.height),
        r: random(1, 3),
        dx: random(-0.5, 0.5),
        dy: random(-0.5, 0.5),
        opacity: random(0.5, 1)
      };
    }
    for (let i = 0; i < 100; i++) sparkles.push(createSparkle());
    function animate() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      sparkles.forEach(s => {
        ctx.beginPath();
        ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
        ctx.fillStyle = "rgba(255,255,255," + s.opacity + ")";
        ctx.fill();
        s.x += s.dx;
        s.y += s.dy;
        if (s.x < 0 || s.x > canvas.width || s.y < 0 || s.y > canvas.height) {
          s.x = random(0, canvas.width);
          s.y = random(0, canvas.height);
        }
      });
      requestAnimationFrame(animate);
    }
    animate();
    window.addEventListener("resize", () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    });
  </script>
</body>
</html>

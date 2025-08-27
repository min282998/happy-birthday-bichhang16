[index.html](https://github.com/user-attachments/files/22002043/index.html)
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Bích Hằng</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      background: radial-gradient(circle at center, #ffdde1, #ee9ca7, #ff6a88, #ff99ac);
      background-size: 400% 400%;
      animation: bgMove 15s ease infinite;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: white;
    }

    @keyframes bgMove {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    .message {
      position: absolute;
      font-size: 2.5em;
      font-weight: bold;
      text-align: center;
      opacity: 0;
      animation: fadeInOut 16s linear infinite;
    }

    @keyframes fadeInOut {
      0% {opacity: 0; transform: scale(0.8);}
      5% {opacity: 1; transform: scale(1);}
      20% {opacity: 1;}
      25% {opacity: 0;}
      100% {opacity: 0;}
    }

    .msg1 { animation-delay: 0s; }
    .msg2 { animation-delay: 4s; }
    .msg3 { animation-delay: 8s; }
    .msg4 { animation-delay: 12s; }

    /* Hộp quà */
    .gift {
      position: absolute;
      bottom: 20%;
      width: 100px;
      height: 100px;
      background: #ff477e;
      border-radius: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
      animation: shake 2s infinite;
      z-index: 2;
    }

    .gift:before {
      content: "";
      position: absolute;
      width: 20px;
      height: 100%;
      background: #ffd700;
    }
    .gift:after {
      content: "";
      position: absolute;
      height: 20px;
      width: 100%;
      background: #ffd700;
    }

    @keyframes shake {
      0%, 100% {transform: rotate(0deg);}
      25% {transform: rotate(3deg);}
      75% {transform: rotate(-3deg);}
    }

    /* Happy Birthday text */
    .big-text {
      position: absolute;
      font-size: 3.5em;
      font-weight: bold;
      text-align: center;
      top: 35%;
      opacity: 0;
      background: linear-gradient(270deg, #ff6ec4, #7873f5, #4ade80, #facc15, #f87171);
      background-size: 1000% 1000%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: bigText 16s infinite, gradient 10s ease infinite;
    }

    @keyframes gradient {
      0%{background-position:0% 50%}
      50%{background-position:100% 50%}
      100%{background-position:0% 50%}
    }

    @keyframes bigText {
      0%,60% {opacity: 0; transform: scale(0.5);}
      65% {opacity: 1; transform: scale(1.1);}
      70% {opacity: 1; transform: scale(1);}
      90% {opacity: 1;}
      100% {opacity: 0;}
    }

    /* LED rainbow tên người gửi */
    .signature {
      position: absolute;
      top: 10px;
      left: 10px;
      font-weight: bold;
      font-size: 1.2em;
      background: linear-gradient(90deg, red, orange, yellow, green, cyan, blue, violet);
      background-size: 400% 400%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: rainbow 5s linear infinite;
    }

    @keyframes rainbow {
      0% {background-position: 0%;}
      100% {background-position: 400%;}
    }

    /* Confetti */
    .confetti {
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      top: -10px;
      animation: fall 4s linear forwards;
    }

    @keyframes fall {
      0% {transform: translateY(0) rotate(0);}
      100% {transform: translateY(100vh) rotate(720deg);}
    }
  </style>
</head>
<body>
  <div class="message msg1">Happy Birthday Bích Hằng 🎂</div>
  <div class="message msg2">Chúc mừng tuổi 16 ✨</div>
  <div class="message msg3">Ngày càng xinh đẹp 🌸</div>
  <div class="message msg4">Wish you all the best 💖</div>

  <div class="gift"></div>
  <div class="big-text">🎉 Happy Birthday 🎉</div>
  <div class="signature">From: Hải Thành (Minazure)</div>

  <script>
    function createConfetti() {
      for(let i=0; i<40; i++) {
        let conf = document.createElement("div");
        conf.classList.add("confetti");
        document.body.appendChild(conf);
        conf.style.left = Math.random() * window.innerWidth + "px";
        conf.style.backgroundColor = ["#ff4d6d","#ffd93d","#6a4c93","#00bbf9","#00f5d4"][Math.floor(Math.random()*5)];
        conf.style.animationDuration = (Math.random()*3+2) + "s";
        setTimeout(()=>{conf.remove();},4000);
      }
    }

    setInterval(createConfetti,16000); // mỗi lần hộp quà nổ
  </script>
</body>
</html>

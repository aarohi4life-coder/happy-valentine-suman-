<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For Suman ❤️</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }
    body {
      height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      color: #fff;
    }
    .container {
      text-align: center;
      animation: fadeIn 2s ease;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.3rem;
      margin-bottom: 30px;
      line-height: 1.6;
    }
    .heart {
      font-size: 4rem;
      animation: beat 1s infinite;
      margin-bottom: 20px;
    }
    button {
      padding: 15px 30px;
      font-size: 1.1rem;
      border: none;
      border-radius: 30px;
      background: #fff;
      color: #ff4d6d;
      cursor: pointer;
      transition: 0.3s ease;
      margin: 10px;
    }
    button:hover {
      transform: scale(1.1);
    }
    #noBtn {
      position: absolute;
    }
    .hidden {
      display: none;
    }
    @keyframes beat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.2); }
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .final {
      font-size: 2.2rem;
      animation: fadeIn 2s ease;
    }
    .floating-hearts span {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: float 6s linear infinite;
    }
    @keyframes float {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(-100vh); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="floating-hearts"></div>

  <div class="container" id="step1">
    <div class="heart">❤️</div>
    <h1>Hey Suman</h1>
    <p>
      From the moment you came into my life,<br />
      everything became softer, warmer, and more beautiful.
    </p>
    <button onclick="nextStep()">Continue 💖</button>
  </div>

  <div class="container hidden" id="step2">
    <h1>Suman, listen carefully…</h1>
    <p>
      I don’t promise perfection,<br />
      but I promise honesty, effort, and a heart that chooses you every single day.
    </p>
    <button onclick="nextStep2()">One Last Thing 💌</button>
  </div>

  <div class="container hidden" id="step3">
    <h1>Will you be mine forever? 💍</h1>
    <p>You are my today, my tomorrow, my always.</p>
    <button onclick="yesClicked()">YES ❤️</button>
    <button id="noBtn">NO 🙈</button>
  </div>

  <div class="container hidden" id="final">
    <h1 class="final">She said YES!!! 💖✨</h1>
    <p>
      Suman, this is just the beginning of our forever.
    </p>
  </div>

  <script>
    function nextStep() {
      document.getElementById('step1').classList.add('hidden');
      document.getElementById('step2').classList.remove('hidden');
    }
    function nextStep2() {
      document.getElementById('step2').classList.add('hidden');
      document.getElementById('step3').classList.remove('hidden');
    }
    function yesClicked() {
      document.getElementById('step3').classList.add('hidden');
      document.getElementById('final').classList.remove('hidden');
    }

    const noBtn = document.getElementById('noBtn');
    noBtn.addEventListener('mouseover', () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);
      noBtn.style.left = x + 'px';
      noBtn.style.top = y + 'px';
    });

    const heartContainer = document.querySelector('.floating-hearts');
    setInterval(() => {
      const heart = document.createElement('span');
      heart.innerHTML = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
      heartContainer.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }, 300);
  </script>
</body>
</html>

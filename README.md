# Valentines-
just for uhh..💕✨
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Forever Us ❤️</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ff6f91, #ff9a9e);
    font-family: Arial, sans-serif;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card {
    background: white;
    border-radius: 25px;
    padding: 35px;
    width: 90%;
    max-width: 440px;
    text-align: center;
    box-shadow: 0 15px 40px rgba(0,0,0,0.3);
    z-index: 5;
  }

  h1 { color: #e63946; }
  h2 { color: #b5179e; }
  p { color: #5a1a1a; font-size: 16px; }

  button {
    padding: 12px 25px;
    font-size: 16px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    margin: 10px;
  }

  .yes { background: #ff4d6d; color: white; }
  .no { background: #555; color: white; }

  .secret, .photo, .forever {
    display: none;
    margin-top: 20px;
    animation: fadeIn 1.5s ease-in;
  }

  .photo img {
    width: 100%;
    border-radius: 20px;
    margin-top: 15px;
  }

  .forever {
    font-size: 22px;
    font-weight: bold;
    color: #ff4d6d;
    animation: pulse 1.5s infinite;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: scale(0.95); }
    to { opacity: 1; transform: scale(1); }
  }

  @keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.12); }
    100% { transform: scale(1); }
  }

  /* Floating emojis */
  .emoji {
    position: absolute;
    font-size: 22px;
    animation: float 6s infinite linear;
    opacity: 0.8;
    z-index: 1;
  }

  @keyframes float {
    from { transform: translateY(100vh); }
    to { transform: translateY(-10vh); }
  }

  /* Light heart rain */
  .heart {
    position: absolute;
    top: -10vh;
    font-size: 18px;
    opacity: 0.7;
    animation: heartFall linear forwards;
    z-index: 1;
  }

  @keyframes heartFall {
    to {
      transform: translateY(110vh);
      opacity: 0;
    }
  }

  .burn {
    animation: burn 1s forwards;
  }

  @keyframes burn {
    0% { background: #555; opacity: 1; }
    100% { background: red; opacity: 0; transform: scale(0); }
  }

  .burst {
    position: absolute;
    font-size: 20px;
    animation: burst 1s forwards;
    z-index: 10;
  }

  @keyframes burst {
    to {
      transform: translate(var(--x), var(--y)) scale(0);
      opacity: 0;
    }
  }
</style>
</head>

<body>

<audio id="music" loop>
  <!-- 🔴 Replace with your MP3 file -->
  <source src="music.mp3" type="audio/mpeg">
</audio>

<script>
  /* Floating emojis */
  const emojis = ["💖","💕","💘","❤️","🌷","✨"];
  for (let i = 0; i < 20; i++) {
    let e = document.createElement("div");
    e.className = "emoji";
    e.innerHTML = emojis[Math.floor(Math.random()*emojis.length)];
    e.style.left = Math.random()*100 + "vw";
    e.style.animationDuration = (Math.random()*3 + 4) + "s";
    document.body.appendChild(e);
  }

  /* Light heart rain */
  function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 5) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 8000);
  }
  setInterval(createHeart, 900);

  function yesClick(e) {
    document.getElementById("secret").style.display = "block";
    document.getElementById("photo").style.display = "block";
    document.getElementById("forever").style.display = "block";

    document.getElementById("music").play();

    for (let i = 0; i < 25; i++) {
      let burst = document.createElement("div");
      burst.className = "burst";
      burst.innerHTML = "💖";
      burst.style.left = e.clientX + "px";
      burst.style.top = e.clientY + "px";
      burst.style.setProperty("--x", (Math.random()*200 - 100) + "px");
      burst.style.setProperty("--y", (Math.random()*200 - 100) + "px");
      document.body.appendChild(burst);
      setTimeout(() => burst.remove(), 1000);
    }
  }

  function noClick() {
    const btn = document.getElementById("noBtn");
    btn.classList.add("burn");
    setTimeout(() => btn.remove(), 1000);
  }
</script>

<div class="card">
  <h1>Hey My Love ❤️</h1>
  <p>This little page holds a big part of my heart 💕</p>

  <h2>Will you be my Valentine? 💌</h2>

  <button class="yes" onclick="yesClick(event)">YES 💖</button>
  <button class="no" id="noBtn" onclick="noClick()">NO 😢</button>

  <div class="secret" id="secret">
    Mere pyaare se bacchee 🫶🏻💕<br><br>
    I love you today, tomorrow, and forever ❤️✨  
    You are my everything 💖  
    Being with you is a blessing 🌷  
    <br><br>
    <strong>I am going to marry you very soon ❤️✨🌷</strong>
  </div>

  <div class="photo" id="photo">
    <!-- 🔴 Replace with your image -->
    <img src="us.jpg" alt="Us Together">
  </div>

  <div class="forever" id="forever">
    💍 Forever Together 💍
  </div>
</div>

</body>
</html>

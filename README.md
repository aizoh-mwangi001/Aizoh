<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love Betty ❤️</title>
<style>
body {
  margin: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #ff5fa2, #8f5bff);
  font-family: 'Segoe UI', sans-serif;
  color: white;
}
.card {
  background: rgba(255,255,255,0.15);
  backdrop-filter: blur(12px);
  padding: 30px;
  border-radius: 22px;
  text-align: center;
  width: 90%;
  max-width: 360px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
}
h1 { font-size: 1.9rem; margin-bottom: 10px; }
h2 { font-size: 1.2rem; font-weight: normal; margin-bottom: 20px; }
p { font-size: 1rem; opacity: 0.9; margin-bottom: 25px; }
button {
  border: none;
  padding: 14px 32px;
  font-size: 1rem;
  border-radius: 30px;
  cursor: pointer;
  margin: 8px;
  transition: 0.3s;
}
#yes { background: #ff2f7d; color: white; }
#yes:hover { transform: scale(1.08); }
#no { background: transparent; color: white; border: 1px solid white; position: relative; }
.message { margin-top: 20px; font-size: 1.1rem; display: none; }
.countdown { margin-top: 15px; font-size: 0.9rem; opacity: 0.85; }
#whatsappLink a { color: white; font-weight: bold; text-decoration: none; background: #25D366; padding: 12px 20px; border-radius: 20px; display: inline-block; margin-top: 10px; }
</style>
</head>
<body>
<div class="card">
  <h2>My love Betty ❤️🥰</h2>
  <h1>Will You Be My Valentine?</h1>
  <p>It’s been three years now,<br>and I want you more than ever.</p>

  <button id="yes">YES 💕</button>
  <button id="no">NO 💔</button>

  <div class="message" id="message">I love you baby ❤️🫶</div>
  <div id="whatsappLink" style="display:none;">
    <a id="wa" href="#" target="_blank">Send me a message on WhatsApp 💌</a>
  </div>
  <div class="countdown" id="countdown"></div>
</div>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/10/30/audio_7f2c4c9c7e.mp3" type="audio/mpeg">
</audio>

<script>
const yesBtn = document.getElementById("yes");
const noBtn = document.getElementById("no");
const msg = document.getElementById("message");
const music = document.getElementById("music");
const waLinkDiv = document.getElementById("whatsappLink");
const waLink = document.getElementById("wa");
const countdownDiv = document.getElementById("countdown");

const phone = "254797008884"; // Betty's number
const text = encodeURIComponent("I love you baby ❤️🫶 Happy Valentine’s Day 💖");

yesBtn.onclick = () => {
  msg.style.display = "block";
  waLinkDiv.style.display = "block";
  waLink.href = `https://wa.me/${phone}?text=${text}`;
  // Play music reliably on mobile
  music.pause();
  music.currentTime = 0;
  music.play().catch(() => {
    alert("Tap YES again to play the music ❤️");
  });
};

noBtn.onmouseover = () => {
  const x = Math.random() * 200 - 100;
  const y = Math.random() * 200 - 100;
  noBtn.style.transform = `translate(${x}px, ${y}px)`;
};

// Countdown logic
const startTime = new Date("Feb 10, 2026 14:00:00").getTime();
const valentinesDay = new Date("Feb 14, 2026 00:00:00").getTime();

function updateCountdown() {
  const now = new Date().getTime();
  if(now < startTime){
    countdownDiv.innerHTML = "Something special is coming… 💭";
    return;
  }
  const distance = valentinesDay - now;
  if(distance <= 0){
    countdownDiv.innerHTML = "Happy Valentine’s Day 💖";
    return;
  }
  const days = Math.floor(distance / (1000*60*60*24));
  const hours = Math.floor((distance % (1000*60*60*24)) / (1000*60*60));
  const minutes = Math.floor((distance % (1000*60*60)) / (1000*60));
  const seconds = Math.floor((distance % (1000*60)) / 1000);
  countdownDiv.innerHTML = `Counting down to our day… ${days}d ${hours}h ${minutes}m ${seconds}s`;
}
setInterval(updateCountdown, 1000);
updateCountdown();
</script>
</body>
</html># Aizoh

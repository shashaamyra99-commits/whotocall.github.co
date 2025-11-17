[PHONE CALL BOOTH.html](https://github.com/user-attachments/files/23589936/PHONE.CALL.BOOTH.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Phone Booth Kiosk — Keypad</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap');

:root{
  --red-1: #8b0000;
  --red-2: #b30000;
  --accent: #ff4d4d;
  --panel: rgba(255,255,255,0.15);
}

html,body{height:100%;margin:0}
body {
  display:flex;
  align-items:center;
  justify-content:center;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(90deg, var(--red-1), var(--red-2));
  background-size: 400% 400%;
  animation: redFlow 8s ease infinite;
  color: white;
  -webkit-font-smoothing:antialiased;
}

@keyframes redFlow{
  0%{background-position:0% 50%}
  50%{background-position:100% 50%}
  100%{background-position:0% 50%}
}

/* Phone Booth Panels */
.scene{
  width:500px;
  max-width:95vw;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:20px;
  padding:30px 15px;
}
.sign{
  width:100%;
  text-align:center;
  font-weight:700;
  letter-spacing:4px;
  font-size:24px;
  padding:12px 0;
  background: linear-gradient(180deg, rgba(255,255,255,0.2), rgba(0,0,0,0.1));
  border-radius:12px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.35), inset 0 1px 0 rgba(255,255,255,0.05);
}

/* Display Panel */
.display{
  width:100%;
  padding:25px 25px 15px 25px;
  background: var(--panel);
  border-radius:20px;
  box-shadow: 0 12px 35px rgba(0,0,0,0.3);
  backdrop-filter: blur(8px);
  display:flex;
  flex-direction:column;
  gap:20px;
}
h1{margin:6px 0 0 0;font-size:30px;text-align:left}

/* Keypad */
.keypad{
  display:grid;
  grid-template-columns: repeat(2, 1fr);
  gap:16px;
  width:100%;
  max-width:360px;
  margin-top:10px;
}
.keypad button{
  aspect-ratio: 1 / 1;
  width:100%;
  border-radius:15px;
  border:none;
  font-size:28px;
  font-weight:700;
  background: linear-gradient(180deg, rgba(255,255,255,0.3), rgba(0,0,0,0.2));
  color:white;
  box-shadow: 0 8px 20px rgba(0,0,0,0.35), inset 0 0 10px rgba(255,255,255,0.05);
  cursor:pointer;
  transition:transform .12s ease, box-shadow .12s ease;
  display:flex;align-items:center;justify-content:center;
}
.keypad button:active{transform:translateY(2px) scale(.995)}
.keypad button:hover{transform:translateY(-4px); box-shadow: 0 18px 40px rgba(0,0,0,0.45);}

/* Player / Progress Bar */
.player {
  width:100%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
}
.bar-wrap{
  flex:1;
  height:20px;
  background: rgba(255,255,255,0.2);
  border-radius: 12px;
  overflow: hidden;
  position: relative; /* important */
}
@keyframes gradientMove {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
.bar{
  position:absolute; /* important */
  top:0; left:0;
  height:100%;
  width:0%;
  border-radius:12px;
  background: linear-gradient(270deg, #ff6666, #ff9999, #ff0000, #ff6666);
  background-size:400% 100%;
  animation: gradientMove 2s linear infinite;
}
.message{font-size:18px;font-weight:600;text-align:right; min-width:150px;}

/* Thank you screen */
.thanks{display:flex;flex-direction:column;align-items:center;gap:15px}

/* Side Panels */
.side-panel{position:fixed;top:0;bottom:0;width:12vw;max-width:80px;background:linear-gradient(180deg,rgba(0,0,0,0.12),rgba(0,0,0,0.06));box-shadow:inset 0 0 80px rgba(0,0,0,0.35);pointer-events:none}
.left{left:0}
.right{right:0}

/* Welcome Screen */
#welcomeScreen {
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  height:200px;
  text-align:center;
  gap:25px;
}
#welcomeScreen h1{
  font-size:32px;
  line-height:1.2;
}
#welcomeScreen button{
  padding:15px 25px;
  font-size:20px;
  border:none;
  border-radius:10px;
  background:var(--accent);
  color:white;
  cursor:pointer;
  font-weight:700;
}
@media (max-width:480px){
  .scene{padding:16px}
  h1{font-size:24px}
  .sign{font-size:18px}[audio4.mp3](https://github.com/user-attachments/files/23589954/audio4.mp3)
[audio3.mp3](https://github.com/user-attachments/files/23589949/audio3.mp3)
[audio2.mp3](https://github.com/user-attachments/files/23589945/audio2.mp3)
[audio1.mp3](https://github.com/user-attachments/files/23589937/audio1.mp3)

  #welcomeScreen h1{font-size:24px;}
  #welcomeScreen button{font-size:18px; padding:12px 18px;}
}
</style>
</head>
<body>
<div class="side-panel left"></div>
<div class="side-panel right"></div>

<div class="scene">
  <div class="sign">TELEFON</div>
  <div class="display" id="screen">
    <div id="welcomeScreen">
      <h1>WELCOME TO<br>WHO TO CALL</h1>
      <button id="startBtn">Start</button>
    </div>

    <div id="keypadScreen" style="display:none">
  <h1 style="text-align:left; margin-bottom:10px;">Pilih Hotline</h1>
  <div class="keypad" role="keypad">
    <button data-key="1"><span class="digit">1</span></button>
    <button data-key="2"><span class="digit">2</span></button>
    <button data-key="3"><span class="digit">3</span></button>
    <button data-key="4"><span class="digit">4</span></button>
  </div>
</div>

<!-- Add this OUTSIDE the screen div -->
<div class="player" id="player" style="display:none">
  <div class="bar-wrap"><div class="bar" id="bar"></div></div>
  <div class="message" id="playerMessage">Sedang bermain audio...</div>
</div>

    </div>
  </div>
</div>

<audio id="audio1" src="audio1.mp3" preload="auto"></audio>
<audio id="audio2" src="audio2.mp3" preload="auto"></audio>
<audio id="audio3" src="audio3.mp3" preload="auto"></audio>
<audio id="audio4" src="audio4.mp3" preload="auto"></audio>

<script>
const welcomeScreen = document.getElementById('welcomeScreen');
const keypadScreen = document.getElementById('keypadScreen');
const startBtn = document.getElementById('startBtn');
let rafId = null;
let currentAudio = null;

// Start Button
startBtn.addEventListener('click',()=>{
  welcomeScreen.style.display='none';
  keypadScreen.style.display='flex';
  playRandomAudio();
});

// Keypad Buttons
function setupKeypadButtons(){
  document.querySelectorAll('.keypad button').forEach(btn=>{
    btn.onclick = () => {
      // Cut current audio
      if(currentAudio){
        currentAudio.pause();
        currentAudio.currentTime=0;
        document.getElementById('player').style.display='none';
        if(rafId) cancelAnimationFrame(rafId);
      }
      showThankYou();
    }
  });
}
setupKeypadButtons();

// Progress Bar
function updateBar(audio){
  const bar = document.getElementById('bar');
  function loop(){
    const pct = Math.min(100,(audio.currentTime/28)*100);
    bar.style.width = pct+'%';
    if(!audio.paused && audio.currentTime<28) rafId=requestAnimationFrame(loop);
  }
  rafId=requestAnimationFrame(loop);
}

// Play Audio
function playAudio(num){
  const audio = document.getElementById('audio'+num);
  if(!audio) return;
  currentAudio = audio;

  const player = document.getElementById('player');
  player.style.display='flex';
  document.getElementById('bar').style.width='0%';

  audio.currentTime=0;
  audio.play().then(()=>{
    if(rafId) cancelAnimationFrame(rafId);
    updateBar(audio);
    audio.onended = ()=>{
      player.style.display='none';
      currentAudio=null;
    }
  });
}

function updateBar(audio){
  const bar = document.getElementById('bar');
  function loop(){
    const pct = Math.min(100,(audio.currentTime/28)*100);
    bar.style.width = pct+'%';
    if(!audio.paused && audio.currentTime<28) rafId=requestAnimationFrame(loop);
  }
  rafId=requestAnimationFrame(loop);
}

// Play Random 1-4
function playRandomAudio(){
  const rand=Math.floor(Math.random()*4)+1;
  playAudio(rand);
}

// Thank You Screen
function showThankYou(){
  const screen=document.getElementById('screen');
  screen.innerHTML=`
    <div class="thanks">
      <div style="font-size:26px;font-weight:700">Terima kasih kerana mendengar</div>
      <div style="opacity:.9">Sila ambil kad anda</div>
    </div>
  `;
  setTimeout(()=>{
    screen.innerHTML=`
      <div id="welcomeScreen">
        <h1>WELCOME TO<br>WHO TO CALL</h1>
        <button id="startBtn">Start</button>
      </div>
      <div id="keypadScreen" style="display:none">
        <h1 style="text-align:left; margin-bottom:10px;">Pilih Hotline</h1>
        <div class="keypad" role="keypad">
          <button data-key="1"><span class="digit">1</span></button>
          <button data-key="2"><span class="digit">2</span></button>
          <button data-key="3"><span class="digit">3</span></button>
          <button data-key="4"><span class="digit">4</span></button>
        </div>
        <div class="player" id="player" style="display:none">
          <div class="bar-wrap"><div class="bar" id="bar"></div></div>
          <div class="message" id="playerMessage">Sedang bermain audio...</div>
        </div>
      </div>
    `;
    document.getElementById('startBtn').addEventListener('click',()=>{
      document.getElementById('welcomeScreen').style.display='none';
      document.getElementById('keypadScreen').style.display='flex';
      playRandomAudio();
    });
    setupKeypadButtons();
  },5000);
}
</script>
</body>
</html>

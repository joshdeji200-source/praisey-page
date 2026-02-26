<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Favour @15 👑</title>

<style>
body{
  margin:0;
  height:100vh;
  overflow:hidden;
  font-family: Arial, sans-serif;
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
  color:white;
  transition: background 0.6s;
}

/* PAGE 1 BACKGROUND */
.page1bg{
  background: radial-gradient(circle at top left,#0d1b4c,#4b0082,#1a0033);
}

/* PAGE 2 ABSTRACT PURPLE PINK */
.page2bg{
  background: linear-gradient(135deg,#ff00cc,#6a00ff,#ff66cc,#9900ff);
  background-size: 400% 400%;
  animation: moveBG 8s infinite alternate;
}

@keyframes moveBG{
  0%{background-position:0% 50%;}
  100%{background-position:100% 50%;}
}

button{
  padding:20px 40px;
  font-size:20px;
  font-weight:bold;
  border:none;
  border-radius:40px;
  cursor:pointer;
  margin:15px;
  transition:0.3s;
}

.big-btn{
  font-size:22px;
  padding:22px 45px;
}

.hidden{display:none;}

h1{font-size:2.5em;}
.big-text{font-size:3em;font-weight:900;}
.stats{font-size:1.8em;font-weight:900;margin:10px 0;}

.confetti,.balloon,.heart{
  position:absolute;
  font-size:30px;
  animation:float 5s linear forwards;
}

@keyframes float{
  from{transform:translateY(0) rotate(0deg);opacity:1;}
  to{transform:translateY(-800px) rotate(720deg);opacity:0;}
}
</style>
</head>

<body class="page1bg">

<!-- PAGE 1 -->
<div id="page1">
  <h1>In a world where legends are born…</h1>
  <h1>On this day… A QUEEN was created 👑</h1>
  <h1>Her name is… FAVOUR.</h1>
  <button class="big-btn" onclick="goPage2()">🎬 Reveal Her Destiny</button>
</div>

<!-- PAGE 2 -->
<div id="page2" class="hidden">
  <h1>🔴 SYSTEM UPDATE COMPLETE 🔴 ✅</h1>
  <h1>FAVOUR 14❌… 15✅💯</h1>
  <h1>FAVOUR @15 INSTALLED</h1>

  <div class="stats">+1000 Aura ✨</div>
  <div class="stats">+500 Beauty 💅</div>
  <div class="stats">+Infinite Blessings 🙏</div>
  <div class="stats">+Main Character Energy 🎬</div>

  <button class="big-btn" onclick="birthdayMessage()">🎂 Read Birthday Message</button>
  <button class="big-btn" onclick="chaosMode()">🚨 DO NOT PRESS THIS</button>
</div>

<!-- PAGE 3 -->
<div id="page3" class="hidden">
  <h1>Happy Birthday, my G 🎉</h1>
  <p>
  May your life be filled with peace, success and laughter.<br>
  May all your dreams come true for you and may you always get the best of the world.
  </p>

  <div class="big-text">LONG LIVE THE QUEEN 👑</div>
</div>

<script>

function goPage2(){
  document.body.className="page2bg";
  document.getElementById("page1").classList.add("hidden");
  document.getElementById("page2").classList.remove("hidden");
  scatterConfetti(150);

  // Flash gold then back
  document.body.style.background="gold";
  setTimeout(()=>{
    document.body.className="page2bg";
  },500);
}

function birthdayMessage(){
  document.getElementById("page2").classList.add("hidden");
  document.getElementById("page3").classList.remove("hidden");
  scatterConfetti(200);
}

function chaosMode(){
  document.body.style.background="red";
  setTimeout(()=>{
    document.body.className="page2bg";
  },500);

  alert("TOO LATE\nYOU PRESSED IT\nEXTRA CHAOS ACTIVATED");

  scatterBalloons(120);
  scatterHearts(120);
}

function scatterConfetti(count){
  for(let i=0;i<count;i++){
    let c=document.createElement("div");
    c.className="confetti";
    c.innerHTML="🎉";
    c.style.left=Math.random()*window.innerWidth+"px";
    c.style.top=Math.random()*window.innerHeight+"px";
    c.style.fontSize=(20+Math.random()*40)+"px";
    c.style.animationDuration=(3+Math.random()*3)+"s";
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),6000);
  }
}

function scatterBalloons(count){
  for(let i=0;i<count;i++){
    let b=document.createElement("div");
    b.className="balloon";
    b.innerHTML="🎈";
    b.style.left=Math.random()*window.innerWidth+"px";
    b.style.top=Math.random()*window.innerHeight+"px";
    b.style.fontSize=(40+Math.random()*50)+"px";
    document.body.appendChild(b);
    setTimeout(()=>b.remove(),6000);
  }
}

function scatterHearts(count){
  for(let i=0;i<count;i++){
    let h=document.createElement("div");
    h.className="heart";
    h.innerHTML="💖";
    h.style.left=Math.random()*window.innerWidth+"px";
    h.style.top=Math.random()*window.innerHeight+"px";
    h.style.fontSize=(40+Math.random()*50)+"px";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),6000);
  }
}

</script>

</body>
</html>

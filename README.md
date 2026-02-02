
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine Proposal 2026</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<!-- Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Pacifico&display=swap" rel="stylesheet">

<!-- html2canvas -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>

<style>
/* ROOT COLORS */
:root {
    --primary: #ff4fa3;
    --secondary: #cba4ff;
    --bg1: #ffe5f3;
    --bg2: #f2e4ff;
    --neon: #ff2fcf;
    --text-dark: #5a4c66;
}

/* GLOBAL BODY */
body {
    margin: 0;
    background: radial-gradient(circle at top, var(--bg1), var(--bg2));
    font-family: "Poppins", sans-serif;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
}

/* ------------------- PULSING HEART LOADER ------------------- */
#loader {
    position: fixed;
    inset: 0;
    background: linear-gradient(135deg, #ffd8ec, #f2d6ff);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 5000;
    animation: fadeOut 1s ease 2.4s forwards;
}

.pulse-heart {
    width: 80px;
    height: 80px;
    background: #ff4fa3;
    position: relative;
    transform: rotate(45deg);
    animation: pulse 1.2s infinite ease-in-out;
    box-shadow: 0 0 25px rgba(255, 30, 150, 0.4);
}
.pulse-heart:before,
.pulse-heart:after {
    content: "";
    width: 80px;
    height: 80px;
    background: #ff4fa3;
    border-radius: 50%;
    position: absolute;
}
.pulse-heart:before { left: -40px; top: 0; }
.pulse-heart:after  { left: 0; top: -40px; }

#loaderText {
    margin-top: 22px;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--primary);
}

@keyframes pulse {
    0%   { transform: rotate(45deg) scale(1); }
    50%  { transform: rotate(45deg) scale(1.25); }
    100% { transform: rotate(45deg) scale(1); }
}

@keyframes fadeOut {
    to { opacity: 0; visibility: hidden; }
}

/* ------------------- FLOATING BUBBLES (BACKGROUND) ------------------- */
.bubble {
    position: absolute;
    border-radius: 50%;
    background: rgba(255,255,255,0.45);
    animation: floatUp linear infinite;
}

@keyframes floatUp {
    from { transform: translateY(100vh) scale(.4); opacity:.75; }
    to   { transform: translateY(-10vh) scale(1);  opacity:0; }
}

/* ------------------- MAIN CARD ------------------- */
.card {
    background: white;
    width: 85%;
    max-width: 480px;
    padding: 52px 36px;
    border-radius: 32px;
    text-align: center;
    box-shadow: 0 20px 45px rgba(150, 85, 255, 0.18);
    position: relative;
    z-index: 10;
}

/* Question Frame */
.questionFrame {
    padding: 18px 16px;
    border-radius: 18px;
    margin-bottom: 22px;
    background: linear-gradient(135deg, #ffe3f0, #e8d8ff);
    box-shadow: 0 0 14px rgba(255, 90, 175, 0.18);
}

/* Typing animation text */
.typed {
    display: block;
    overflow: hidden;
    border-right: 3px solid var(--primary);
    font-size: 1.75rem;
    font-weight: 700;
    color: var(--text-dark);
    line-height: 1.4;
    white-space: normal;
    min-height: 65px;
}

@media(max-width:420px){
    .typed{ font-size:1.55rem; }
}

.typed-small {
    display:block;
    margin-top:4px;
    border-right:2px solid var(--secondary);
    font-size:1.15rem;
    color:var(--text-dark);
    white-space:nowrap;
}

/* Emoji */
.emoji { font-size:85px; animation:bounce 1.6s infinite; }
@keyframes bounce {
    50% { transform:translateY(-14px); }
}

/* Buttons */
.btn-container {
    margin-top:38px;
    display:flex;
    flex-direction:column;
    gap:22px;
}
.btn {
    padding: 16px 42px;
    border: none;
    border-radius: 18px;
    font-size: 1.15rem;
    font-weight: 600;
    cursor: pointer;
    transition: 0.3s;
}
#yesBtn{
    background:linear-gradient(135deg,#ff4fa3,#ff77c9);
    color:white;
    box-shadow:0 8px 26px rgba(255,70,160,0.4);
}
#yesBtn:hover{ transform:translateY(-4px) scale(1.09); }

#noBtn{
    background:rgba(255,255,255,0.55);
    backdrop-filter:blur(8px);
    color:#5e4f73;
    border:2px solid rgba(200,150,255,0.25);
    box-shadow:0 4px 16px rgba(160,120,255,0.18);
}

/* shy text */
#shyMsg {
    margin-top:16px;
    opacity:0;
    animation:shyAppear 1.6s ease forwards 2.5s;
    color:#7b6a8e;
}
@keyframes shyAppear { to{opacity:1;} }

/* ------------------- CELEBRATION SCREEN ------------------- */
#celebrate {
    position:fixed;
    inset:0;
    background:linear-gradient(135deg,#ffd9ec,#f2d8ff);
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
    z-index:3000;
    overflow:hidden;
}

#celebrate h1 {
    font-size:3rem;
    color:#ff4fa3;
    font-weight:800;
    text-shadow:
        0 0 12px rgba(255,60,160,0.6),
        0 0 22px rgba(255,40,140,0.5);
    margin-bottom:20px;
}

.sparkle {
    position:absolute;
    width:6px;
    height:6px;
    background:white;
    border-radius:50%;
    opacity:0.85;
    box-shadow:0 0 12px white;
    animation:sparkleMove 2s linear infinite;
}
@keyframes sparkleMove {
    from { transform:translateY(100vh) scale(.6); opacity:.9;}
    to   { transform:translateY(-10vh) scale(1.8); opacity:0;}
}

.cHeart {
    position:absolute;
    font-size:28px;
    animation:riseHeart 3s ease-out forwards;
}
@keyframes riseHeart{
    from{transform:translateY(0) scale(1);opacity:1;}
    to  {transform:translateY(-150px) scale(2);opacity:0;}
}

/* ------------------- SHARE SCREEN ------------------- */
#shareScreen {
    position:fixed;
    inset:0;
    background:linear-gradient(135deg,#ffd4ea,#e4b6ff);
    display:none;
    flex-direction:column;
    align-items:center;
    padding:30px 16px;
    z-index:4000;
    text-align:center;
}

#shareTitle{
    font-size:2.6rem;
    margin-top:40px;
    font-weight:700;
    color:white;
    text-shadow:
        0 0 10px var(--neon),
        0 0 20px var(--neon);
}

.shareFrame{
    margin-top:30px;
    padding:24px;
    width:85%;
    max-width:340px;
    background:rgba(255,255,255,0.55);
    border-radius:25px;
    border:3px solid rgba(255,80,200,0.7);
    box-shadow:
        0 0 15px rgba(255,30,160,0.5),
        inset 0 0 10px rgba(255,80,200,0.4);
}

#shareSignature{
    margin-top:25px;
    font-size:1.3rem;
    font-family:"Pacifico",cursive;
    color:#ff4fa3;
}

#downloadBtn {
    margin-top:35px;
    padding:14px 38px;
    font-size:1.25rem;
    border:none;
    border-radius:18px;
    color:white;
    background:linear-gradient(135deg,#ff4fa3,#ff77c9);
    box-shadow:0 8px 26px rgba(255,70,160,0.4);
    cursor:pointer;
}
</style>
</head>

<body>

<!-- LOADER -->
<div id="loader">
    <div class="pulse-heart"></div>
    <div id="loaderText">Setting the mood… Be patient😉</div>
</div>

<script>
/* FLOATING BUBBLES (BACKGROUND) */
for (let i=0;i<35;i++){
    let b=document.createElement("div");
    b.classList.add("bubble");
    let s=20+Math.random()*60;
    b.style.width=s+"px"; b.style.height=s+"px";
    b.style.left=Math.random()*100+"vw";
    b.style.animationDuration=(6+Math.random()*8)+"s";
    b.style.animationDelay=Math.random()*3+"s";
    document.body.appendChild(b);
}
</script>

<!-- MAIN CARD -->
<div class="card">
    <div class="emoji">❤️🫵🏽❤️</div>

    <div class="questionFrame">
        <div id="typedText" class="typed"></div>
    </div>
    <div id="fromText" class="typed-small"></div>

    <div class="btn-container">
        <button id="yesBtn" class="btn">Yes</button>
        <button id="noBtn" class="btn">No</button>
    </div>

    <div id="shyMsg">“No button” is a bit shy 🌚</div>
</div>

<!-- CELEBRATION SCREEN -->
<div id="celebrate">
    <h1>Yay!! You Accepted💖</h1>
</div>

<!-- SHARE SCREEN -->
<div id="shareScreen">
    <div id="shareTitle">YOU SAID YES! 💖✨</div>

    <div class="shareFrame">
        <h3 style="color:#5a4c66;font-size:1.4rem;margin-bottom:4px;">Let’s Get It!💃🏽🕺🏾</h3>
        <p style="color:#7a6a8e;">💗Here's to you🥂💗</p>
    </div>

    <div id="shareSignature">— MBILIMA 😌</div>

    <button id="downloadBtn">Share / Download</button>
</div>

<!-- AUDIO -->
<audio id="bgMusic">
    <source src="https://cdn.pixabay.com/download/audio/2023/01/18/audio_8da5ad2e28.mp3?filename=romantic-piano-135356.mp3">
</audio>
<audio id="wiggleSound">
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_0d95ca0fcb.mp3?filename=pop-94319.mp3">
</audio>
<audio id="yesSound">
    <source src="https://cdn.pixabay.com/download/audio/2021/09/02/audio_4680a29fda.mp3?filename=correct-2-46134.mp3">
</audio>

<script>
const typedText = document.getElementById("typedText");
const fromText  = document.getElementById("fromText");
const noBtn     = document.getElementById("noBtn");
const yesBtn    = document.getElementById("yesBtn");
const music     = document.getElementById("bgMusic");
const wiggleSound = document.getElementById("wiggleSound");
const yesSound = document.getElementById("yesSound");
const celebrate = document.getElementById("celebrate");
const shareScreen = document.getElementById("shareScreen");
const downloadBtn = document.getElementById("downloadBtn");

/* TYPING EFFECT */
let question = "Will you be my Valentine?";
let signature = "— from Mbilima 😌";

let i=0, j=0;
function typeMain(){
    if(i < question.length){
        typedText.innerHTML += question.charAt(i);
        i++;
        setTimeout(typeMain, 70);
    } else {
        typedText.style.borderRight="none";
        setTimeout(typeFrom, 350);
    }
}
function typeFrom(){
    if(j < signature.length){
        fromText.innerHTML += signature.charAt(j);
        j++;
        setTimeout(typeFrom, 55);
    } else {
        fromText.style.borderRight="none";
    }
}
setTimeout(typeMain, 2400);

/* NO BUTTON FLEES */
let yesScale=1, noScale=1;
function moveNo(){
    wiggleSound.currentTime=0;
    wiggleSound.play();

    let angle=Math.random()*2*Math.PI;
    let dist=120+Math.random()*140;

    noBtn.style.transform=`translate(${Math.cos(angle)*dist}px,${Math.sin(angle)*dist}px) scale(${noScale})`;

    yesScale+=0.15;
    noScale-=0.05;
    if(noScale<0.45) noScale=0.45;

    yesBtn.style.transform=`scale(${yesScale})`;
}
noBtn.addEventListener("mouseenter", moveNo);
noBtn.addEventListener("touchstart",e=>{ e.preventDefault(); moveNo(); });

/* YES BUTTON */
yesBtn.addEventListener("click",()=>{
    yesSound.play();
    music.volume=0.5;
    music.play().catch(()=>{});

    sendTelegramNotification();
    startCelebration();

    setTimeout(()=>{
        celebrate.style.display="none";
        shareScreen.style.display="flex";
    },2400);
});

/* TELEGRAM ALERT */
function sendTelegramNotification(){
    const botToken="8284220817:AAFuA-PmC_5kzA1vZ5CJUg3RtRCysgP-Mr4";
    const chatID="6984879007";
    const text=encodeURIComponent(`She clicked YES! 💖\nTimestamp: ${new Date().toLocaleString()}`);
    fetch(`https://api.telegram.org/bot${botToken}/sendMessage?chat_id=${chatID}&text=${text}`);
}

/* CELEBRATION */
function startCelebration(){
    celebrate.style.display="flex";

    let celebrationInterval=setInterval(()=>{
        let h=document.createElement("div");
        h.className="cHeart";
        h.innerHTML=["💖","💘","💕","💗"][Math.floor(Math.random()*4)];
        h.style.left=Math.random()*100+"vw";
        h.style.bottom="-20px";
        h.style.fontSize=(26+Math.random()*22)+"px";
        celebrate.appendChild(h);
        setTimeout(()=>h.remove(),3000);
    },180);

    /* sparkles */
    for(let i=0;i<22;i++){
        let s=document.createElement("div");
        s.classList.add("sparkle");
        s.style.left=Math.random()*100+"vw";
        s.style.animationDuration=(1.8+Math.random()*2)+"s";
        s.style.animationDelay=(Math.random()*1.5)+"s";
        celebrate.appendChild(s);
        setTimeout(()=>s.remove(),3500);
    }

    setTimeout(()=>clearInterval(celebrationInterval),2000);
}

/* SHARE / DOWNLOAD */
downloadBtn.addEventListener("click",()=>{
    html2canvas(shareScreen,{scale:2}).then(canvas=>{
        let link=document.createElement("a");
        link.download="She_Said_Yes.png";
        link.href=canvas.toDataURL();
        link.click();
    });
});
</script>

</body>
</html>

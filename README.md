# Birthday-letter
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Special Letter 💌</title>

<style>
body{
    margin:0;
    font-family:Arial;
    background: linear-gradient(135deg,#f3e8ff,#e9d5ff,#dcc6ff,#f7f0ff);
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
    color:#5a2d82;
    flex-direction:column;
    padding:15px;
    box-sizing:border-box;
}

/* hearts */
.heart{
    position:absolute;
    font-size:18px;
    opacity:0.6;
    animation:float 4s infinite ease-in-out;
}

@keyframes float{
    0%{transform:translateY(0);}
    50%{transform:translateY(-20px);}
    100%{transform:translateY(0);}
}

/* TITLE */
#title{
    font-size:24px;
    font-weight:bold;
    color:#6a3a8a;
    margin-bottom:10px;
    text-align:center;
}

/* 💎 PREMIUM COUNTDOWN BOX */
#countdownBox{
    display:flex;
    gap:10px;
    margin-bottom:15px;
    flex-wrap:wrap;
    justify-content:center;
}

/* individual blocks */
.box{
    background:rgba(255,255,255,0.6);
    backdrop-filter: blur(10px);
    padding:12px 14px;
    border-radius:12px;
    min-width:75px;
    text-align:center;
    box-shadow:0 6px 15px rgba(0,0,0,0.08);
}

.num{
    font-size:22px;
    font-weight:bold;
    color:#6a3a8a;
}

.label{
    font-size:12px;
    color:#7a4ca3;
    margin-top:3px;
}

/* button */
#startBtn{
    padding:12px 22px;
    border:none;
    border-radius:12px;
    background:#b57edc;
    color:white;
    font-size:16px;
    cursor:pointer;
    opacity:0.5;
    cursor:not-allowed;
}

/* letter box */
#letterBox{
    display:none;
    background:white;
    padding:20px;
    border-radius:15px;
    width:100%;
    max-width:600px;
    max-height:85vh;
    overflow-y:auto;
    box-shadow:0 10px 25px rgba(0,0,0,0.15);
    text-align:center;
    animation:fadeIn 1s ease;
}

@keyframes fadeIn{
    from{opacity:0; transform:scale(0.9);}
    to{opacity:1; transform:scale(1);}
}

h2{
    color:#6a3a8a;
    font-size:20px;
}

p{
    font-size:14px;
    line-height:1.6;
    color:#4b2a6b;
}

@media (max-width:480px){
    #title{font-size:20px;}
    .num{font-size:18px;}
    p{font-size:13px;}
}
</style>
</head>

<body>

<!-- hearts -->
<div class="heart" style="top:10%;left:15%">💜</div>
<div class="heart" style="top:20%;left:80%">✨</div>
<div class="heart" style="top:70%;left:20%">🤍</div>
<div class="heart" style="top:60%;left:75%">🌸</div>

<!-- title -->
<div id="title">🎉 Happy Birthday Angry Bird 🎉</div>

<!-- 💎 COUNTDOWN -->
<div id="countdownBox">
    <div class="box">
        <div class="num" id="days">00</div>
        <div class="label">Days</div>
    </div>

    <div class="box">
        <div class="num" id="hours">00</div>
        <div class="label">Hours</div>
    </div>

    <div class="box">
        <div class="num" id="minutes">00</div>
        <div class="label">Minutes</div>
    </div>

    <div class="box">
        <div class="num" id="seconds">00</div>
        <div class="label">Seconds</div>
    </div>
</div>

<!-- button -->
<button id="startBtn" onclick="showLetter()">💌 Tap to Open Letter</button>

<!-- letter -->
<div id="letterBox">

<h2>💌 A Special Letter For You</h2>

<p>
Happy Birthday to my favorite person 🤍🎂✨
</p>

<p>
Honestly, I don’t even know where to start because no words ever feel enough 🫶🏻
You’re one of those people who made life feel softer 🌸
</p>

<p>
Even though we live far away, you’ve always felt close to my heart 🌙✨
</p>

<p>
Thank you for everything 💖 You became my comfort place 🧿
</p>

<p>
I hope this year brings you happiness, peace and smiles 😌✨
</p>

<p>
And no matter how much time passes… you’ll always be very special to me 🤍
</p>

<p>
Happy Birthday once againnn 🌸🎂  
Now smile please 🫶🏻
</p>

</div>

<script>

// 🎯 target date
let target = new Date("May 22, 2026 00:00:00").getTime();

let x = setInterval(()=>{

    let now = new Date().getTime();
    let diff = target - now;

    if(diff <= 0){
        clearInterval(x);

        document.getElementById("startBtn").disabled = false;
        document.getElementById("startBtn").style.opacity = "1";
        document.getElementById("startBtn").style.cursor = "pointer";

        return;
    }

    let d = Math.floor(diff/(1000*60*60*24));
    let h = Math.floor((diff%(1000*60*60*24))/(1000*60*60));
    let m = Math.floor((diff%(1000*60*60))/(1000*60));
    let s = Math.floor((diff%(1000*60))/1000);

    document.getElementById("days").innerHTML = d;
    document.getElementById("hours").innerHTML = h;
    document.getElementById("minutes").innerHTML = m;
    document.getElementById("seconds").innerHTML = s;

},1000);

// lock initially
window.onload=function(){
    document.getElementById("startBtn").disabled = true;
};

// open letter
function showLetter(){
    document.getElementById("startBtn").style.display="none";
    document.getElementById("title").style.display="none";
    document.getElementById("countdownBox").style.display="none";
    document.getElementById("letterBox").style.display="block";
}

</script>

</body>
</html>

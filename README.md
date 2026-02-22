<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title><b>Time Store™ </b></title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: 'Poppins', sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
    background: linear-gradient(-45deg, #6a11cb, #2575fc, #ff6a00, #ee0979);
    background-size:400% 400%;
    animation: gradientMove 10s ease infinite;
    color:white;
}

@keyframes gradientMove {
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
}

.container{
    background: rgba(255,255,255,0.1);
    backdrop-filter: blur(15px);
    padding:50px;
    border-radius:25px;
    text-align:center;
    width:380px;
    box-shadow: 0 25px 50px rgba(0,0,0,0.4);
    animation: float 4s ease-in-out infinite;
}

@keyframes float {
    0%{transform:translateY(0);}
    50%{transform:translateY(-15px);}
    100%{transform:translateY(0);}
}

h1{
    font-size:30px;
    margin-bottom:10px;
}

.tagline{
    font-size:14px;
    opacity:0.9;
    margin-bottom:20px;
    min-height:20px;
}

.clock{
    font-size:32px;
    margin:20px 0;
    font-weight:bold;
    letter-spacing:2px;
}

.price{
    background:white;
    color:#111;
    padding:12px;
    border-radius:15px;
    font-weight:bold;
    margin-bottom:15px;
}

.stock{
    font-size:13px;
    margin-bottom:20px;
    color:#ffdd57;
}

button{
    padding:12px 25px;
    border:none;
    border-radius:30px;
    background:white;
    color:black;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    transform:scale(1.15) rotate(3deg);
    background:#ffdd57;
}

.message{
    margin-top:15px;
    font-size:14px;
}

.particle{
    position:absolute;
    width:6px;
    height:6px;
    background:white;
    border-radius:50%;
    opacity:0.7;
    animation: rise 10s linear infinite;
}

@keyframes rise {
    from{
        transform:translateY(100vh);
    }
    to{
        transform:translateY(-10vh);
    }
}

</style>
</head>
<body>

<div class="container">
    <h1>⏳ Time Inc.</h1>
    <div class="tagline" id="typing"></div>

    <div class="clock" id="clock"></div>

    <div class="price">💸 Price: Free hai enjoy karo</div>
    <div class="stock" id="stock"></div>

    <button onclick="buyTime()">Claim Unlimited Time</button>

    <div class="message" id="msg"></div>
</div>

<script>
// Live Clock
function updateClock(){
    const now = new Date();
    document.getElementById("clock").innerText = now.toLocaleTimeString();
}
setInterval(updateClock,1000);
updateClock();

// Fake stock counter
let stock = 7;
const stockEl = document.getElementById("stock");
stockEl.innerText = "⚠ Only " + stock + " minutes left in stock!";

setInterval(()=>{
    if(stock>1){
        stock--;
        stockEl.innerText = "⚠ Only " + stock + " minutes left in stock!";
    }else{
        stockEl.innerText = "😱 Time SOLD OUT... just kidding it's unlimited.";
    }
},3000);

// Typing Effect
const text = "We sell premium time to premium people.";
let i = 0;
function typing(){
    if(i < text.length){
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typing,40);
    }
}
typing();

// Buy button
function buyTime(){
    document.getElementById("msg").innerHTML =
    "🎉 Congratulations! You now own 24 hours daily. Use wisely. Or waste creatively.";
}

// Floating particles
for(let i=0;i<25;i++){
    let particle = document.createElement("div");
    particle.classList.add("particle");
    particle.style.left = Math.random()*100 + "vw";
    particle.style.animationDuration = (5 + Math.random()*5) + "s";
    particle.style.opacity = Math.random();
    document.body.appendChild(particle);
}
</script>

</body>
</html>

# Time-inc5
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Time™ Premium</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family: 'Segoe UI', sans-serif;
}

body{
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
  background: linear-gradient(-45deg, #0f2027, #203a43, #2c5364, #1c1c2b);
  background-size:400% 400%;
  animation: gradientMove 15s ease infinite;
}

@keyframes gradientMove{
  0%{background-position:0% 50%}
  50%{background-position:100% 50%}
  100%{background-position:0% 50%}
}

/* Floating Glow Orbs */
.orb{
  position:absolute;
  width:250px;
  height:250px;
  border-radius:50%;
  filter:blur(120px);
  opacity:0.5;
  animation: float 10s infinite alternate ease-in-out;
}

.orb1{
  background:#00f5ff;
  top:-100px;
  left:-100px;
}

.orb2{
  background:#ff00c8;
  bottom:-100px;
  right:-100px;
  animation-duration:12s;
}

@keyframes float{
  from{transform:translate(0,0)}
  to{transform:translate(150px,150px)}
}

/* Glass Card */
.card{
  position:relative;
  width:360px;
  padding:40px;
  border-radius:25px;
  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border:1px solid rgba(255,255,255,0.2);
  box-shadow:0 20px 50px rgba(0,0,0,0.5);
  text-align:center;
  color:white;
  animation: rise 4s ease-in-out infinite;
}

@keyframes rise{
  0%{transform:translateY(0)}
  50%{transform:translateY(-10px)}
  100%{transform:translateY(0)}
}

h1{
  font-size:30px;
  margin-bottom:10px;
}

.tagline{
  font-size:14px;
  opacity:0.8;
  margin-bottom:20px;
}

.clock{
  font-size:34px;
  letter-spacing:2px;
  margin:20px 0;
}

.price{
  background:white;
  color:#111;
  padding:10px;
  border-radius:15px;
  font-weight:bold;
  margin-bottom:20px;
}

button{
  padding:12px 25px;
  border:none;
  border-radius:25px;
  background: linear-gradient(45deg, #00f5ff, #ff00c8);
  color:white;
  font-weight:bold;
  cursor:pointer;
  transition:0.3s;
}

button:hover{
  transform:scale(1.1);
}

.message{
  margin-top:15px;
  font-size:14px;
  opacity:0.9;
}
</style>
</head>

<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>

<div class="card">
  <h1>⏳ Time™</h1>
  <div class="tagline">We sell premium time to premium people.</div>

  <div class="clock" id="clock"></div>

  <div class="price">💸 Price: Free hai enjoy karo</div>

  <button onclick="buyTime()">Claim Unlimited Time</button>

  <div class="message" id="msg"></div>
</div>

<script>
function updateClock(){
  const now = new Date();
  document.getElementById("clock").innerText = now.toLocaleTimeString();
}
setInterval(updateClock,1000);
updateClock();

function buyTime(){
  document.getElementById("msg").innerText =
  "🎉 Congratulations. You now own 24 hours daily. Use wisely. Or waste creatively.";
}
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Para ti Sunny 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:linear-gradient(135deg,#ff9a9e,#fad0c4);
  text-align:center;
  padding:20px;
}

.hidden{display:none;}

img{
  width:200px;
  margin:20px auto;
  display:block;
}

button{
  padding:15px 25px;
  font-size:18px;
  border:none;
  border-radius:12px;
  background:#ff6b81;
  color:white;
  margin-top:20px;
}

.buttons{
  position:relative;
  width:300px;
  height:200px;
  margin:30px auto;
}

#yes{
  position:absolute;
  left:50%;
  top:50%;
  transform:translate(-50%,-50%);
}

#no{
  position:absolute;
  background:#ccc;
}
</style>
</head>

<body>

<h1 id="title">Para ti Sunny 🌞💖</h1>

<audio id="music" loop>
  <source src="https://files.catbox.moe/3c7m8e.mp3" type="audio/mpeg">
</audio>

<div id="intro">
  <img src="https://i.imgur.com/9ZQZ0ZC.png">
  <p>Antes de decirte algo…</p>
  <button onclick="next1()">Continuar</button>
</div>

<div id="msg1" class="hidden">
  <p><b>Quiero decir que me encantas</b> 💕</p>
  <button onclick="next2()">Siguiente</button>
</div>

<div id="msg2" class="hidden">
  <p>A cada rato pienso en ti</p>
  <p>te extraño mucho 🥺</p>
  <button onclick="next3()">Siguiente</button>
</div>

<div id="msg3" class="hidden">
  <p>y ojalá vivieras</p>
  <p><b>más cerca de mí</b> 💘</p>
  <button onclick="showQuestion()">Continuar</button>
</div>

<div id="question" class="hidden">
  <h2>¿Quieres ser mi San Valentín? 💖</h2>
  <div class="buttons">
    <button id="yes">Sí 💕</button>
    <button id="no">No 🙈</button>
  </div>
</div>

<script>
const music=document.getElementById("music");

function next1(){
  music.play();
  document.getElementById("intro").classList.add("hidden");
  document.getElementById("msg1").classList.remove("hidden");
}

function next2(){
  document.getElementById("msg1").classList.add("hidden");
  document.getElementById("msg2").classList.remove("hidden");
}

function next3(){
  document.getElementById("msg2").classList.add("hidden");
  document.getElementById("msg3").classList.remove("hidden");
}

function showQuestion(){
  document.getElementById("msg3").classList.add("hidden");
  document.getElementById("question").classList.remove("hidden");
}

let yes=document.getElementById("yes");
let no=document.getElementById("no");
let scale=1;

no.onclick=()=>{
  scale+=0.15;
  yes.style.transform=`translate(-50%,-50%) scale(${scale})`;
  no.style.left=Math.random()*240+"px";
  no.style.top=Math.random()*140+"px";
};

yes.onclick=()=>{
  document.body.innerHTML=`
    <h1>💖💖💖</h1>
    <img src="https://i.imgur.com/9ZQZ0ZC.png">
    <h2>Sabía que dirías que sí, Sunny 😏</h2>
    <p>Feliz San Valentín 🌹</p>
  `;
  music.play();
};
</script>

</body>
</html>

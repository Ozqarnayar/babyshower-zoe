<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Baby Shower Zoé</title>

<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Montserrat:wght@300;500&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    font-family:'Montserrat', sans-serif;
    background:linear-gradient(to bottom, #ffd6e8, #ffffff);
    text-align:center;
    color:#8b4a6b;
    overflow-x:hidden;
}

/* Pantalla inicial */
#cover{
    position:fixed;
    width:100%;
    height:100%;
    background:#ffd6e8;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    z-index:1000;
}

#cover h1{
    font-family:'Pacifico', cursive;
    font-size:2.5em;
}

.open-btn{
    margin-top:20px;
    padding:15px 30px;
    background:#ff9ecb;
    color:white;
    border:none;
    border-radius:30px;
    font-size:1.2em;
}

/* Secciones */
.section{ padding:60px 20px; }

h1{
    font-family:'Pacifico', cursive;
    font-size:3em;
    animation:latido 2s infinite;
}
@keyframes latido{
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.05);}
}

.button{
    display:inline-block;
    padding:15px 30px;
    margin:15px;
    background:#ff9ecb;
    color:white;
    text-decoration:none;
    border-radius:30px;
    font-weight:bold;
    transition:0.3s;
}
.button:hover{
    background:#ff6fb3;
    transform:scale(1.1);
}

.countdown{
    font-size:1.4em;
    font-weight:bold;
}

/* Globos */
.balloon{
    position:fixed;
    bottom:-150px;
    width:40px;
    height:50px;
    background:#ffb6d9;
    border-radius:50%;
    animation:flotar 12s infinite;
}
.balloon:after{
    content:'';
    position:absolute;
    width:2px;
    height:40px;
    background:#aaa;
    left:50%;
    top:50px;
}
@keyframes flotar{
    from{transform:translateY(0);}
    to{transform:translateY(-110vh);}
}

/* Nubes */
.cloud{
    position:absolute;
    top:50px;
    width:120px;
    opacity:0.7;
    animation:nube 60s linear infinite;
}
@keyframes nube{
    from{left:-150px;}
    to{left:110%;}
}

/* Estrellas */
.star{
    position:fixed;
    width:5px;
    height:5px;
    background:white;
    border-radius:50%;
    animation:brillo 2s infinite alternate;
}
@keyframes brillo{
    from{opacity:0.3;}
    to{opacity:1;}
}

/* Abeja */
.bee{
    position:fixed;
    width:40px;
    animation:abeja 15s linear infinite;
}
@keyframes abeja{
    0%{left:-50px; top:30%;}
    50%{left:50%; top:45%;}
    100%{left:110%; top:35%;}
}
</style>
</head>

<body>

<!-- Pantalla de apertura -->
<div id="cover">
    <h1>Baby Shower Zoé</h1>
    <p>La dulce espera está por terminar</p>
    <button class="open-btn" onclick="openInvite()">Toca para abrir 💕</button>
</div>

<!-- Música -->
<audio id="music" loop>
  <source src="gimnasia.mp3" type="audio/mpeg">
</audio>

<!-- Decoraciones -->
<img src="https://i.imgur.com/V4RclNb.png" class="cloud">
<img src="https://i.imgur.com/9Xn4FZQ.png" class="bee">

<div class="balloon" style="left:10%; animation-duration:10s;"></div>
<div class="balloon" style="left:40%; animation-duration:13s;"></div>
<div class="balloon" style="left:70%; animation-duration:11s;"></div>

<div class="star" style="top:10%; left:20%;"></div>
<div class="star" style="top:30%; left:70%;"></div>
<div class="star" style="top:60%; left:40%;"></div>

<!-- Contenido -->
<div class="section">
    <h1>Zoé</h1>
</div>

<div class="section">
    <h2>📅 28 de marzo 2026</h2>
    <h2>🕒 4:40 PM</h2>
    <div class="countdown" id="countdown"></div>
</div>

<div class="section">
    <a class="button" href="https://maps.app.goo.gl/CfFLgyTNA2M7JLFj6?g_st=ic" target="_blank">
        📍 Ver Ubicación
    </a>
</div>

<div class="section">
    <a class="button" href="https://wa.me/525543700603" target="_blank">
        💌 Confirmar Asistencia
    </a>
</div>

<script>
function openInvite(){
    document.getElementById("cover").style.display="none";
    document.getElementById("music").play();
}

var eventDate = new Date("March 28, 2026 16:40:00").getTime();

setInterval(function(){
var now = new Date().getTime();
var distance = eventDate - now;

var days = Math.floor(distance / (1000 * 60 * 60 * 24));
var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));

document.getElementById("countdown").innerHTML =
"Faltan " + days + " días, " + hours + " horas y " + minutes + " minutos";

if(distance < 0){
document.getElementById("countdown").innerHTML = "¡Hoy es el gran día!";
}
},1000);
</script>

</body>
</html>

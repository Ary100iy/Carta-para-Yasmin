# <!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Yasmin ❤️</title>

<style>
body{
margin:0;
font-family:Georgia,serif;
height:100vh;
overflow:hidden;
background:linear-gradient(135deg,#ffb6c1,#ffd1dc,#fff0f5);
display:flex;
justify-content:center;
align-items:center;
}

/* ENVELOPE */
.container{
text-align:center;
z-index:5;
}

.envelope{
width:320px;
height:220px;
position:relative;
cursor:pointer;
transition:0.8s ease;
}

.back{
position:absolute;
width:100%;
height:100%;
background:#ff6fa3;
border-radius:12px;
}

.front{
position:absolute;
width:100%;
height:100%;
background:#ff8fb8;
clip-path:polygon(0 0,50% 55%,100% 0,100% 100%,0 100%);
transition:1s ease;
}

.envelope.open .front{
transform:translateY(-260px);
opacity:0;
pointer-events:none;
}

.seal{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
font-size:42px;
}

.text{
color:white;
font-weight:bold;
margin-top:15px;
}

/* CARTA */
.letter{
position:fixed;
inset:0;
display:flex;
justify-content:center;
align-items:center;
background:rgba(255,255,255,0.25);
backdrop-filter:blur(12px);
opacity:0;
visibility:hidden;
transition:1s;
padding:20px;
z-index:2;
}

.letter.show{
opacity:1;
visibility:visible;
}

.card{
background:white;
max-width:800px;
width:100%;
padding:40px;
border-radius:24px;
box-shadow:0 20px 60px rgba(0,0,0,0.25);
overflow:auto;
max-height:85vh;
animation:up 1s ease;
}

@keyframes up{
from{transform:translateY(40px);opacity:0;}
to{transform:translateY(0);opacity:1;}
}

h1{
color:#ff4f8b;
text-align:center;
margin-bottom:25px;
}

p{
font-size:18px;
line-height:1.9;
color:#444;
margin-bottom:14px;
}

.counter{
margin-top:25px;
padding:12px;
background:#fff0f5;
border-radius:12px;
color:#ff4f8b;
font-weight:bold;
text-align:center;
}

/* CORAÇÕES */
.heart{
position:fixed;
font-size:18px;
pointer-events:none;
left:0;
top:0;
animation:fall linear forwards;
}

@keyframes fall{
from{
transform:translateY(-10vh);
opacity:1;
}
to{
transform:translateY(110vh);
opacity:0;
}
}

/* SPOTIFY */
.music{
position:fixed;
bottom:15px;
right:15px;
width:320px;
height:152px;
opacity:0.95;
transition:0.8s ease;
z-index:10;
}

.music.hide{
opacity:0;
transform:translateY(40px);
pointer-events:none;
}
</style>
</head>

<body>

<!-- ENVELOPE -->
<div class="container" id="container">
<div class="envelope" id="envelope">
<div class="back"></div>
<div class="front"></div>
<div class="seal">💌</div>
</div>
<div class="text">Clique para abrir ❤️</div>
</div>

<!-- CARTA -->
<div class="letter" id="letter">
<div class="card">

<h1>Para Yasmin ❤️</h1>

<p>Meu amor,</p>

<p>
Eu talvez não fale isso tanto quanto deveria, mas você se tornou uma das partes mais importantes da minha vida. Você está nos meus pensamentos quando eu acordo, nas pequenas coisas que acontecem durante o dia e até nos momentos mais aleatórios. De alguma forma, você sempre encontra um jeito de aparecer na minha mente e deixar meu dia melhor.
</p>

<p>
Às vezes eu pareço meio fechado ou não demonstro tudo o que sinto da melhor forma. Nem sempre consigo transformar em palavras o que passa aqui dentro. Mas queria que você soubesse que isso nunca significou falta de sentimento. Muito pelo contrário. O que eu sinto por você é tão verdadeiro que, às vezes, parece impossível explicar.
</p>

<p>
Eu amo o seu jeito, suas manias, suas brincadeiras, suas implicâncias e até aqueles momentos em que você acha que está sendo chata, mas só consegue me fazer gostar ainda mais de você.
</p>

<p>
E se eu pudesse escolher uma coisa para ouvir todos os dias, seria a sua risada. Ela é linda, leve e contagiante.
</p>

<p>
Obrigado por cada momento. Eu escolho você todos os dias. ❤️
</p>

<p>
Eu te amo mais do que consigo colocar em palavras, Yasmin. 💖
</p>

<p>
Feliz Dia dos Namorados 💞
</p>

<p style="text-align:center;color:#ff4f8b;font-weight:bold;margin-top:18px;">
Nosso começo: 26/02/2025 💖
</p>

<div class="counter" id="counter"></div>

</div>
</div>

<!-- SPOTIFY -->
<iframe id="spotifyPlayer"
class="music"
src="https://open.spotify.com/embed/track/1De425SCFJULIHbcmeebUw"
frameborder="0"
allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
</iframe>

<script>

const envelope = document.getElementById("envelope");
const letter = document.getElementById("letter");
const container = document.getElementById("container");

envelope.addEventListener("click", () => {

envelope.classList.add("open");

setTimeout(() => {
container.style.display = "none";
letter.classList.add("show");

document.getElementById("spotifyPlayer").style.display = "none";

}, 900);

});

// contador
function updateCounter(){

const start = new Date("2025-02-26");
const now = new Date();

let diff = now - start;
let days = Math.floor(diff / (1000*60*60*24));

let years = Math.floor(days / 365);
days %= 365;

let months = Math.floor(days / 30);
days %= 30;

document.getElementById("counter").innerHTML =
`❤️ Juntos há ${years} ano(s), ${months} mês(es) e ${days} dia(s) ❤️`;
}

updateCounter();
setInterval(updateCounter,1000);

// corações
function heart(){

const h = document.createElement("div");
h.classList.add("heart");
h.innerHTML = "❤️";

h.style.left = Math.random() * 100 + "vw";
h.style.animationDuration = (Math.random() * 3 + 3) + "s";

document.body.appendChild(h);

set

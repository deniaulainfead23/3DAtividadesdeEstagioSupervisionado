Atividade 2 — Pegue a Estrela ⭐
Estrutura
pegue-a-estrela/
│
├── index.html
├── style.css
└── script.js
📄 index.html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <title>Pegue a Estrela</title>

    <link rel="stylesheet" href="style.css">
</head>

<body>

    <h1>⭐ Pegue a Estrela ⭐</h1>

    <div class="painel">

        <span>🏆 Pontos:
            <strong id="pontos">0</strong>
        </span>

        <span>⏱ Tempo:
            <strong id="tempo">30</strong>s
        </span>

    </div>

    <div id="areaJogo">

        <div id="estrela">
            ⭐
        </div>

    </div>

    <button onclick="iniciar()">
        ▶ Iniciar Jogo
    </button>

<script src="script.js"></script>

</body>

</html>
🎨 style.css
body{

    font-family:Arial;

    text-align:center;

    background:#dbeafe;

}

h1{

    color:#2563eb;

}

.painel{

    display:flex;

    justify-content:center;

    gap:40px;

    font-size:22px;

    margin:20px;

}

#areaJogo{

    width:700px;

    height:450px;

    background:white;

    margin:auto;

    border-radius:15px;

    border:4px solid #2563eb;

    position:relative;

    overflow:hidden;

}

#estrela{

    position:absolute;

    font-size:45px;

    cursor:pointer;

    user-select:none;

}

button{

    margin-top:20px;

    padding:15px 30px;

    font-size:18px;

    background:#2563eb;

    color:white;

    border:none;

    border-radius:10px;

}
⚙ script.js
let pontos=0;

let tempo=30;

let intervalo;

const estrela=document.getElementById("estrela");

function mover(){

let x=Math.random()*620;

let y=Math.random()*360;

estrela.style.left=x+"px";

estrela.style.top=y+"px";

}

estrela.onclick=function(){

pontos++;

document.getElementById("pontos").innerHTML=pontos;

mover();

}

function iniciar(){

pontos=0;

tempo=30;

document.getElementById("pontos").innerHTML=0;

document.getElementById("tempo").innerHTML=30;

mover();

clearInterval(intervalo);

intervalo=setInterval(function(){

tempo--;

document.getElementById("tempo").innerHTML=tempo;

if(tempo==0){

clearInterval(intervalo);

alert("Fim de jogo!\n\nSua pontuação foi: "+pontos);

}

},1000);

}
🎯 Desafio usando IA Generativa

Agora é sua vez de evoluir o projeto!

Utilize uma Inteligência Artificial Generativa para solicitar melhorias no jogo.

Sugestão de Prompt
Melhore este jogo desenvolvido em HTML, CSS e JavaScript.

Implemente as seguintes funcionalidades:

• faça a estrela mudar de cor;
• adicione sons ao clicar;
• crie níveis Fácil, Médio e Difícil;
• aumente a velocidade conforme a pontuação;
• adicione um recorde utilizando localStorage;
• coloque um fundo animado;
• adicione efeitos quando a estrela for clicada;
• exiba uma tela de "Fim de Jogo";
• mantenha o código organizado e comentado.

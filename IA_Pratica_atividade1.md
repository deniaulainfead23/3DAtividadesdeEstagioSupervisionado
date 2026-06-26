# Guia Prático – Atividade IA Prática 1  
## Crie seu Jogo Web com HTML + CSS + JavaScript + GitHub Pages

**Professora Denise Moraes**  
**Tema:** Usando Inteligência Artificial para transformar ideias em projetos reais.

---

## Objetivo da Atividade

Nesta atividade, você irá criar um **jogo web de perguntas e respostas** usando:

- HTML
- CSS
- JavaScript
- GitHub
- GitHub Pages
- Apoio de Inteligência Artificial Generativa

Ao final, seu jogo estará publicado na internet e poderá ser acessado por qualquer pessoa pelo navegador.

---

## O que será desenvolvido?

Um jogo chamado:

# Quiz Tech Challenge

O jogo terá:

- perguntas e respostas;
- pontuação;
- vidas;
- feedback de acerto e erro;
- tela final;
- botão para jogar novamente;
- publicação no GitHub Pages.

---

# 1. Planejamento do Jogo

Antes de programar, defina as regras.

## Tema do jogo

Perguntas sobre tecnologia, informática, internet, programação e inteligência artificial.

## Regras

- O jogador começa com 3 vidas.
- Cada acerto vale 10 pontos.
- Cada erro remove 1 vida.
- O jogo termina quando:
  - acabarem as perguntas; ou
  - acabarem as vidas.

---

# 2. Estrutura de Arquivos

Crie uma pasta chamada:

```text
quiz-tech-challenge
```

Dentro dela, crie três arquivos:

```text
index.html
style.css
script.js
```

A estrutura ficará assim:

```text
quiz-tech-challenge/
│
├── index.html
├── style.css
└── script.js
```

---

# 3. Código do Arquivo index.html

Crie o arquivo **index.html** e cole:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Quiz Tech Challenge</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <main class="container">

    <section class="card">

      <h1>Quiz Tech Challenge</h1>
      <p class="subtitulo">Teste seus conhecimentos em tecnologia!</p>

      <div class="info">
        <span>Pontos: <strong id="pontos">0</strong></span>
        <span>Vidas: <strong id="vidas">❤️❤️❤️</strong></span>
      </div>

      <div id="pergunta" class="pergunta">
        Carregando pergunta...
      </div>

      <div id="opcoes" class="opcoes"></div>

      <p id="mensagem" class="mensagem"></p>

      <button id="proxima" onclick="proximaPergunta()" disabled>
        Próxima
      </button>

      <button id="reiniciar" onclick="reiniciarJogo()" class="oculto">
        Jogar novamente
      </button>

    </section>

  </main>

  <script src="script.js"></script>
</body>
</html>
```

---

# 4. Código do Arquivo style.css

Crie o arquivo **style.css** e cole:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #667eea, #764ba2);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #222;
}

.container {
  width: 100%;
  max-width: 600px;
  padding: 20px;
}

.card {
  background: white;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.25);
  text-align: center;
}

h1 {
  color: #1e3a8a;
  margin-bottom: 10px;
}

.subtitulo {
  margin-bottom: 20px;
  color: #555;
}

.info {
  display: flex;
  justify-content: space-between;
  background: #f1f5f9;
  padding: 12px;
  border-radius: 12px;
  margin-bottom: 20px;
}

.pergunta {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 20px;
}

.opcoes {
  display: grid;
  gap: 10px;
}

.opcoes button {
  background: #e5e7eb;
  border: none;
  padding: 14px;
  border-radius: 12px;
  cursor: pointer;
  font-size: 16px;
}

.opcoes button:hover {
  background: #c7d2fe;
}

.correta {
  background: #22c55e !important;
  color: white;
}

.errada {
  background: #ef4444 !important;
  color: white;
}

.mensagem {
  margin: 18px 0;
  font-weight: bold;
}

button {
  background: #2563eb;
  color: white;
  border: none;
  padding: 14px 20px;
  border-radius: 12px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 10px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.oculto {
  display: none;
}
```

---

# 5. Código do Arquivo script.js

Crie o arquivo **script.js** e cole:

```javascript
const perguntas = [
  {
    pergunta: "Qual linguagem é usada para criar a estrutura de uma página web?",
    opcoes: ["CSS", "HTML", "JavaScript", "Python"],
    resposta: "HTML"
  },
  {
    pergunta: "Qual linguagem é usada para estilizar uma página web?",
    opcoes: ["HTML", "CSS", "SQL", "Java"],
    resposta: "CSS"
  },
  {
    pergunta: "Qual linguagem adiciona interatividade a uma página web?",
    opcoes: ["JavaScript", "HTML", "Excel", "PowerPoint"],
    resposta: "JavaScript"
  },
  {
    pergunta: "O que significa IA?",
    opcoes: ["Internet Aberta", "Inteligência Artificial", "Interface Automática", "Informação Analógica"],
    resposta: "Inteligência Artificial"
  },
  {
    pergunta: "Qual plataforma permite publicar sites gratuitamente usando repositórios?",
    opcoes: ["GitHub Pages", "WhatsApp", "Word", "Paint"],
    resposta: "GitHub Pages"
  }
];

let indiceAtual = 0;
let pontos = 0;
let vidas = 3;
let respondeu = false;

function carregarPergunta() {
  respondeu = false;

  document.getElementById("mensagem").textContent = "";
  document.getElementById("proxima").disabled = true;

  const perguntaAtual = perguntas[indiceAtual];

  document.getElementById("pergunta").textContent = perguntaAtual.pergunta;

  const opcoesDiv = document.getElementById("opcoes");
  opcoesDiv.innerHTML = "";

  perguntaAtual.opcoes.forEach(opcao => {
    const botao = document.createElement("button");
    botao.textContent = opcao;
    botao.onclick = () => verificarResposta(botao, opcao);
    opcoesDiv.appendChild(botao);
  });

  atualizarInfo();
}

function verificarResposta(botao, opcaoEscolhida) {
  if (respondeu) return;

  respondeu = true;

  const perguntaAtual = perguntas[indiceAtual];
  const botoes = document.querySelectorAll("#opcoes button");

  botoes.forEach(b => {
    b.disabled = true;

    if (b.textContent === perguntaAtual.resposta) {
      b.classList.add("correta");
    }
  });

  if (opcaoEscolhida === perguntaAtual.resposta) {
    pontos += 10;
    document.getElementById("mensagem").textContent = "✅ Resposta correta! +10 pontos";
  } else {
    vidas--;
    botao.classList.add("errada");
    document.getElementById("mensagem").textContent = "❌ Resposta errada! Você perdeu uma vida.";
  }

  atualizarInfo();

  if (vidas <= 0) {
    finalizarJogo();
  } else {
    document.getElementById("proxima").disabled = false;
  }
}

function proximaPergunta() {
  indiceAtual++;

  if (indiceAtual >= perguntas.length) {
    finalizarJogo();
  } else {
    carregarPergunta();
  }
}

function atualizarInfo() {
  document.getElementById("pontos").textContent = pontos;

  let coracoes = "";
  for (let i = 0; i < vidas; i++) {
    coracoes += "❤️";
  }

  document.getElementById("vidas").textContent = coracoes || "💔";
}

function finalizarJogo() {
  document.getElementById("pergunta").textContent = "Fim de jogo!";
  document.getElementById("opcoes").innerHTML = "";
  document.getElementById("mensagem").textContent = `Sua pontuação final foi: ${pontos} pontos.`;

  document.getElementById("proxima").classList.add("oculto");
  document.getElementById("reiniciar").classList.remove("oculto");
}

function reiniciarJogo() {
  indiceAtual = 0;
  pontos = 0;
  vidas = 3;

  document.getElementById("proxima").classList.remove("oculto");
  document.getElementById("reiniciar").classList.add("oculto");

  carregarPergunta();
}

carregarPergunta();
```

---

# 6. Teste Local

Abra o arquivo:

```text
index.html
```

no navegador.

Verifique:

- As perguntas aparecem?
- A pontuação funciona?
- As vidas diminuem?
- O botão Próxima funciona?
- O fim de jogo aparece?

Se algo não funcionar, revise os nomes dos arquivos:

```text
index.html
style.css
script.js
```

Eles devem estar na mesma pasta.

---

# 7. Melhorias com Inteligência Artificial

Depois que o jogo funcionar, use uma IA generativa para pedir melhorias.

Exemplo de prompt:

```text
Melhore este jogo de perguntas e respostas em HTML, CSS e JavaScript.

Adicione:
- mais perguntas;
- ranking;
- sons de acerto e erro;
- cronômetro;
- tela inicial;
- níveis de dificuldade;
- salvamento de recorde no localStorage;
- visual mais moderno.

Mantenha o código simples para estudantes iniciantes.
```

---

# 8. Criar Conta no GitHub

Acesse:

```text
https://github.com
```

Crie uma conta ou faça login.

---

# 9. Criar Repositório

Clique em:

```text
New repository
```

Nome sugerido:

```text
quiz-tech-challenge
```

Marque:

```text
Public
```

Clique:

```text
Create repository
```

---

# 10. Enviar os Arquivos para o GitHub

No repositório, clique:

```text
Add file
```

Depois:

```text
Upload files
```

Envie:

```text
index.html
style.css
script.js
```

Depois clique:

```text
Commit changes
```

---

# 11. Ativar o GitHub Pages

No repositório, acesse:

```text
Settings
```

Depois:

```text
Pages
```

Em **Source**, selecione:

```text
Deploy from a branch
```

Em **Branch**, escolha:

```text
main
```

Em pasta, escolha:

```text
/root
```

Clique:

```text
Save
```

---

# 12. Acessar o Jogo Publicado

Após alguns minutos, o GitHub irá gerar um link parecido com:

```text
https://seuusuario.github.io/quiz-tech-challenge/
```

Esse será o endereço público do seu jogo.

---

# 13. Entrega da Atividade

Entregar:

- link do repositório GitHub;
- link do jogo no GitHub Pages;
- print da tela inicial;
- print da tela de pontuação final.

---

# 14. Desafio Extra

Vale ponto bônus se adicionar:

- cronômetro;
- ranking;
- tema escuro;
- tela inicial;
- efeitos sonoros;
- perguntas aleatórias;
- animações;
- perguntas por categoria.

---

# Checklist Final

- [ ] Criei a pasta do projeto.
- [ ] Criei o arquivo index.html.
- [ ] Criei o arquivo style.css.
- [ ] Criei o arquivo script.js.
- [ ] Testei localmente.
- [ ] Criei repositório no GitHub.
- [ ] Enviei os arquivos.
- [ ] Ativei GitHub Pages.
- [ ] Copiei o link público.
- [ ] Entreguei a atividade.

---

## Rodapé

**Guia Prático – Atividade usando HTML + CSS + JavaScript + GitHub Pages**  
**Professora Denise Moraes**  
**Criado com apoio de Inteligência Artificial Generativa**

---------------------------------------------------------------------------------------------------------------------------------------------------------

Reflexão da Atividade

1. Explique, com suas palavras, qual é a função de cada tecnologia utilizada no projeto.

HTML:
CSS:
JavaScript:

2. Qual foi a principal contribuição da Inteligência Artificial durante o desenvolvimento do jogo? Ela substituiu o programador? Justifique sua resposta.

3. Após publicar o projeto no GitHub Pages, qual é a principal vantagem de disponibilizar seu jogo na internet?

4. Qual estrutura de repetição (ou repetição implícita) você acredita que foi utilizada para exibir todas as alternativas de cada pergunta? Explique sua resposta.

5. O que é uma variável? Cite duas variáveis utilizadas no projeto e explique a função de cada uma.

6. Qual é a função das functions (funções) no JavaScript? Cite uma função utilizada no projeto e explique sua finalidade.

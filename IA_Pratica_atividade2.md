# 🚀 IA PRÁTICA – ATIVIDADE 2

# **ContaCerta PWA**

## Transformando uma Página Web em um Aplicativo Instalável para Windows e Celular

**Professora Denise Moraes**

---

# 🎯 Objetivo

Nesta atividade você irá desenvolver uma **Progressive Web App (PWA)** chamada **ContaCerta**, uma agenda financeira inteligente que poderá ser instalada no **Windows**, **Android**, **tablet** e utilizada como um aplicativo real.

Durante o desenvolvimento você utilizará:

* HTML5
* CSS3
* JavaScript
* Progressive Web App (PWA)
* GitHub
* GitHub Pages
* Inteligência Artificial Generativa

Ao final da atividade seu projeto poderá ser instalado diretamente pelo navegador, funcionando como um aplicativo.

---

# 📚 O que é uma PWA?

Uma **Progressive Web App (PWA)** é uma aplicação desenvolvida utilizando tecnologias Web que pode ser instalada como um aplicativo tradicional.

Entre suas vantagens estão:

✅ Instalação sem necessidade de loja de aplicativos

✅ Funcionamento em Windows, Android, Linux e macOS

✅ Atualizações automáticas

✅ Layout responsivo

✅ Possibilidade de funcionamento offline

---

# 💡 Projeto

## Nome

**ContaCerta**

## Slogan

> *"Você não vai ter dívidas se cuidar das suas contas."*

---

# 🗂 Estrutura do Projeto

Crie uma pasta chamada:

```text
contacerta-pwa
```

Dentro dela crie os seguintes arquivos:

```text
contacerta-pwa/
│
├── index.html
├── style.css
├── script.js
├── manifest.json
├── service-worker.js
└── icons/
      ├── icon-192.png
      └── icon-512.png
```

---

# 🧱 Etapa 1 — Criando a Interface (index.html)

O arquivo **index.html** será responsável pela estrutura do aplicativo.

Sua interface deverá conter:

* Logo do ContaCerta
* Nome do aplicativo
* Formulário para cadastro de contas
* Lista das contas cadastradas
* Dashboard financeiro
* Menu superior
* Botões de ação

Campos mínimos:

* Descrição
* Categoria
* Valor
* Data de vencimento
* Forma de pagamento
* Status

---

# 🎨 Etapa 2 — Criando o Visual (style.css)

Desenvolva um layout moderno inspirado em aplicativos financeiros.

Utilize a seguinte paleta:

🔵 Azul — cor principal

🟢 Verde — contas pagas

🟠 Laranja — alertas

🔴 Vermelho — contas vencidas

⚪ Branco — fundo

O aplicativo deve lembrar uma agenda financeira organizada.

---

# ⚙️ Etapa 3 — Criando a Lógica (script.js)

Implemente as seguintes funcionalidades:

✔ Cadastro de contas

✔ Exclusão de contas

✔ Marcar conta como paga

✔ Listagem automática

✔ Resumo financeiro

✔ Total de gastos do mês

✔ Identificação de contas vencidas

✔ Armazenamento utilizando **localStorage**

---

# 📱 Etapa 4 — Transformando em PWA (manifest.json)

Crie o arquivo **manifest.json** contendo:

* Nome do aplicativo
* Nome curto
* Descrição
* Cor principal
* Cor do tema
* Página inicial
* Ícones
* Display: standalone

Esse arquivo permitirá que o navegador reconheça o projeto como um aplicativo instalável.

---

# 🌐 Etapa 5 — Funcionamento Offline (service-worker.js)

Implemente um **Service Worker**.

Ele deverá armazenar em cache:

* index.html
* style.css
* script.js
* manifest.json
* ícones

Assim o aplicativo continuará funcionando mesmo sem conexão com a internet para visualizar os dados locais.

---

# 🧪 Etapa 6 — Testando Localmente

Abra o arquivo:

```text
index.html
```

Realize os seguintes testes:

✅ Cadastro de conta

✅ Listagem

✅ Marcar como paga

✅ Contas vencidas

✅ Total do mês

✅ Atualização automática

---

# ☁️ Etapa 7 — Publicando na Internet

Publique seu projeto utilizando uma das plataformas abaixo:

* GitHub Pages
* Netlify
* Vercel

Após a publicação, copie o endereço do seu aplicativo.

---

# 💻 Etapa 8 — Instalando no Windows

Abra o aplicativo utilizando:

* Google Chrome
* Microsoft Edge

Depois clique em:

**Menu → Aplicativos → Instalar este site como aplicativo**

ou

Clique no ícone de instalação exibido na barra de endereço.

Após a instalação, o **ContaCerta** aparecerá no Menu Iniciar do Windows como um aplicativo.

---

# 🤖 CODIGOS

index.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ContaCerta PWA</title>
  <link rel="stylesheet" href="style.css" />
  <link rel="manifest" href="manifest.json" />
  <meta name="theme-color" content="#0f62fe" />
</head>
<body>
  <header>
    <h1>ContaCerta</h1>
    <p>Você não vai ter dívidas se cuidar das suas contas.</p>
  </header>

  <main>
    <section class="resumo">
      <div class="card">
        <h3>Total do mês</h3>
        <p id="totalMes">R$ 0,00</p>
      </div>
      <div class="card verde">
        <h3>Pagas</h3>
        <p id="totalPago">R$ 0,00</p>
      </div>
      <div class="card laranja">
        <h3>Em aberto</h3>
        <p id="totalAberto">R$ 0,00</p>
      </div>
      <div class="card vermelho">
        <h3>Vencidas</h3>
        <p id="totalVencido">R$ 0,00</p>
      </div>
    </section>

    <section class="formulario">
      <h2>Nova Conta</h2>

      <input type="text" id="descricao" placeholder="Descrição da conta" />

      <select id="categoria">
        <option>Moradia</option>
        <option>Água</option>
        <option>Luz</option>
        <option>Internet</option>
        <option>Mercado</option>
        <option>Saúde</option>
        <option>Educação</option>
        <option>Transporte</option>
        <option>Cartão de Crédito</option>
        <option>Outros</option>
      </select>

      <input type="number" id="valor" placeholder="Valor" step="0.01" />

      <input type="date" id="vencimento" />

      <select id="forma">
        <option>Pix</option>
        <option>Boleto</option>
        <option>Cartão de Crédito</option>
        <option>Cartão de Débito</option>
        <option>Dinheiro</option>
        <option>Débito Automático</option>
        <option>Transferência</option>
        <option>Outro</option>
      </select>

      <button onclick="adicionarConta()">Adicionar Conta</button>
    </section>

    <section class="lista">
      <h2>Minhas Contas</h2>
      <div id="listaContas"></div>
    </section>
  </main>

  <footer>
    <p>Professora Denise Moraes • Atividade com IA Generativa</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
style.css
* {
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}

body {
  margin: 0;
  background: #f4f8fb;
  color: #1f2937;
}

header {
  background: linear-gradient(135deg, #0f62fe, #22c55e);
  color: white;
  text-align: center;
  padding: 28px 16px;
}

header h1 {
  margin: 0;
  font-size: 2.2rem;
}

header p {
  margin: 8px 0 0;
}

main {
  width: 95%;
  max-width: 1000px;
  margin: 20px auto;
}

.resumo {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 16px;
  margin-bottom: 20px;
}

.card,
.formulario,
.lista {
  background: white;
  padding: 18px;
  border-radius: 16px;
  box-shadow: 0 8px 18px rgba(0, 0, 0, 0.08);
}

.card h3 {
  margin: 0;
  color: #475569;
}

.card p {
  font-size: 1.4rem;
  font-weight: bold;
  color: #0f62fe;
}

.verde p {
  color: #22c55e;
}

.laranja p {
  color: #f97316;
}

.vermelho p {
  color: #dc2626;
}

input,
select,
button {
  width: 100%;
  padding: 13px;
  margin: 8px 0;
  border: 1px solid #cbd5e1;
  border-radius: 10px;
  font-size: 1rem;
}

button {
  background: #0f62fe;
  color: white;
  font-weight: bold;
  cursor: pointer;
  border: none;
}

button:hover {
  background: #0842a0;
}

.conta {
  border-left: 6px solid #0f62fe;
  background: #f8fafc;
  padding: 14px;
  margin: 12px 0;
  border-radius: 12px;
}

.conta.paga {
  border-left-color: #22c55e;
}

.conta.vencida {
  border-left-color: #dc2626;
}

.conta h3 {
  margin: 0 0 8px;
}

.acoes {
  display: flex;
  gap: 8px;
  margin-top: 10px;
}

.acoes button {
  flex: 1;
  margin: 0;
}

.btn-pago {
  background: #22c55e;
}

.btn-excluir {
  background: #dc2626;
}

footer {
  text-align: center;
  color: #64748b;
  padding: 20px;
}

@media (max-width: 600px) {
  header h1 {
    font-size: 1.7rem;
  }

  .acoes {
    flex-direction: column;
  }
}
script.js
let contas = JSON.parse(localStorage.getItem("contas")) || [];

function salvarLocalStorage() {
  localStorage.setItem("contas", JSON.stringify(contas));
}

function formatarMoeda(valor) {
  return Number(valor).toLocaleString("pt-BR", {
    style: "currency",
    currency: "BRL"
  });
}

function adicionarConta() {
  const descricao = document.getElementById("descricao").value;
  const categoria = document.getElementById("categoria").value;
  const valor = Number(document.getElementById("valor").value);
  const vencimento = document.getElementById("vencimento").value;
  const forma = document.getElementById("forma").value;

  if (!descricao || !valor || !vencimento) {
    alert("Preencha descrição, valor e vencimento.");
    return;
  }

  const conta = {
    id: Date.now(),
    descricao,
    categoria,
    valor,
    vencimento,
    forma,
    status: "Aberto"
  };

  contas.push(conta);
  salvarLocalStorage();
  limparFormulario();
  listarContas();
  atualizarResumo();
}

function limparFormulario() {
  document.getElementById("descricao").value = "";
  document.getElementById("valor").value = "";
  document.getElementById("vencimento").value = "";
}

function listarContas() {
  const lista = document.getElementById("listaContas");
  lista.innerHTML = "";

  if (contas.length === 0) {
    lista.innerHTML = "<p>Nenhuma conta cadastrada.</p>";
    return;
  }

  contas.forEach(conta => {
    const vencida = verificarVencida(conta);
    const div = document.createElement("div");

    div.className = "conta";

    if (conta.status === "Pago") {
      div.classList.add("paga");
    } else if (vencida) {
      div.classList.add("vencida");
    }

    div.innerHTML = `
      <h3>${conta.descricao}</h3>
      <p><strong>Categoria:</strong> ${conta.categoria}</p>
      <p><strong>Valor:</strong> ${formatarMoeda(conta.valor)}</p>
      <p><strong>Vencimento:</strong> ${formatarData(conta.vencimento)}</p>
      <p><strong>Forma:</strong> ${conta.forma}</p>
      <p><strong>Status:</strong> ${vencida && conta.status !== "Pago" ? "Vencida" : conta.status}</p>

      <div class="acoes">
        <button class="btn-pago" onclick="marcarComoPaga(${conta.id})">Marcar como paga</button>
        <button class="btn-excluir" onclick="excluirConta(${conta.id})">Excluir</button>
      </div>
    `;

    lista.appendChild(div);
  });
}

function marcarComoPaga(id) {
  contas = contas.map(conta => {
    if (conta.id === id) {
      conta.status = "Pago";
    }
    return conta;
  });

  salvarLocalStorage();
  listarContas();
  atualizarResumo();
}

function excluirConta(id) {
  if (confirm("Deseja excluir esta conta?")) {
    contas = contas.filter(conta => conta.id !== id);
    salvarLocalStorage();
    listarContas();
    atualizarResumo();
  }
}

function verificarVencida(conta) {
  const hoje = new Date();
  const vencimento = new Date(conta.vencimento + "T00:00:00");

  hoje.setHours(0, 0, 0, 0);

  return vencimento < hoje && conta.status !== "Pago";
}

function atualizarResumo() {
  const hoje = new Date();
  const mesAtual = hoje.getMonth();
  const anoAtual = hoje.getFullYear();

  let totalMes = 0;
  let totalPago = 0;
  let totalAberto = 0;
  let totalVencido = 0;

  contas.forEach(conta => {
    const dataConta = new Date(conta.vencimento + "T00:00:00");

    if (
      dataConta.getMonth() === mesAtual &&
      dataConta.getFullYear() === anoAtual
    ) {
      totalMes += conta.valor;

      if (conta.status === "Pago") {
        totalPago += conta.valor;
      } else if (verificarVencida(conta)) {
        totalVencido += conta.valor;
      } else {
        totalAberto += conta.valor;
      }
    }
  });

  document.getElementById("totalMes").textContent = formatarMoeda(totalMes);
  document.getElementById("totalPago").textContent = formatarMoeda(totalPago);
  document.getElementById("totalAberto").textContent = formatarMoeda(totalAberto);
  document.getElementById("totalVencido").textContent = formatarMoeda(totalVencido);
}

function formatarData(data) {
  return new Date(data + "T00:00:00").toLocaleDateString("pt-BR");
}

if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("service-worker.js");
}

listarContas();
atualizarResumo();
manifest.json
{
  "name": "ContaCerta",
  "short_name": "ContaCerta",
  "description": "Agenda financeira para controle de contas.",
  "start_url": "./index.html",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#0f62fe",
  "orientation": "portrait",
  "icons": [
    {
      "src": "icons/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icons/icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
service-worker.js
const CACHE_NAME = "contacerta-cache-v1";

const ARQUIVOS = [
  "./",
  "./index.html",
  "./style.css",
  "./script.js",
  "./manifest.json",
  "./icons/icon-192.png",
  "./icons/icon-512.png"
];

self.addEventListener("install", evento => {
  evento.waitUntil(
    caches.open(CACHE_NAME).then(cache => {
      return cache.addAll(ARQUIVOS);
    })
  );
});

self.addEventListener("fetch", evento => {
  evento.respondWith(
    caches.match(evento.request).then(resposta => {
      return resposta || fetch(evento.request);
    })
  );
});


---

# 📦 Entrega da Atividade

O aluno deverá entregar:

✅ Link do repositório GitHub

✅ Link do GitHub Pages (ou Netlify/Vercel)

✅ Print do aplicativo funcionando

✅ Print do aplicativo instalado no Windows

✅ Respostas das questões de reflexão

---

# 📝 Questões de Reflexão

**1.** O que é uma Progressive Web App (PWA) e quais vantagens ela oferece em relação a uma página Web tradicional?

---

**2.** Qual é a função do arquivo **manifest.json** dentro de uma PWA?

---

**3.** Explique a função do **service-worker.js** e como ele contribui para o funcionamento offline da aplicação.

---

**4.** Por que foi utilizado o **localStorage** neste projeto? Quais são suas vantagens e limitações?

---

**5.** De que forma a Inteligência Artificial Generativa contribuiu para acelerar ou melhorar o desenvolvimento desta atividade?

---

**6.** Cite pelo menos **três melhorias** que poderiam transformar o ContaCerta em um sistema profissional.

---

# ⭐ Desafio Extra

Implemente uma ou mais funcionalidades abaixo:

* 🌙 Modo Escuro
* 📊 Dashboard com gráficos
* 📅 Calendário financeiro
* 🔔 Alertas de vencimento
* 📤 Exportação para CSV
* 📥 Importação de dados
* 📱 Notificações
* ☁️ Sincronização com banco de dados (Supabase/Firebase)

---

# ✅ Resultado Esperado

Ao concluir esta atividade você será capaz de:

* Desenvolver uma aplicação Web completa;
* Transformá-la em uma Progressive Web App (PWA);
* Instalar seu projeto como aplicativo no Windows e Android;
* Publicar aplicações utilizando GitHub Pages;
* Utilizar Inteligência Artificial como apoio ao desenvolvimento de software.

---

## 🎓 Professora Denise Moraes

**Atividade desenvolvida com apoio de Inteligência Artificial Generativa.**

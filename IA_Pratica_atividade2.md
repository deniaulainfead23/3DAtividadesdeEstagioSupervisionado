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

# 🤖 Prompt para IA Generativa

Utilize este prompt para auxiliar no desenvolvimento:

> Crie uma aplicação PWA chamada **ContaCerta** utilizando HTML, CSS e JavaScript puro.
>
> O aplicativo deve funcionar como uma agenda financeira instalável.
>
> Permita cadastrar contas contendo:
>
> * descrição
> * valor
> * categoria
> * vencimento
> * forma de pagamento
> * status
>
> Utilize localStorage para persistência dos dados.
>
> Desenvolva uma interface moderna, responsiva e amigável.
>
> Crie automaticamente:
>
> * index.html
> * style.css
> * script.js
> * manifest.json
> * service-worker.js
>
> O aplicativo deve funcionar como PWA instalada no Windows e Android.

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

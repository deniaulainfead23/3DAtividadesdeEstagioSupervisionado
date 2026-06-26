# 🎮 IA Prática – Atividade 2

# **Mini Campo Minado**

## Aprendendo Matrizes, Loops e Eventos com HTML, CSS e JavaScript

**Professora Denise Moraes**

---

# 🎯 Objetivo

Nesta atividade você desenvolverá uma versão simplificada do clássico **Campo Minado**, utilizando **HTML**, **CSS** e **JavaScript**.

Ao concluir esta atividade você será capaz de:

* Criar interfaces utilizando HTML;
* Aplicar estilos utilizando CSS;
* Manipular elementos da página com JavaScript;
* Trabalhar com matrizes (arrays bidimensionais);
* Utilizar estruturas de repetição (`for`);
* Implementar eventos de clique;
* Alterar classes CSS dinamicamente.

---

# 📚 O que é o Campo Minado?

O Campo Minado é um jogo clássico de lógica.

O objetivo é abrir todas as casas do tabuleiro **sem clicar em uma mina**.

Cada casa aberta pode indicar quantas minas existem ao seu redor, permitindo ao jogador utilizar o raciocínio lógico para encontrar um caminho seguro.

Nesta atividade construiremos uma versão simplificada para compreender os principais conceitos de programação Web.

---

# 🧠 O que você irá aprender?

## HTML

* Estrutura de páginas
* `<div>`
* Botões
* Organização da interface

## CSS

* Grid Layout
* Classes CSS
* Cores
* Estados visuais
* Hover
* Responsividade

## JavaScript

* Variáveis
* Funções
* Matrizes
* Estruturas de repetição (`for`)
* Eventos (`click`)
* Manipulação do DOM
* `Math.random()`

---

# 🎮 O que será desenvolvido?

Seu jogo deverá possuir:

* 🎯 Tabuleiro **5 × 5**
* 💣 Cinco minas distribuídas aleatoriamente
* 😀 Contador de casas abertas
* 😵 Tela de **Game Over**
* 🏆 Tela de **Vitória**
* 🔄 Botão **Reiniciar Jogo**

---

# 📂 Estrutura do Projeto

Crie uma pasta chamada:

```text
campo-minado
```

Dentro dela crie os arquivos abaixo:

```text
campo-minado/
│
├── index.html
├── style.css
└── script.js
```

---

# 🛠️ Etapa 1 — Criando a Interface

Crie o arquivo:

```text
index.html
```

Ele será responsável por construir toda a estrutura do jogo.

A interface deverá conter:

* Título do jogo;
* Área do tabuleiro;
* Contador de casas abertas;
* Mensagem de vitória ou derrota;
* Botão **Reiniciar**.

---

# 🎨 Etapa 2 — Criando o Visual

Crie o arquivo:

```text
style.css
```

Utilize um visual agradável, inspirado no jogo clássico.

Sugestão de cores:

🟦 Azul → Casas fechadas

⬜ Branco → Casas abertas

🟥 Vermelho → Mina encontrada

🟩 Verde → Vitória

O tabuleiro deverá utilizar **CSS Grid** para organizar automaticamente as 25 casas.

---

# ⚙️ Etapa 3 — Programando o Jogo

Crie o arquivo:

```text
script.js
```

O JavaScript será responsável por:

* criar a matriz do tabuleiro;
* distribuir as minas aleatoriamente;
* abrir as casas quando clicadas;
* detectar vitória;
* detectar derrota;
* reiniciar o jogo.

---

# 🧪 Etapa 4 — Testando

Abra o arquivo:

```text
index.html
```

Verifique se:

* ✅ O tabuleiro aparece corretamente;
* ✅ As minas são distribuídas aleatoriamente;
* ✅ O clique abre uma casa;
* ✅ O jogo identifica derrota;
* ✅ O jogo identifica vitória;
* ✅ O botão Reiniciar funciona corretamente.

---

# 🤖 Etapa 5 — Melhorando com IA

O jogo deverá estar **100% funcional** antes de utilizar uma Inteligência Artificial.

Depois disso, utilize uma IA apenas para implementar **pequenas melhorias**.

Sugestões:

* ⏱️ Adicionar cronômetro;
* 🚩 Criar bandeiras para marcar minas;
* 🔊 Inserir sons simples;
* 🎨 Melhorar as cores do tabuleiro;
* ✨ Adicionar pequenas animações;
* 💾 Salvar o recorde utilizando `localStorage`.

### Exemplo de Prompt

```text
Melhore este jogo de Campo Minado desenvolvido em HTML, CSS e JavaScript.

Não altere sua estrutura principal.

Implemente apenas:

- cronômetro;
- bandeiras;
- sons simples;
- pequenas animações;
- comentários explicando o código.

Mantenha o projeto simples e adequado para estudantes iniciantes.
```

---

# 📝 Questões de Reflexão

**1.** Explique a função de cada tecnologia utilizada no projeto.

* HTML:
* CSS:
* JavaScript:

---

**2.** Como a matriz foi utilizada para representar o tabuleiro do jogo?

---

**3.** Qual estrutura de repetição foi utilizada para criar as casas do tabuleiro? Explique sua finalidade.

---

**4.** Como os eventos de clique permitiram a interação do jogador com o jogo?

---

**5.** Qual é a função das classes CSS no projeto? Cite um exemplo utilizado.

---

**6.** Como a Inteligência Artificial Generativa contribuiu para melhorar o projeto sem alterar sua estrutura principal?

---

# ⭐ Desafio (Opcional – Vale ponto extra)

Utilize uma IA Generativa para implementar **duas melhorias** no jogo e descreva:

* Quais funcionalidades foram adicionadas;
* Como a IA auxiliou no desenvolvimento;
* Quais alterações foram realizadas no código.

---

## 👩‍🏫 Professora Denise Moraes

**Atividade desenvolvida com apoio de Inteligência Artificial Generativa.**

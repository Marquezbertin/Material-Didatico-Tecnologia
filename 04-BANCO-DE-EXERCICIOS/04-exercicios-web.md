# EX-W4 — Banco de Exercícios: HTML, CSS e JavaScript (13–17 anos)

**Trilha:** Adolescentes [B5 — Web: HTML, CSS e JavaScript](../02-ADOLESCENTES-13-17/05-web.md) ·
[B6 — Banco de Dados e SQL](../02-ADOLESCENTES-13-17/06-banco-de-dados-sql.md) ·
Adultos [03 — Git e GitHub profissional](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md) (publicação no GitHub Pages)

| Item | Descrição |
|---|---|
| **Faixa etária** | 13 a 17 anos (revisão rápida para 18+) |
| **Nº de itens** | 18 — HTML (6), CSS (6), JavaScript (6) |
| **Nível** | ⭐ Fácil (7 itens) · ⭐⭐ Médio (7 itens) · ⭐⭐⭐ Difícil (4 itens) |
| **Tempo estimado** | 70 a 90 min (3 a 5 min por item, mais 15 min de teste no navegador) |
| **Formato** | Enunciado com código e **gabarito com o trecho de código correto** |

> ⚠️ **Licença de uso:** material livre, sob a licença **CC BY 4.0** (Creative Commons
> Atribuição 4.0 Internacional). Você pode copiar, adaptar e redistribuir, desde que cite a
> autoria (Bruno Bertin Marquez) e indique as mudanças. Licença:
> https://creativecommons.org/licenses/by/4.0/

---

## 🎯 Objetivo

Ao final da atividade, o aluno será capaz de:

1. Escrever **HTML semântico** (estrutura, listas, tabelas, imagens, formulários).
2. Aplicar **CSS** de estilo, **box-model**, **Flexbox**, **Grid** e responsividade.
3. Manipular a página com **JavaScript**: variáveis, funções, DOM, eventos e `fetch`.

**Objetivo secundário:** ler o DevTools (F12) — abas *Elements*, *Styles* e *Console* — para
encontrar o erro do próprio código.

---

## 📚 Fontes no repositório

| Repositório | Pasta usada | O que foi aproveitado |
|---|---|---|
| `html-css-js-pratica` | `01_html_basico/` | Estrutura, tags, atributos, texto, imagens, links |
| `html-css-js-pratica` | `02_listas_e_tabelas/` | `<ul>`, `<ol>`, `<li>`, `<table>`, `<thead>`, `<tbody>` |
| `html-css-js-pratica` | `03_css_fundamentos/` | Seletores, cores, tipografia, box-model, margin, padding |
| `html-css-js-pratica` | `04_css_layout/` | Display, position, Flexbox, Grid, responsividade |
| `html-css-js-pratica` | `05_css_avancado/` | Pseudo-classes, transições, variáveis CSS |
| `html-css-js-pratica` | `06_html_formularios/` | `<form>`, `input`, `label`, `select`, `required`, `pattern` |
| `html-css-js-pratica` | `07_javascript_basico/` | Variáveis, tipos, operadores, funções, arrow functions |
| `html-css-js-pratica` | `08_javascript_dom/` | `querySelector`, criar e remover elementos |
| `html-css-js-pratica` | `09_javascript_events/` | `addEventListener`, `submit`, delegação |
| `html-css-js-pratica` | `10_javascript_assincrono/` | `fetch`, `async/await`, JSON, tratamento de erro |

**Trilha web (projetor):**
`laboratorio-tech-social/site/exercicios/criador-site.html` (para quem travar no HTML) ·
`laboratorio-tech-social/site/exercicios/validador-regex.html`

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **HTML** | "A **esqueleto**. O que existe." |
| **CSS** | "A **aparência**. Como cada coisa se apresenta." |
| **JavaScript** | "O **comportamento**. O que acontece quando..." |
| **DOM** | "A árvore de objetos que o navegador fez do seu HTML." |
| **Classe (`.`)** | "Vários elementos podem ter a **mesma** classe." |
| **Id (`#`)** | "**Um** elemento só. O id é único." |
| **Box-model** | "Conteúdo + padding + borda + margem = o espaço ocupado." |
| **Flexbox** | "1 dimensão: linha **ou** coluna." |
| **Grid** | "2 dimensões: linhas **e** colunas ao mesmo tempo." |
| **`textContent`** | "Trocar o **texto** que aparece na tela." |
| **`preventDefault()`** | "Faz o navegador **não** fazer a ação padrão." |
| **`async/await`** | "Pausa o código até a resposta chegar, sem travar a página." |

---

## 📝 Bloco 1 — HTML (1 a 6)

### Exercício 1 — Corrigir a estrutura ⭐ · ⏱️ 2 min

O código abaixo está **faltando tags de fechamento**. Escreva a versão corrigida.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Notícias da Escola</title>
</head>
<body>
  <h1>Notícias da Escola
  <p>Resumo da notícia do dia.
  <ul>
    <li>Feira de Livros
    <li>Feira de Ciência
</body>
</html>
```

### Exercício 2 — Tabela ⭐ · ⏱️ 2 min

Escreva uma tabela com cabeçalho (`thead`) e corpo (`tbody`), duas colunas
(**Turma** e **Alunos**) e duas linhas de dados: `9A / 28` e `9B / 30`.

### Exercício 3 — Imagem e link ⭐ · ⏱️ 3 min

Escreva o HTML de:

1. um link para `https://www.gov.br` que abra em **nova aba**, com o texto `Portal do Governo`;
2. uma imagem `imagens/feira.jpg` com o texto alternativo
   `Alunos na feira de livros da escola` e largura de 300 pixels.

### Exercício 4 — Formulário de cadastro ⭐⭐ · ⏱️ 3 min

Escreva um `<form>` com **dois campos**: nome (texto, obrigatório) e e-mail (tipo e-mail,
obrigatório). Cada campo deve ter um `<label>` ligado por `for`/`id`, e o botão deve ser do
tipo `submit`.

### Exercício 5 — HTML semântico ⭐⭐ · ⏱️ 3 min

Monte a estrutura de uma página de escola usando `header`, `nav` (com `ul` e `li`), `main`,
`section`, `article` e `footer`. O `header` tem um `h1` e um menu com dois links
(`#noticias` e `#horarios`); o `main` tem uma `section` com um `article`; o `footer` tem o
copyright.

### Exercício 6 — Corrigir e melhorar ⭐⭐⭐ · ⏱️ 4 min

O código abaixo tem **três problemas**. Aponte os três e reescreva o trecho corrigido.

```html
<div class="card">
  <h2>Curso de Python</h2>
  <p>Turmas abrem na segunda-feira. <b>Inscrições pelo site
  <img src="python.png">
</div>
```

---

## 📝 Bloco 2 — CSS (7 a 12)

### Exercício 7 — Classe × id ⭐ · ⏱️ 2 min

Responda com suas palavras:

1. Quantos elementos da página podem ter a classe `cartao`?
2. Quantos elementos podem ter o id `principal`?
3. Qual seletor estiliza **apenas** o elemento com id `principal`?

### Exercício 8 — Box-model ⭐ · ⏱️ 3 min

Calcule a **largura total** que a caixa abaixo ocupa na tela:

```css
.caixa {
  width: 200px;
  padding: 10px;
  border: 5px solid #000000;
}
```

E diga o que muda se for acrescentado `box-sizing: border-box;`.

### Exercício 9 — Preencher as lacunas ⭐⭐ · ⏱️ 3 min

Complete o CSS abaixo com as propriedades adequadas:

```css
body {
  font-family: Arial, sans-serif;
  __________________;
  background-color: #ffffff;
  margin: 0;
  padding: 20px;
}

.titulo {
  font-size: 24px;
  __________________;
}
```

### Exercício 10 — Corrigir a regra CSS ⭐⭐ · ⏱️ 3 min

A regra abaixo não funciona no navegador. Encontre **todos** os erros e reescreva:

```css
.caixa
  widht 300px;
  background-color: #ff0000
  border: 2px solid #000000;
}
```

### Exercício 11 — Flexbox ⭐⭐ · ⏱️ 4 min

Escreva o CSS de um container `.container` que dispõe **três cartões** (`.card`) em linha,
com espaço de 16 pixels entre eles, e que **quebre a linha** quando não couber. Cada cartão
deve ocupar no mínimo 280 pixels de largura.

### Exercício 12 — Grid e responsividade ⭐⭐⭐ · ⏱️ 5 min

Escreva o CSS de uma `.grade` com **três colunas iguais** e espaçamento de 16 pixels. Depois,
escreva uma `@media` que transforme a grade em **uma coluna só** quando a tela tiver no
máximo 700 pixels de largura.

---

## 📝 Bloco 3 — JavaScript (13 a 18)

### Exercício 13 — Variáveis e template literal ⭐ · ⏱️ 3 min

Complete o código para que o `console.log` mostre `Ana tem 14 anos.`:

```javascript
______ nome = "Ana";
let idade = 14;

const mensagem = __________________;

console.log(mensagem);
```

### Exercício 14 — Funções ⭐ · ⏱️ 3 min

Escreva:

1. uma função `somar(a, b)` que devolve a soma dos dois números;
2. uma **arrow function** `dobrar(numero)` que devolve o dobro;
3. as chamadas que mostram os resultados na tela.

### Exercício 15 — DOM: ler e escrever na página ⭐⭐ · ⏱️ 4 min

Dado o HTML abaixo, escreva o JavaScript que troca o texto do `h2` por
`Lista de compras` e escreve `Arroz, feijão e leite.` no parágrafo:

```html
<h2 id="titulo">Resultado:</h2>
<p id="saida"></p>
```

### Exercício 16 — Evento de envio do formulário ⭐⭐ · ⏱️ 4 min

Dado o HTML abaixo, escreva o JavaScript que, ao enviar o formulário, **não recarrega a
página**, mostra `Cadastro de Ana enviado!` (usando o que foi digitado no campo) e **limpa o
formulário**:

```html
<form id="form-cadastro">
  <input type="text" id="nome" placeholder="Seu nome">
  <button type="submit">Enviar</button>
</form>
<p id="confirmacao"></p>
```

### Exercício 17 — Criar elementos na lista ⭐⭐⭐ · ⏱️ 5 min

Dado o HTML `<ul id="lista"></ul>`, escreva o JavaScript que cria **um `li` para cada item**
da lista `['Estudar JavaScript', 'Revisar SQL', 'Fazer o simulado']` e adiciona todos dentro
do `ul`.

### Exercício 18 — Consumir uma API ⭐⭐⭐ · ⏱️ 6 min

Escreva uma função `async` que busca os alunos em `https://api.exemplo.com/alunos`,
converte a resposta em JSON e mostra **só os nomes** separados por vírgula. Se a requisição
falhar (status diferente de 200) ou a rede cair, mostre a mensagem
`Não foi possível carregar: ...`.

---

## ✅ Gabarito com o código correto

### 1 — Corrigir a estrutura

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Notícias da Escola</title>
</head>
<body>
  <h1>Notícias da Escola</h1>
  <p>Resumo da notícia do dia.</p>
  <ul>
    <li>Feira de Livros</li>
    <li>Feira de Ciência</li>
  </ul>
</body>
</html>
```

> Faltavam quatro tags de fechamento: `</h1>`, `</p>` e os dois `</li>`. O navegador até
> "conserta" isso sozinho, mas o HTML fica torto e a leitura por leitor de tela fica ruim.

### 2 — Tabela

```html
<table>
  <thead>
    <tr>
      <th>Turma</th>
      <th>Alunos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>9A</td>
      <td>28</td>
    </tr>
    <tr>
      <td>9B</td>
      <td>30</td>
    </tr>
  </tbody>
</table>
```

> `<th>` é o cabeçalho (negrito, por padrão) e `<td>` é a célula de dado.

### 3 — Imagem e link

```html
<a href="https://www.gov.br" target="_blank" rel="noopener">Portal do Governo</a>

<img src="imagens/feira.jpg" alt="Alunos na feira de livros da escola" width="300">
```

> O `alt` descreve a imagem para quem não enxerga (leitor de tela) e para quando a imagem não
> carrega. `rel="noopener"` evita que a nova aba controle a original.

### 4 — Formulário de cadastro

```html
<form id="cadastro" action="#" method="post">
  <label for="nome">Nome completo:</label>
  <input type="text" id="nome" name="nome" required>

  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>

  <button type="submit">Cadastrar</button>
</form>
```

> O `for` do `<label>` e o `id` do `<input>` precisam **combinar**: é isso que faz o clique
> no texto colocar o cursor no campo. O `required` faz o navegador bloquear o envio vazio.

### 5 — HTML semântico

```html
<header>
  <h1>Escola Azul</h1>
  <nav>
    <ul>
      <li><a href="#noticias">Notícias</a></li>
      <li><a href="#horarios">Horários</a></li>
    </ul>
  </nav>
</header>

<main>
  <section id="noticias">
    <h2>Notícias</h2>
    <article>
      <h3>Feira de Ciência</h3>
      <p>Os alunos da 9ª série apresentaram 12 projetos na feira de ciência.</p>
    </article>
  </section>
</main>

<footer>
  <p>&copy; 2026 Escola Azul</p>
</footer>
```

> O elemento `<main>` deve existir **uma vez** por página. O `&copy;` é o símbolo de copyright.

### 6 — Corrigir e melhorar

**Os três problemas:**

1. `<p>` não foi fechado antes de `<b>`;
2. `<b>` não foi fechado;
3. a `<img>` está sem o atributo `alt` (obrigatório pela acessibilidade).

**Versão corrigida:**

```html
<article class="card">
  <h2>Curso de Python</h2>
  <p>Turmas abrem na segunda-feira. <b>Inscrições pelo site</b></p>
  <img src="python.png" alt="Tela com código Python aberto no editor">
</article>
```

> Além de fechar as tags, troquei o `<div>` genérico por `<article>`, que tem significado
> claro: um conteúdo independente dentro da seção.

### 7 — Classe × id

1. **Vários** elementos podem ter a classe `cartao` — a classe serve para **reaproveitar** o
   mesmo estilo.
2. **No máximo um** elemento pode ter o id `principal` — o id é único dentro da página.
3. O seletor é `#principal` (com `#`). O `.` é para classe e o `#` é para id.

```css
.cartao {
  border: 1px solid #cccccc;
}

#principal {
  background-color: #f4f4f4;
}
```

### 8 — Box-model

Largura total = **200 (conteúdo) + 20 (padding: 10 de cada lado) + 10 (borda: 5 de cada
lado) = 230 pixels**.

Com `box-sizing: border-box;` a largura total passa a ser **200 pixels**, porque o padding e
a borda passam a caber **dentro** da largura declarada.

```css
.caixa {
  box-sizing: border-box;
  width: 200px;
  padding: 10px;
  border: 5px solid #000000;
}
```

### 9 — Preencher as lacunas

```css
body {
  font-family: Arial, sans-serif;
  color: #333333;
  background-color: #ffffff;
  margin: 0;
  padding: 20px;
}

.titulo {
  font-size: 24px;
  text-align: center;
}
```

> `color` muda a cor do **texto**; `background-color` muda a cor do **fundo**. Um erro comum é
> trocar um pelo outro.

### 10 — Corrigir a regra CSS

**Os erros:** falta o `:` depois de `.caixa`; `widht` está escrito errado (`width`); falta o
`;` depois de `background-color`.

```css
.caixa {
  width: 300px;
  background-color: #ff0000;
  border: 2px solid #000000;
}
```

> Erro de digitação em nome de propriedade é o problema número 1 no CSS. O navegador
> **ignora** a regra inteira sem avisar — por isso a dica é sempre olhar o DevTools.

### 11 — Flexbox

```css
.container {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.card {
  flex: 1 1 280px;
  padding: 16px;
  border: 1px solid #dddddd;
  border-radius: 8px;
}
```

> `flex: 1 1 280px` significa: crescer (`1`), encolher (`1`) e ter largura base de 280 pixels.
> Com `flex-wrap: wrap`, os cartões que não couberem **caem para a linha de baixo**.

### 12 — Grid e responsividade

```css
.grade {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

@media (max-width: 700px) {
  .grade {
    grid-template-columns: 1fr;
  }
}
```

> `repeat(3, 1fr)` = três colunas do mesmo tamanho. O `1fr` significa "uma fração do espaço
> disponível". A `@media` é o que torna a página **responsiva**.

### 13 — Variáveis e template literal

```javascript
const nome = "Ana";
let idade = 14;

const mensagem = `${nome} tem ${idade} anos.`;

console.log(mensagem);
```

> A crase (backtick) cria o template literal: tudo entre `${` e `}` é **executado** como
> código. Com aspas normais (`"..."`), o resultado seria o texto literal `nome tem idade anos`.

### 14 — Funções

```javascript
function somar(a, b) {
  return a + b;
}

const dobrar = (numero) => numero * 2;

console.log(somar(3, 4));
console.log(dobrar(5));
```

> Saída: `7` e `10`. A arrow function é mais curta porque não precisa de `return` para um
> único valor.

### 15 — DOM: ler e escrever na página

```javascript
const titulo = document.querySelector('#titulo');
const saida = document.querySelector('#saida');

titulo.textContent = "Lista de compras";
saida.textContent = "Arroz, feijão e leite.";
```

> `querySelector` usa o **seletor CSS** para achar o elemento. `textContent` substitui todo o
> texto que estava lá — para colocar **HTML** dentro do elemento, o equivalente é
> `innerHTML`.

### 16 — Evento de envio do formulário

```javascript
const form = document.querySelector('#form-cadastro');
const nome = document.querySelector('#nome');
const confirmacao = document.querySelector('#confirmacao');

form.addEventListener('submit', (evento) => {
  evento.preventDefault();
  confirmacao.textContent = `Cadastro de ${nome.value} enviado!`;
  form.reset();
});
```

> Sem o `preventDefault()`, o navegador recarrega a página e a mensagem some junto.
> `nome.value` é o texto digitado no campo.

### 17 — Criar elementos na lista

```javascript
const lista = document.querySelector('#lista');
const tarefas = ['Estudar JavaScript', 'Revisar SQL', 'Fazer o simulado'];

tarefas.forEach((tarefa) => {
  const item = document.createElement('li');
  item.textContent = tarefa;
  lista.appendChild(item);
});
```

> A ordem importa: primeiro se **cria** o elemento, depois se **preenche**, depois se
> **adiciona** ao pai. `createElement` cria; `appendChild` coloca.

### 18 — Consumir uma API

```javascript
async function carregarAlunos() {
  const botao = document.querySelector('#carregar');
  const saida = document.querySelector('#resultado');

  botao.addEventListener('click', async () => {
    saida.textContent = "Carregando...";

    try {
      const resposta = await fetch('https://api.exemplo.com/alunos');

      if (!resposta.ok) {
        throw new Error(`Erro HTTP ${resposta.status}`);
      }

      const alunos = await resposta.json();
      saida.textContent = alunos.map((aluno) => aluno.nome).join(', ');
    } catch (erro) {
      saida.textContent = `Não foi possível carregar: ${erro.message}`;
    }
  });
}

carregarAlunos();
```

> Três passos: `fetch` faz a requisição, `await` espera a resposta, `resposta.json()` converte o
> corpo. O `try/catch` garante que **qualquer** falha (rede, status, JSON inválido) vire uma
> mensagem na tela em vez de um erro silencioso no Console.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Prova de Web | 12 ou mais acertos em 18 |
| Itens 1, 6 e 10 | O aluno **nomeia** o problema antes de corrigir |
| Teste no navegador | O código do gabarito roda sem erro no Console (F12) |
| Item 18 | O aluno sabe dizer o que cada `await` espera |

**Pergunta de escrita:**
> "Qual é a diferença entre `<div>` e `<article>`? E por que isso importa?"
> **Resposta:** `<div>` é um **contêiner genérico**, sem significado; `<article>` declara que o
> conteúdo é **independente** e faz sentido sozinho (uma notícia, um post, um produto).
> O navegador não muda nada visualmente, mas buscadores e leitores de tela usam essa
> informação — e é isso que torna a página **semântica**.

---

## 🏠 Para casa

Monte uma página com: `header` com `nav`, uma `section` com **três cards** em Flexbox que
viram **uma coluna** em tela pequena (media query), e um botão com JavaScript que mostra a
**data e hora** atual com `new Date()`. Valide com o DevTools: **zero erros no Console**.

---

## 🔗 Próximo módulo

[EX-S5 — Banco de Exercícios: SQL e Modelagem (14–17 anos)](05-exercicios-sql.md)

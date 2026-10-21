# B5 — Web: HTML, CSS e JavaScript (13–17 anos)

**Duração:** 90 min · **Aula 5 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Construir uma página **semântica** (header, nav, main, section, footer) com **CSS de layout** (`Flexbox` e `Grid`) e **JavaScript de DOM**.
2. Escrever um **formulário com validação** em HTML e validar em JS.
3. Consumir uma **API** com `fetch` e renderizar o resultado.

**Objetivo secundário:** Explicar a diferença entre HTML, CSS e JS em uma frase cada.

---

## 📚 Fontes no repositório

`html-css-js-pratica/` — **15 módulos × 6 exercícios = 90 exercícios**, cada um com
**"RESULTADO ESPERADO"**:

| Módulo | Conteúdo | Exercícios |
|---|---|---|
| `01_html_basico` | Estrutura, tags, atributos, texto, imagens, links | 6 |
| `02_listas_e_tabelas` | `<ul>`, `<ol>`, `<li>`, `<table>`, `<thead>`, `<tbody>` | 6 |
| `03_css_fundamentos` | Seletores, cores, tipografia, box-model, margins, padding | 6 |
| `04_css_layout` | Display, position, Flexbox, Grid, responsividade | 6 |
| `05_css_avancado` | Pseudo-classes, `:hover`, `:focus`, transições, animações, variáveis | 6 |
| `06_html_formularios` | `<form>`, input, label, select, textarea, required, pattern | 6 |
| `07_javascript_basico` | Variáveis, tipos, operadores, funções, arrow functions | 6 |
| `08_javascript_dom` | `getElementById`, `querySelector`, criar/remover elementos | 6 |
| `09_javascript_events` | `addEventListener`, `click`, `submit`, `keydown`, delegação | 6 |
| `10_javascript_assincrono` | `fetch`, Promises, `async/await`, JSON, tratamento de erro | 6 |
| `11_bootstrap` | Grid, componentes, responsividade | 6 |
| `12_projeto_landing_page` | **Projeto: landing page** | 6 |
| `13_projeto_portfolio` | **Projeto: portfólio** | 6 |
| `14_projeto_lista_tarefas` | **Projeto: lista de tarefas** | 6 |
| `15_projeto_jogo_simples` | **Projeto: jogo simples** | 6 |

**Projetos reais do autor (mostram o "nível profissional"):**
- `portfolio/` — Webpack + API do GitHub + localStorage + CSS de impressão
- `meu-treino/` — PWA com Wake Lock, GPS, Web Share, localStorage
- `anyms/` — IndexedDB, 17 tabelas, custo médio ponderado
- `hubias-estudos/` — SQLite (WASM) no navegador + flashcards + Pomodoro + sync
- `lista_canais/` — agregador de 70+ canais (arrays, filtro, agrupamento)
- `esporte-sao-pedro/` — Supabase + RLS + Edge Functions + IA + SEO
- `barbearia/`, `Academia/`, `bem-estar/` — sites estáticos (bons para aula de HTML/CSS puro)
- `instagram-dio-master/` — ⚠️ **clone visual sem nenhum `<script>`**: o README diz "JavaScript" e "botão Entrar", mas o `index.html` tem 49 linhas e zero JavaScript. **Use como aula de "documentação × código".**

**Trilha web e slides:**
`laboratorio-tech-social/site/trilhas/adolescentes/02-web.html` ·
`laboratorio-tech-social/materiais/slides/aula-teens-02-web.html` ·
`laboratorio-tech-social/site/exercicios/criador-site.html` ·
`laboratorio-tech-social/site/exercicios/simulador-api.html` ·
`laboratorio-tech-social/site/exercicios/validador-regex.html`

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **HTML** | "A **esqueleto**. A estrutura. O que existe." |
| **CSS** | "A **aparência**. Como cada coisa se apresenta." |
| **JavaScript** | "O **comportamento**. O que acontece quando..." |
| **DOM** | "A árvore de objetos que o navegador fez do seu HTML." |
| **Seletor CSS** | "Uma regra de "ache quem" para estilizar." |
| **Box-model** | "Conteúdo + padding + borda + margem = o espaço que o elemento ocupa." |
| **Flexbox** | "1-dimensional: linha OU coluna." |
| **Grid** | "2-dimensional: linhas E colunas ao mesmo tempo." |
| **async/await** | "Pausa o código até a resposta chegar, sem travar a página." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Vocês usam o Instagram 2 horas por dia. Ele é feito de HTML, CSS e JavaScript.
E a mesma coisa vale pro site da escola, o do banco e o do governo. A web é a linguagem
mais registrada em que existe."*
Não diga "não é possível". Diga: **"É a mesma base. A diferença é o tamanho e a disciplina."**

**Demonstração ao vivo (5 min):** abra o DevTools (F12) num site qualquer e mostre:
- Aba **Elements** → o HTML (a árvore)
- Aba **Styles** → o CSS aplicado
- Aba **Console** → o JavaScript

Diga: *"Três abas, três linguagens. Todos os sites do mundo são isso."*

### Fase 2 — Exploração (20 min)

**Parte 1 — Anatomia de uma página (8 min).**
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Minha Página</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header><h1>Título</h1></header>
  <nav><a href="#">Link</a></nav>
  <main>
    <section>
      <h2>Seção</h2>
      <p>Texto</p>
      <form id="form">
        <label for="nome">Nome:</label>
        <input id="nome" type="text" required>
        <button type="submit">Enviar</button>
      </form>
    </section>
  </main>
  <footer><p>&copy; 2026</p></footer>
  <script src="script.js"></script>
</body>
</html>
```

**Explique por que `viewport` está no `<head>`:** sem isso, o site aparece minúsculo no celular.

**Parte 2 — Box-model e Flexbox (7 min).**
Desenhe o box-model no quadro:
```
        margem (margin)
     ┌──────────────────────┐
     │  borda (border)       │
     │  ┌────────────────┐  │
     │  │ padding        │  │
     │  │  ┌──────────┐  │  │
     │  │  │ conteúdo │  │  │
     │  │  └──────────┘  │  │
     │  └────────────────┘  │
     └──────────────────────┘
```
Flexbox em 1 linha:
```css
.container { display: flex; gap: 1rem; }
.card { flex: 1; padding: 1rem; border-radius: 8px; }
```
Grid em 1 linha:
```css
.grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; }
```

**Parte 3 — DOM e eventos (5 min).**
```javascript
const botao = document.querySelector('#botao');
const saida = document.querySelector('#saida');

botao.addEventListener('click', () => {
  saida.textContent = 'Cliquei!';
});
```

**Parte 4 — `fetch` (0 min, só mostrar)**
```javascript
async function carregar() {
  const r = await fetch('https://api.exemplo.com/dados');
  if (!r.ok) throw new Error('HTTP ' + r.status);
  const dados = await r.json();
  console.log(dados);
}
```

### Fase 3 — Mão na massa (40 min)

**Atividade A — Landing page (25 min).**
Base: `html-css-js-pratica/12_projeto_landing_page/`.
Construa uma página de **1 seção** com:
- `header` com título e subtítulo
- `nav` com 3 links
- 3 `cards` em **Flexbox** (depois em **Grid**)
- 1 `form` de contato com `required` e `type="email"`
- 1 botão que **mostra uma mensagem** sem recarregar a página (`addEventListener` + `preventDefault`)

**Atividade B — 3 exercícios do repo (15 min).**
Escolha 3 entre:
- `03_css_fundamentos/exercicio_03_box_model` — box-model
- `04_css_layout/exercicio_02_flexbox` — Flexbox
- `04_css_layout/exercicio_03_grid` — Grid
- `06_html_formularios/exercicio_04_validacao` — validação
- `08_javascript_dom/exercicio_03_criar_elementos` — criar elementos
- `09_javascript_events/exercicio_02_submit` — evento de submit
- `10_javascript_assincrono/exercicio_02_fetch` — fetch

Cada um tem um **"RESULTADO ESPERADO"** no repo. Cole-o como comentário no código e
confirme que a página faz o que dice.

**Atividade C — Consome uma API (extra, 0 min em aula / casa).**
Use `laboratorio-tech-social/site/exercicios/simulador-api.html` para entender o formato,
e depois a API real do GitHub (usada pelo repo `portfolio/`):
```javascript
const resposta = await fetch('https://api.github.com/users/Marquezbertin/repos?per_page=5');
const repos = await resposta.json();
```

### Fase 4 — Projeto (15 min)

**Desafio: "A página do projeto final"**
Monte a **landing page do projeto que a turma vai entregar** (aula 13):
- Nome do projeto, slogan, 3 cards com os "pilares"
- 1 formulário de "quero ajudar"
- 1 botão que mostra a data de atualização (via `new Date()`)

**Critério de pronto:**
- [ ] HTML **semântico** (usa `header`, `nav`, `main`, `section`, `footer`)
- [ ] `viewport` no `<head>`
- [ ] Layout com **Flexbox ou Grid**
- [ ] **1 interação** com JS (formulário, botão, menu)
- [ ] Passa no validador: **sem erro no console** (F12 → Console → 0 erros)

### Fase 5 — Mostra (5 min)

Abra 2 landing pages no projetor. Cada turma dá **1 ponto forte** e **1 sugestão**.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Landing page | 5 critérios do "pronto" |
| 3 exercícios do repo | "RESULTADO ESPERADO" conferido |
| Console limpo | 0 erros no DevTools |
| Semanticidade | Aluno sabe dizer o que é `main` e por que existe |
| Pergunta de saída | "O que o `preventDefault()` faz?" |

**Pergunta de escrita:**
> "Você tem um `<form>` que envia para o servidor. Ao clicar em enviar, a página recarrega
> e o texto digitado se perde. Como resolver sem recarregar?"
> **Resposta:** `event.preventDefault()` no handler do `submit` + AJAX (`fetch`) ou
> manipulação local.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `html-css-js-pratica/05_css_avancado/` | Pseudo-classes, transições, variáveis CSS |
| `html-css-js-pratica/11_bootstrap/` | Bootstrap (grid e componentes) |
| `html-css-js-pratica/13_projeto_portfolio/` | Portfólio — o projeto mais próximo do "portfólio do aluno" |
| `html-css-js-pratica/15_projeto_jogo_simples/` | Jogo simples (canvas ou DOM) |
| `portfolio/` (repo do autor) | Webpack, API do GitHub, CSS de impressão |
| `lista_canais/` | Agregador: arrays, filtro, agrupamento, ordenação |
| `meu-treino/` | PWA: manifest, service worker, Wake Lock, GPS, Web Share |
| `anyms/` | IndexedDB (banco no navegador) + 17 tabelas |
| `laboratorio-tech-social/site/exercicios/criador-site.html` | Gerador de site (para quem travou) |
| `laboratorio-tech-social/site/exercicios/validador-regex.html` | Regex no navegador |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Gerar dados fictícios para popular o site |

---

## 🏠 Para casa

Transformar a landing page em **site de 3 páginas** (index, sobre, contato) com CSS
externo em arquivo próprio. Publicar no GitHub Pages depois da aula 07.

---

## 🔗 Próximo módulo

[B6 — Banco de Dados e SQL](06-banco-de-dados-sql.md)

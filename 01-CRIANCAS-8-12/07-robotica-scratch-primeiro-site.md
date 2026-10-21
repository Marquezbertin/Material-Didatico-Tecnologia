# A7 — Robótica, Scratch e Primeiro Site (8–12 anos)

**Duração:** 60 min · **Computador:** 1 por aluno · **Aula 7 de 12**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. **Programar um personagem no Scratch** que se move, diz algo e reage a uma condição.
2. **Explicar o que é um sensor** e **simular 1 sensor** (luz, distância ou som).
3. **Publicar 1 página HTML** com título, um parágrafo e uma imagem — e **abrir a página no GitHub Pages**.

**Objetivo secundário:** Descobrir que um site é um **texto em um arquivo**, não um programa misterioso.

---

## 📚 Fontes no repositório

| Arquivo | O que traz |
|---|---|
| `laboratorio-tech-social/trilhas/criancas-8-12/modulo-02-scratch.md` | Módulo canônico de Scratch (15–20 min de espera + explicação) |
| `laboratorio-tech-social/trilhas/criancas-8-12/modulo-03-robotica-iot.md` | Módulo canônico de Robótica & IoT |
| `laboratorio-tech-social/site/trilhas/criancas/02-scratch.html` | Trilha web de Scratch |
| `laboratorio-tech-social/site/trilhas/criancas/03-robotica.html` | Trilha web de Robótica |
| `laboratorio-tech-social/site/trilhas/criancas/04-primeiro-site.html` | Trilha web de Primeiro Site |
| `laboratorio-tech-social/site/exercicios/simulador-robotica.html` | **Simulador de robô com sensores** (não precisa de kit!) |
| `laboratorio-tech-social/site/exercicios/robo-labirinto.html` | Labirinto do robô |
| `laboratorio-tech-social/site/exercicios/casa-inteligente.html` | Casa inteligente (IoT) |
| `laboratorio-tech-social/site/exercicios/code-builder.html` | Construtor de código (blocos) |
| `laboratorio-tech-social/site/exercicios/criador-site.html` | **Gerador de site no navegador** (para quem não tem editor) |
| `laboratorio-tech-social/site/exercicios/criador-projeto.html` | Gerador de projeto |
| `laboratorio-tech-social/site/exercicios/piano-virtual.html` | Piano (sensores de som) |
| `laboratorio-tech-social/site/exercicios/estacao-meteo.html` | Estação meteorológica (IoT) |
| `laboratorio-tech-social/materiais/slides/aula-criancas-02-scratch.html` | Slide de Scratch |
| `laboratorio-tech-social/materiais/slides/aula-criancas-03-robotica.html` | Slide de Robótica |
| `laboratorio-tech-social/materiais/slides/aula-criancas-04-primeiro-site.html` | Slide de Primeiro Site |
| `html-css-js-pratica/` (repo à parte) | HTML/CSS/JS na prática — 15 módulos com "RESULTADO ESPERADO" (use como referência do professor) |

---

## 🧠 Conceitos da aula

| Conceito | Analogia | Onde está |
|---|---|---|
| **Algoritmo em blocos** | Montar um robô de LEGO | `modulo-02-scratch.md` |
| **Evento** | "Quando acontecer X, faça Y" | Scratch |
| **Condição** | "SE touche a borda, ENTÃO vire" | Scratch |
| **Sensor** | O olho e o ouvido do robô | `modulo-03-robotica-iot.md` |
| **HTML** | A **planta** da página (a estrutura) | `04-primeiro-site.html` |
| **CSS** | A **decoração** da página | `html-css-js-pratica/` |
| **Publicar** | Colocar o site no mundo | `git-github-iniciantes/09_github_pages/` (visto na trilha adolescente) |

---

## ⏱️ Roteiro

### Fase 1 — Apresentação (5 min)

**Quiz de recuperação (A6):** *"Me dê 2 sinais de que uma notícia pode ser falsa."*

**Gancho:** *"Hoje vocês vão dar ordens para um personagem — e ele vai obedecer SEMPRE.
Depois vocês vão Teach o robô a enxergar. E no final, cada um de vocês vai ter
**o próprio site na internet**, com o nome de vocês."*

### Fase 2 — Exploração (15 min)

**Parte 1 — Scratch: 3 blocos resolvem tudo (8 min).**
Base: `modulo-02-scratch.md`.

Três perguntas e as respostas em blocos:

| Pergunta | Bloco |
|---|---|
| "Quando o jogo começar, o que faz?" | `quando ⚑ verde for clicado` → `vá para x: y: -50` |
| "Como o boneco se move?" | `se <tecla arrow> pressionada então mover 10 passos` |
| "E se chegar na borda?" | `se <tocando na borda?> então virar 180 graus` |

Explique a ordem: **Evento → Condição → Ação.** É a mesma estrutura do fluxograma da A2!
*"Viram? O fluxograma da aula 2 é exatamente isso."*

**Parte 2 — Sensores (4 min).**
Base: `modulo-03-robotica-iot.md`.
Sensores do repositório: **luz (LDR)**, **distância (ultrassom)**, **temperatura (LM35)**,
**umidade (DHT11)**, **som**.

Analogia: *"O processador é o cérebro, mas sem olhos e ouvidos, o cérebro não sabe
que tem uma parede na frente. O sensor é o olho."*

**Parte 3 — HTML é só texto (3 min).**
Mostre um `index.html` de 8 linhas. Diga:
*"Isso é um arquivo de texto. Ponto. Não existe 'programa de site' — existe um arquivo
com instruções, e o navegador lê. Igual o fluxograma: instruções que o outro entende."*

### Fase 3 — Mão na massa (28 min)

#### Tarefa 1 — Scratch (10 min)
No Scratch (scratch.mit.edu):
- Cena: personagem + fundo simples
- **Evento:** "quando eu apertar a seta verde"
- **Ação:** mover o personagem
- **Condição:** se tocar a borda, virar
- **Condição extra:** se tocar o mouse, dizer "Oi!" por 2 segundos

Desafio: adicione um **segundo personagem** que se move sozinho (sem comando) — ele usa
`segue o mouse` ou um número aleatório.

#### Tarefa 2 — Robótica simulada (8 min)
Abra `simulador-robotica.html`:
- Configure o sensor de **distância**
- Faça o robô **parar** quando o sensor detectar obstáculo
- Depois configure o sensor de **luz**: o robô procura o escuro (ou a luz)

**Whoa:** `robo-labirinto.html` para o mais rápido.

#### Tarefa 3 — Primeiro site (10 min)
Escolha **uma** das duas opções:

**Opção A — editor de texto (recomendada):**
Crie `meu-site.html`:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Meu Site - [Seu Nome]</title>
</head>
<body>
  <h1>Ola! Eu sou [Seu Nome]</h1>
  <p>Este site foi feito na aula de informatica.</p>
  <img src="foto.jpg" alt="Minha foto">
</body>
</html>
```
Salve como `.html` e **abra com duplo clique** no navegador. Funciona!

**Opção B — sem editor:** use `criador-site.html` (gerador no navegador).

> **Não publique ainda.** A publicação vem na trilha adolescente (GitHub Pages).
> Aqui o objetivo é: **"eu fiz um site e ele abre!"**

### Fase 4 — Projeto (7 min)

**Desafio: "A Sala Inteligente"**
Cada dupla projeta uma sala (sala de aula, quarto, cozinha) com **3 sensores** e
**2 automações**. Exemplo:
- Sensor de luz no corredor → acende a luz quando escurece
- Sensor de distância na porta → acende a luz ao chegar

Explicar com o **fluxograma da A2**: cada automação = 1 fluxograma (evento → condição → ação).

### Fase 5 — Mostra (5 min)

- 2 alunos jogam o jogo de Scratch (30 s cada).
- 2 duplas apresentam a Sala Inteligente.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Scratch | Personagem se move, vira na borda e reage ao clique do mouse (3 de 3) |
| Robótica | Robô para ao detectar obstáculo (1 de 1) |
| Site | Abre no navegador com título, texto e imagem (3 de 3) |
| Sala Inteligente | 3 sensores + 2 automações, com fluxograma |
| Pergunta de saída | "Qual a diferença entre sensor e processador?" |

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `laboratorio-tech-social/site/exercicios/pintura-pixel.html` | Imagem como matriz (matemática) |
| `laboratorio-tech-social/site/exercicios/piano-virtual.html` | Teclas como sensores de som |
| `laboratorio-tech-social/site/exercicios/estacao-meteo.html` | IoT com dados de sensor |
| `laboratorio-tech-social/site/exercicios/memoria-conceitos.html` | Jogo da memória dos conceitos (revisão) |
| `laboratorio-tech-social/site/exercicios/jogo-memoria.html` | Revisão geral da trilha |
| `html-css-js-pratica/` (repo separado) | 15 módulos com "RESULTADO ESPERADO" — referência para o professor preparar a aula dos 13+ |

---

## 🏠 Para casa

Melhorar o site: colocar **mais 1 parágrafo** e **1 imagem a mais**. Ou fazer um 2º jogo no Scratch.

---

## 🔗 Próximo módulo

[07 — Projeto Final](07-projeto-final.md) (aulas 8, 9 e 10)

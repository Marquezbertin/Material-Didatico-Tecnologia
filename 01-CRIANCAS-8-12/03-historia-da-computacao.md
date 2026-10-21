# A3 — História da Computação (8–12 anos)

**Duração:** 60 min · **Computador:** projetor (opcional) · **Aula 3 de 12**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de **contar, com suas palavras, a história de 3 pessoas
que mudaram a computação** e **explicar por que o computador de hoje é feito de zeros e uns**.

**Objetivo secundário:** Entender que invenções vêm de ideias de pessoas reais.

---

## 📚 Fontes no repositório

### Capítulos prontos (em `questionario/Guia da Questões/Capitulos/`)

| Capítulo | Herói da história | O que a criança vai aprender |
|---|---|---|
| `Exercicios resolvidos - Introdução.md` | — | Warm-up e como o guia é organizado |
| `História da Computação - Primeiros Dispositivos.md` | — | Que a computação é mais velha que o computador |
| `História da Computação - Charles Babbage.md` | Babbage | O "pai" do computador; a máquina analítica; Ada programando nela |
| `História da Computação - Ada Lovelace.md` | Ada | **A primeira programadora da história**; primeiro algoritmo |
| `História da Computação - Alan Turing.md` | Turing | O "pai da computação moderna"; o problema da máquina de escrever |
| `História da Computação - ENIAC.md` | — | O primeiro computador eletrônico; o tamanho de uma sala |
| `História da Computação - Grace Hopper.md` | Hopper | A "grandmother" dos programas; criou o primeiro compilador; o bug |
| `História da Computação - Processador de Texto.md` | — | **Como o papel deixou de ser obrigatório — e o processador de texto (conecta com a A5/Word)** |
| `História da Computação - IBM PC.md` | — | O computador de mesa entrou na casa das pessoas |
| `História da Computação - Steve Jobs e Steve Wozniak.md` | Jobs/Woz | O computador pessoal, o mouse, a interface gráfica |
| `A Revolução Computacional de Tim Berners-Lee.md` | Berners-Lee | A World Wide Web — a internet que a gente usa |
| `História da Computação - John von Neumann.md` | von Neumann | Como o computador moderno é organizado (memória + programa) |
| `A Evolução da Computação.md` | — | Linha do tempo completa |
| `História da Computação - COBOL.md` | — | A primeira linguagem "declarativa" — para 18+ |

### Imagens prontas
`questionario/Imagens/420px-Arquitetura_de_von_Neumann.png` · `Arquitetura.jpg` ·
`Hardware.PNG` · `history.png`

### Trilha web
`laboratorio-tech-social/site/trilhas/criancas/06-historia-computacao.html`
`laboratorio-tech-social/site/trilhas/criancas/06b-historia-quadrinhos.html` ← **formato quadrinhos!**
`laboratorio-tech-social/site/slides/aula-criancas-06-historia-computacao.html`
`laboratorio-tech-social/site/certificado/historia.html` ← **certificado de História da Computação**

### Sistema binário
`pensamento_computacional/09_sistema_binario/` — 6 exercícios: para binário, para decimal,
texto binário, imagens, sons, por que binário.

### Jogos de apoio
`QA_RUN/js/games/museum.js` · `chronicles.js` · `turing.js` (existem no seu hub de 71 jogos)

---

## 🧠 Conceitos da aula

| Conceito | Analogia | Fonte |
|---|---|---|
| **Zero e um (binário)** | Interruptor: ligado / desligado | `09_sistema_binario/` |
| **Primeiro algoritmo** | Ada Lovelace escreveu instruções para a máquina de Babbage | Cap. Ada Lovelace |
| **O primeiro bug** | Um inseto literal dentro do computador | Cap. Grace Hopper |
| **A Web** | O "encanamento" que liga os computadores do mundo | Cap. Tim Berners-Lee |

---

## ⏱️ Roteiro

### Fase 1 — Apresentação (5 min)

**Gancho:** *"Em 1946, um computador do tamanho de uma sala. Hoje cabe no bolso.
Mas a pessoa que inventou a ideia de 'programar' foi uma **mulher** que escrevia com
letras — num papel."*

**Quiz de recuperação (A2):** *"O que é um fluxograma?"*

### Fase 2 — Exploração (15 min)

Apresente **3 histórias** (escolha conforme o interesse da turma). Sugestão:

**Bloco 1 — Charles Babbage e Ada Lovelace**
Peça para ler `História da Computação - Charles Babbage.md` e `História da Computação - Ada Lovelace.md`.
Pontos para a turma:
- Babbage projetou a "Máquina Analítica" — mas **nunca foi construída na vida dele**.
- Ada Lovelace escreveu o **primeiro algoritmo** da história para a máquina.
- AdaPrevêu que a máquina ia tocar música, não só calcular números. **Ela previu o futuro.**

> **Pergunta para a turma:** *"Como alguém programa uma máquina que nunca funcionou?"*
> (Resposta: escrevendo as instruções no papel, com muito cuidado.) **Conecta com a A1.**

**Bloco 2 — Grace Hopper e o primeiro bug**
De `História da Computação - Grace Hopper.md`:
- Ela queria que programas fossem escritos em **inglês**, não em código de máquina.
- Criou o primeiro **compilador** — um tradutor de inglês para o computador.
- O "bug" literal: um inseto dentro do computador. Daí o nome.

> **Atividade rápida:** mostre uma foto/imagem de um inseto e pergunte *"isso é bug de computador
> ou de bicho?"*. A turma ri, e o termo gruda.

**Bloco 3 — Tim Berners-Lee e a Web**
De `A Revolução Computacional de Tim Berners-Lee.md`:
- Em 1989, Tim Berners-Lee, trabalhando na CERN (Suíça), propôs um sistema de **hipertexto**.
- Criou 3 coisas: **URL**, **HTTP** e **HTML**.
- A Web não era a Internet. A Internet já existia; a Web foi o **serviço** sobre ela.

> **Analogia:** Internet = as **ruas**. Web = os **endereços e os prédios** nas ruas.

### Fase 3 — Mão na massa (20 min)

**Atividade A — Binário na prática (15 min).**
Base: `pensamento_computacional/09_sistema_binario/exercicio_01_para_binario.txt` e `exercicio_03_texto_binario.txt`.

Sistema de cartões:
- 1 cartão virado para cima = **1**
- 1 cartão virado para baixo = **0**

Exercícios:
1. Escreva o número **5** em binário (cartões: 1 0 1).
2. Escreva o nome **JOÃO** usando o código do `exercicio_03_texto_binario.txt` (A=0, B=1, C=2... em 5 bits).
3. **Desafio:** quantos cartões precisa para escrever o número **1000**?

> **Gancho de fechamento:** *"Cada letra que vocês escreveram no WhatsApp hoje foi isso:
> zeros e uns. O computador não entende 'casa' — ele entende '101101'."*

**Atividade B — Linha do tempo (5 min).**
Com fita colorida no chão (ou no quadro), monte uma linha do tempo de 6 tarjetas:
**Abacaxi (séc. IV) → Babbage (1822) → Ada (1843) → ENIAC (1946) → Hopper (1952) →
Turing (1936) → Berners-Lee (1989) → Hoje.**

Coloque a turma **de pé ao lado da sua posição na linha**. Pergunta final:
*"Em 1989, a Web era uma coisa de Adulto. Hoje é onde vocês leem tudo. O que vocês acham
que vem depois?"*

### Fase 4 — Projeto (15 min)

**Desafio: "A invenção que eu quero fazer"**
Cada criança desenha e escreve 3 linhas:
1. **O que eu quero inventar** (ex: um app que avisa quando o nevão chega)
2. **Quem seria o "Alan Turing" dessa ideia** (a pessoa que teria que resolver)
3. **Em quantos passos ela vira um algoritmo** (decomposição!)

### Fase 5 — Mostra (5 min)

3alu presenting leem a invenção. Vote no título mais criativo (escrita, sem contagem pública
para não constranger).

---

## 📝 Avaliação

| Instrumento | Aplicação |
|---|---|
| Quiz | `laboratorio-tech-social/site/trilhas/criancas/06-historia-computacao.html` (se tiver quiz embutido) |
| Observação | Rubrica |
| Entrega | Folha "A invenção que eu quero fazer" |
| Certificado | `laboratorio-tech-social/site/certificado/historia.html` — **existe um certificado específico de História da Computação!** Entregue ao final da aula. |

**Perguntas do quiz:**
1. Quem escreveu o primeiro algoritmo? → Ada Lovelace
2. De onde veio a palavra "bug"? → De um inseto literal no computador
3. O que o computador entende? → Apenas zeros e uns
4. Quem criou a World Wide Web? → Tim Berners-Lee

---

## 🧩 Exercícios extras

| Arquivo | Sobre |
|---|---|
| `pensamento_computacional/09_sistema_binario/exercicio_04_imagens.txt` | Como uma imagem é guardada (pixels) |
| `pensamento_computacional/09_sistema_binario/exercicio_05_sons.txt` | Como um som é guardado |
| `pensamento_computacional/09_sistema_binario/exercicio_06_porque_binario.txt` | Por que só 2 estados? |
| `laboratorio-tech-social/site/exercicios/pintura-pixel.html` | Desenhar por pixels (binário aplicado) |
| `laboratorio-tech-social/site/exercicios/misturador-cores.html` | Cores = números |

---

## 🏠 Para casa

Perguntar a um adulto: *"Como era o computador quando você era pequeno?"*
Trazer a resposta e uma foto (ou desenhar) na próxima aula.

---

## 🔗 Próximo módulo

[A4 — Informática Básica: SO, hardware e digitação](04-informatica-basica.md)

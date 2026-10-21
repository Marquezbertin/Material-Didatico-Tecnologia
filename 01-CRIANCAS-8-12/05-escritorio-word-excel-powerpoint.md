# A5 — Word, Excel e PowerPoint (8–12 anos)

**Duração:** 60 min · **Computador:** 1 por aluno · **Aula 5 de 12**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. **Word/Editor:** criar um documento com **título, 1 parágrafo, negrito, itálico, lista com marcadores e uma imagem**, e **salvar como PDF**.
2. **Excel/Planilha:** criar uma tabela com **cabeçalho, 3 colunas, 5 linhas, fórmula de SOMA e de MÉDIA**, e um **gráfico de barras**.
3. **PowerPoint/Apresentação:** criar **3 slides** com título, texto e imagem, na ordem certa.

**Objetivo secundário:** Entender que planilha = tabela + fórmulas, e que uma fórmula "se refaz sozinha".

---

## 📚 Fontes no repositório

| Arquivo | O que traz |
|---|---|
| `laboratorio-tech-social/site/trilhas/criancas/07-informatica.html` | Trilha web: Word, Excel, PowerPoint, digitação, pesquisa, mídias |
| `laboratorio-tech-social/site/exercicios/editor-texto.html` | **Editor de texto no navegador (mini-Word)** |
| `laboratorio-tech-social/site/exercicios/planilha.html` | **Planilha no navegador (mini-Excel) com fórmulas e gráficos** |
| `laboratorio-tech-social/site/exercicios/flashcards.html` | Reforço de conteúdo com cartões |
| `laboratorio-tech-social/site/exercicios/notas.html` | Caderno de notas (mini-journal) |
| `laboratorio-tech-social/site/exercicios/estacao-meteo.html` | Dados + visualização (projeto de planilha) |
| `laboratorio-tech-social/site/exercicios/visualizador-dados.html` | Visualizador de dados CSV/JSON |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Gerador de dados fictícios (fonte para a planilha) |
| `laboratorio-tech-social/site/exercicios/lista-tarefas.html` | Lista de tarefas (bom para Excel) |
| `laboratorio-tech-social/site/exercicios/casa-inteligente.html` | Casa inteligente (dados de sensores) |
| `laboratorio-tech-social/site/exercicios/misturador-cores.html` | Cores para a apresentação |
| `laboratorio-tech-social/site/exercicios/piano-virtual.html` | Sons/músicas para a apresentação |
| `planilhaeletronicas/` (repo à parte) | Planilha **por trás do código** (Flask + Pandas + XLSX) — referência do professor |

---

## 🧠 Conceitos da aula

| Conceito | Analogia | Por que importa |
|---|---|---|
| **Documento** | Um caderno com capa, texto e imagens | É como o professor avalia o trabalho |
| **Planilha** | Uma tabela que **se calcula sozinha** | É o primeiro "programa" sem escrever código |
| **Célula** | Quadradinho da planilha | Endereço = coluna + linha (B7) |
| **Fórmula** | Uma receita que o Excel repete para todo mundo | **Conceito-chave: a fórmula é o algoritmo** |
| **Slide** | Um cartão de um flipped presentation | Comunicação visual |

> **Frase-chave da aula (repita 3 vezes):**
> *"Planilha é a mesma coisa que receita — a fórmula é o passo que se repete."*
> Isso conecta A1 (algoritmo) com a planilha.

---

## ⏱️ Roteiro

### Fase 1 — Apresentação (5 min)

**Quiz de recuperação (A4):** *"Qual a diferença entre hardware e software?"*

**Gancho:** *"Quem aqui já ganhou um prêmio de 'melhor trabalho da escola'? O que eles olham?
Folha de papel com letra. Hoje vocês vão fazer o mesmo, mas o computador faz a parte chata."*

### Fase 2 — Exploração (12 min)

**Parte 1 — Word (4 min).** Mostre o `editor-texto.html` no projetor.
Explique 5 comandos: **negrito**, *itálico*, **sublinhado**, lista com marcadores, inserir imagem.
Diga: *"Negrito é para o que é IMPORTANTE. Se tudo está em negrito, nada está."*

**Parte 2 — Excel (5 min).** Mostre o `planilha.html` no projetor.
Escreva ao vivo:
- A1: `Produto` | B1: `Preço` | C1: `Qtd` | D1: `Total`
- D2: `=B2*C2`  ← **a fórmula** (a mesma receita do Sanduíche)
- D3: `=B3*C3`
- Selecione D2:D3 e arraste → o Excel copia. **Mostre isso. É o momento "uau".**
- `=MÉDIA(B2:B6)` e `=SOMA(B2:B6)`

**Parte 3 — PowerPoint (3 min).** Mostre `laboratorio-tech-social/materiais/slides/template-slides.html`.
Explique: 1 slide = 1 ideia. Título + no máximo 5 palavras + imagem.

### Fase 3 — Mão na massa (28 min)

Trabalhe em **duplas** no mesmo computador (alternando: um digita, o outro dita — treina
comunicação, que é o objetivo do plano pedagógico).

#### Tarefa 1 — Documento (8 min)
Abra `editor-texto.html` (ou Word/LibreOffice, se a escola tiver).
Crie o documento **"Minha Super Máquina"**:
- Título em negrito e centralizado
- 1 parágrafo de 4 linhas descrevendo a máquina
- **3 recursos** (negrito, itálico, lista com marcadores)
- 1 imagem (desenhe no Paint e insira, ou use `pintura-pixel.html`)
- Salve como PDF (`Salvar como → PDF`)

#### Tarefa 2 — Planilha (12 min)
Abra `planilha.html` (ou Excel/LibreOffice).
Monte a planilha **"Clube do Lanche"**:

| | A | B | C | D |
|---|---|---|---|---|
| 1 | Lanche | Preço | Qtde | Total |
| 2 | Pão de queijo | 6,00 | 3 | `=B2*C2` |
| 3 | Suco | 4,50 | 5 | `=B3*C3` |
| 4 | Bolacha | 3,00 | 2 | `=B4*C4` |
| 5 | Maçã | 2,50 | 4 | `=B5*C5` |
| 6 | **Total** | | | `=SOMA(D2:D5)` |

Extras:
- `=MÉDIA(B2:B5)` na célula B7
- **Gráfico de barras** dos totais
- Altere o preço do pão de queijo e mostre o total mudar sozinho (de novo o "uau")

#### Tarefa 3 — Apresentação (8 min)
3 slides sobre o clube do lanche:
1. **Capa:** "Clube do Lanche" + imagem
2. **O que vendemos:** lista dos lanches
3. **Nossa meta:** quanto vamos ganhar por mês (fórmula aplicada)

### Fase 4 — Projeto (10 min)

**Desafio: "Menu do meu evento"**
Cada dupla cria:
- 1 planilha com os custos do evento (bebida, comida, decoration) + fórmulas de total e por pessoa
- 1 documento com o convite (com imagem)
- 1 apresentação de 3 slides para apresentar o convite à turma

**Critério de pronto (todas as 3 entregas):**
- [ ] Planilha: 3 colunas + fórmula de SOMA + fórmula de MÉDIA + 1 gráfico
- [ ] Documento: título, texto, formatação e imagem
- [ ] Apresentação: 3 slides, sem "trecho de texto enorme"

### Fase 5 — Mostra (5 min)

2 duplas apresentam a apresentação (1 min cada). Turma dá os "2 pontinhos".

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Planilha | 3 fórmulas corretas + 1 gráfico |
| Documento | 4 recursos de formatação + 1 imagem + salvo |
| Apresentação | 3 slides com ordem e clareza |
| Rubrica | Semente / Broto / Árvore / Floresta |
| Autoavaliação | `site/exercicios/flashcards.html` para fixar os 5 comandos |

**Pergunta de saída:** *"O que aconteceria com o total se eu mudasse a quantidade?"*
(Resposta esperada: recalcula sozinho. É a fórmula.)

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `site/exercicios/lista-tarefas.html` | Lista de tarefas (dá para importar para a planilha) |
| `site/exercicios/gerador-dados.html` | Gerar dados fictícios de vendas para a planilha |
| `site/exercicios/estacao-meteo.html` | Dados de temperatura — planilha + gráfico |
| `site/exercicios/visualizador-dados.html` | Ver CSV/JSON — ponte para a trilha de dados (B12) |
| `planilhaeletronicas/` (repo separado) | **Referência do professor:** a mesma planilha feita em Flask + Pandas + XLSX. Use como exemplo do "por trás" e aponte a divergência real: o README manda rodar `test_app.py`, mas o arquivo é `casosdeteste.py`, e 8 de 10 testes falham. |

---

## 🏠 Para casa

Refazer a planilha em casa com os **gastos reais da família** (só com autorização) ou com
dados inventados, e escrever **3 frases** explicando o que a planilha faz.

---

## 🔗 Próximo módulo

[A6 — Pesquisa, Mídias e Cidadania Digital](06-pesquisa-e-midias.md)

# B2 — Lógica e Algoritmos (13–17 anos)

**Duração:** 90 min · **Aula 2 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Escrever **8 algoritmos** em pseudocódigo cobrindo variáveis, condicionais, laços, vetores, matrizes, strings, procedimentos, funções, recursão, ordenação e busca.
2. Implementar **2 deles em Visualg** (os que rodam no executável da escola).
3. Explicar a diferença entre **busca linear** e **busca binária** com medição de tempo.

**Objetivo secundário:** Reconhecer recursão e saber escrever **1 função recursiva** simples.

---

## 📚 Fontes no repositório

`logica_programacao/` — **15 módulos e 80 algoritmos** (a base mais completa do material):

| Módulo | Conteúdo | Nº de algoritmos |
|---|---|---|
| `01_variaveis_e_tipos` | Variáveis, tipos (inteiro, real, caracter, lógico) | — |
| `02_entrada_saida` | `escreva`, `leia`, entrada/saída | — |
| `03_operadores` | Aritméticos, lógicos, relacionais | — |
| `04_condicionais` | `se`, `se...senao`, `escolha` | — |
| `05_lacos_repeticao` | `enquanto`, `para`, `repita` | — |
| `06_vetores` | Vetores de 1, 2 e 3 dimensões | — |
| `07_matrizes` | Matrizes (matriz x vetor) | — |
| `08_strings` | Manipulação de texto | — |
| `09_procedimentos` | Procedimentos (sem retorno) | — |
| `10_funcoes` | Funções (com retorno) | — |
| `11_recursao` | Recursão | — |
| `12_ordenacao` | Bubble sort, insertion sort, seleção | — |
| `13_busca` | Busca linear, busca binária | — |
| `14_introducao_a_dados` | Vetores e matrizes em profundidade | — |
| `15_exercicios_desafio` | Desafios finais | — |

**Complementos:**
- `laboratorio-tech-social/site/exercicios/code-builder.html` — montador de lógica em blocos
- `laboratorio-tech-social/site/exercicios/validador-regex.html` — expressões regulares
- `pensamento_computacional/06_fluxogramas/` e `07_pseudocodigo/`

---

## 🧠 Conceitos-chave

| Conceito | Por que importa |
|---|---|
| **Vetor** | Guardar vários valores do mesmo tipo. É a base de lista, array e tabela |
| **Matriz** | Vetor de vetores. É a base de planilha, imagem e tabela de banco |
| **Procedimento vs Função** | Procedimento executa; função devolve valor. Distinção que a turma esquece sempre |
| **Recursão** | Um caso chama a si mesmo com um caso base. Base de árvore, grafo e recursão de pastas |
| **Complexidade** | O(n) vs O(n log n). Aula que separa quem só decora de quem entende |

**Analogias:**
- Vetor = **prateleira com gavetas numeradas** (acesso direto: gaveta 5)
- Busca linear = procurar um livro **varrendo a prateleira da esquerda para a direita**
- Busca binaria = **a adivinhacao do numero** - metade sempre

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Presentação (10 min)

**Gancho:** *"Seu buscador favorite resolve em 0,2 s. Eu vou te mostrar por que
buscar 1.000.000 de registros 'na mão' leva 1.000.000 de passos."*

**Demonstração ao vivo (5 min):** escreva no quadro a busca linear e rode mentalmente:
```
ENCONTRE(x em v[0..n-1]):
   para i de 0 até n-1:
      se v[i] == x: retorne i
   retorne -1
```
Pergunta: *"Quantos passos, no pior caso, para achar o último item?"* → **n**.
*"E se eu achar que está na metade?"* → **log₂n** = ~20 passos para 1.000.000.
*"Essas são as 2 respostas que a aula vai construir."*

### Fase 2 — Exploração (20 min)

**Parte 1 — Vetores e matrizes (8 min).**
Mostre que a planilha da trilha 8–12 **já é uma matriz**, e que a lista de tarefas do
`html-css-js-pratica/14_projeto_lista_tarefas/` **já é um vetor**.
Peça: *"Dê 3 exemplos de vetor que vocês usam todo dia"* (lista de amigos, notas, vídeos).

**Parte 2 — Procedimento vs Função (6 min).**
```
PROCEDIMENTO MostrarMensagem(texto):     # executa, não devolve nada
   escreva(texto)
FIM

FUNCAO Somar(a, b):                       # devolve valor
   retorne a + b
FIM
```
Pergunta: *"Qual dos dois eu uso quando o resultado entra numa fórmula?"*

**Parte 3 — Recursão (6 min).**
Mostre a soma dos números de 1 a n:
```
FUNCAO Soma(n):
   se n == 0: retorne 0        # CASO BASE
   retorne n + Soma(n - 1)     # CHAMADA RECURSIVA
FIM
```
Rastreie `Soma(4)` na lousa: 4+3+2+1+0 = 10.
A analogia: **boneca russa** — cada uma contém uma menor até a menor não conter mais nada.

> **Armadilha clássica:** sem caso base → pilha estoura (`RecursionError`).
> Teste no Colab: escreva `def f(n): return f(n-1)` e chame `f(1)`. **Deixe quebrar na frente da turma.**

### Fase 3 — Mão na massa (35 min)

**Atividade A — 8 algoritmos em pseudocódigo (25 min).**
Cada aluno pega a folha "Algoritmos" (modelo abaixo) e escreve **8 algoritmos**,
1 por módulo do repo. Escolha 8 entre:

| # | Módulo de origem | Algoritmo a escrever |
|---|---|---|
| 1 | `01_variaveis_e_tipos` | Trocar 2 valores de 2 variáveis (sem variável temporária) |
| 2 | `02_entrada_saida` | Ler nome e 3 notas, mostrar a média |
| 3 | `03_operadores` | Verificar se um número é par E múltiplo de 3 |
| 4 | `04_condicionais` | Classificar nota (A/B/C/D/E) |
| 5 | `05_lacos_repeticao` | Somar todos os números pares de 1 a 100 |
| 6 | `06_vetores` | Preencher um vetor de 10 números e mostrar o maior e o menor |
| 7 | `07_matrizes` | Preencher uma matriz 3x3 e mostrar a diagonal principal |
| 8 | `08_strings` | Contar quantas vogais tem uma frase |
| 9 | `09_procedimentos` | Procedimento `MostarMenu()` que exibe 3 opções |
| 10 | `10_funcoes` | Função `EhPrimo(n)` que retorna V ou F |
| 11 | `11_recursao` | `Fatorial(n)` recursivo |
| 12 | `12_ordenacao` | Bubble sort de um vetor de 5 números |
| 13 | `13_busca` | Busca binária num vetor ordenado |
| 14 | `14_introducao_a_dados` | Preencher matriz de notas de 3 alunos × 4 disciplinas e calcular a média de cada aluno |

> **Critério:** pseudocódigo do padrão `logica_programacao` (ENTRADA / SAIDA / INICIO / FIM),
> com indentação e **1 algoritmo por bloco**.

**Atividade B — 2 algoritmos em Visualg (10 min).**
Se a escola tiver o Visualg instalado (o repo `logica_programacao` foi feito para ele):
implemente o **#2 (média)** e o **#5 (pares de 1 a 100)**.
Se não tiver: implemente no **Scratch** ou em **Python (Colab)**.

### Fase 4 — Projeto (20 min)

**Desafio: "O caçador de números"**
Implemente (em pseudocódigo + implementação) um programa que:
1. Leia **20 números** para um vetor.
2. Peça um valor de busca.
3. Use **busca linear** e **busca binária** (ordene antes).
4. Diga se encontrou, em qual posição (1-based) e **quantas comparações** cada método fez.

**Desafio bônus:** rode com 1.000, 10.000 e 100.000 números e anote as comparações.
A turma vai ver a curva n × log n desenhada na lousa.

### Fase 5 — Mostra (5 min)

3 alunos apresentam um dos 8 algoritmos. Turma identifica: **qual módulo do repo ele veio de**.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| 8 algoritmos | 8 de 8 no formato correto, com ENTRADA/SAIDA quando aplicável |
| 2 implementações | Rodam sem erro |
| Caçador de números | Mostra posição + contagem de comparações nos 2 métodos |
| Participação | 1 algoritmo explicado por aluno (oral) |
| Pergunta de escrita | "Complexidade da busca linear vs binária" |

**Pergunta de escrita (vale 1 ponto):**
> "Você precisa procurar 1 nome em uma lista de 10.000 contatos que **não está ordenada**.
> Busca linear ou binária? Justifique."

**Resposta esperada:** binária **não serve** (exige ordenação). Ou: se ordenar primeiro,
ordenar custa O(n log n) e não compensa para 1 busca. **É a resposta que mostra
entendimento.**

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `logica_programacao/15_exercicios_desafio/` | Desafios finais (use como banco de exercícios extras) |
| `logica_programacao/11_recursao/` | Exercícios de recursão (fibonacci, hanoi, torre) |
| `logica_programacao/12_ordenacao/` | Comparação entre os 3 algoritmos de ordenação |
| `logica_programacao/13_busca/` | Busca sequencial × binária |
| `laboratorio-tech-social/site/exercicios/desafios-python.html` | Versão em Python dos desafios |
| `pensamento_computacional/05_pensamento_algoritmico/exercicio_06_otimizacao.txt` | Otimização |

---

## 🏠 Para casa

Escolha **2 dos 8 algoritmos** e implemente em Python no Google Colab.
Traga o link do notebook (ou o código) na próxima aula.

---

## 🔗 Próximo módulo

[B3 — Python do Zero](03-python.md)

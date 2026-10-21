# B1 — Pensamento Computacional Avançado (13–17 anos)

**Duração:** 90 min · **Aula 1 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de **decompor um sistema real** (ex.: o sistema de
matrícula da escola) em 4 camadas — **dados, regras, interface, infraestrutura** — e
escrever o pseudocódigo de **1 regra de negócio** com **condicional + repetição**.

**Objetivo secundário:** Reconhecer os 4 pilares do pensamento computacional em código
que já existe (e apontar onde falta um deles).

---

## 📚 Fontes no repositório

| Arquivo | O que traz |
|---|---|
| `pensamento_computacional/01_pensamento_computacional/exercicio_04_quatro_pilares.txt` | Os 4 pilares — definição oficial do repo |
| `pensamento_computacional/02_decomposicao/` (6 exercícios) | Decomposição aplicada a casos reais |
| `pensamento_computacional/03_reconhecimento_padroes/` (6) | Padroes: quando repetir codigo, quando abstrair |
| `pensamento_computacional/04_abstracao/` (6) | Abstração: o que esconder e por quê |
| `pensamento_computacional/05_pensamento_algoritmico/` (6) | Algoritmo, decisões, repetições, otimização |
| `pensamento_computacional/06_fluxogramas/` (6) | Fluxogramas de sistemas com várias decisões |
| `pensamento_computacional/07_pseudocodigo/` (6) | Pseudocódigo completo, do "hello world" a programa com lista |
| `pensamento_computacional/08_logica_proposicional/` (6) | Lógica proposicional: E, OU, combinação, paradoxos |
| `laboratorio-tech-social/site/exercicios/pensamento-computacional.html` | Jogo interativo de pensamento computacional |
| `laboratorio-tech-social/site/exercicios/code-builder.html` | Montar lógica em blocos |
| `laboratorio-tech-social/site/exercicios/criador-projeto.html` | Estruturar um projeto antes de codar |

---

## 🧠 O framework que a aula ensina

O `pensamento_computacional` organiza tudo em **4 pilares**. Na faixa 8–12 você usou os
pilares como jogo. Agora eles viram **ferramenta de engenharia**:

| Pilar | No código | Pergunta de revisão |
|---|---|---|
| **Decomposição** | Funções, classes, módulos, serviços | "Isso está grande demais? Onde corto?" |
| **Reconhecimento de padrões** | Funções reutilizáveis, `for`, listas, ORM, APIs | "Esse código já existe? Onde?" |
| **Abstração** | Interfaces, classes abstratas, `dict` em vez de 50 variáveis | "O que o chamador precisa saber?" |
| **Algoritmos** | O `for`, o `if`, a função, a query SQL | "Os passos estão certainos e na ordem?" |

**A tabela de decomposição em 4 camadas** (adaptada de `12_modelagem_er` do repo SQL e do
`modulo-06-projeto-social.md`):

| Camada | O que é | Exemplo (escola) |
|---|---|---|
| **Dados** | O que é guardado | Aluno, Turma,Matrícula,Nota,Professor |
| **Regras** | O que é permitido/calculado | "Nota < 5 reprova"; "Turma <= 40 alunos" |
| **Interface** | Como o humano usa | Formulário de matrícula, relatório |
| **Infraestrutura** | Onde roda | Servidor, banco, CI, deploy |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Vocês já usaram o sistema de matrícula da escola. Ele tem tela, tem banco de
dados, tem regra que reprova aluno. Se alguém apagar essa regra sem querer, ninguém
nota até o boletim sair errado. Hoje a gente vai abrir esse sistema e ver as 4 camadas."*

**Quiz de recuperação (Aula 0 / do 8–12):** *"O que é decomposição?"*

**Demonstração ao vivo (5 min):** mostre o `banco-de-dados-sql/14_projeto_sistema_escolar/`
e pergunte: *"Onde está a regra que reprova? Onde está o dado? Onde está a tela?"*

### Fase 2 — Exploração (20 min)

**Parte 1 — Os 4 pilares em código real (10 min).**
Abra `html-css-js-pratica/14_projeto_lista_tarefas/` e identifique com a turma:

- **Decomposição:** funções separadas (`adicionarTarefa`, `renderizarLista`, `salvar`)
- **Padrão:** o mesmo "adicionar item na lista" aparece em vários lugares → virou função
- **Abstração:** quem chama `salvar()` não sabe se é `localStorage` ou API
- **Algoritmo:** o `for` que percorre a lista e cria os `<li>`

**Parte 2 — Lógica proposicional (10 min).**
Base: `pensamento_computacional/08_logica_proposicional/`.

Exercício ao vivo: *"O aluno pode ser reprovado se: nota < 5 **E** não fez arecovery
**OU** faltou 60% das aulas. Escreva a condição."*

```python
nota < 5 and not fez_recovery or faltas > 0.6 * aulas_totais
```

> **A pegadinha clássica:** sem parênteses, a ordem das operações muda tudo.
> `A and B or C` = `(A and B) or C`. **É a mesma armadilha do fluxograma da A2.**
> Peça: "desenhe o fluxograma dessa condição e depois escreva o código". Se o código e o
> fluxograma não baterem, achamos um bug.

### Fase 3 — Mão na massa (35 min)

**Atividade A — Decomposição do sistema da escola (20 min).**
Em duplas, preencher o quadro (1 folha A3 por dupla):

```
SISTEMA ESCOLAR — Decomposição em 4 camadas

DADOS (o que é guardado):
  Entidade          | Atributos (3+)          | Tipo
  ------------------|--------------------------|----------
  Aluno             |                          |
  Turma             |                          |
  ------------------+--------------------------+----------

REGRAS (o que é permitido/calculado):
  R1:
  R2:
  R3:

INTERFACE (o que a pessoa usa):
  Tela 1:
  Tela 2:

INFRAESTRUTURA (onde roda):
  App:
  Banco:
  Deploy:

DADO QUE NÃO DEVERIA EXISTIR:
  (ex.: senha em texto puro, nota de aluno junto com documento)
```

> **O último campo é o que diferencia um adolescente de um adulto.** Descomente: *"O sistema
> real guarda isso. E nós vamos fazer o nosso sem guardar."*

**Atividade B — Pseudocódigo de 1 regra (15 min).**
Cada dupla escreve o pseudocódigo de **1 regra** do quadro acima, no formato do repo
(`07_pseudocodigo/`):

```
ALGORITMO: ValidarMatricula
ENTRADA: aluno, turma
SAIDA: pode_matricular (VERDADEIRO ou FALSO)
INICIO
    SE turma.vagas <= 0 ENTAO
        RETORNAR FALSO
    FIM SE
    SE aluno.ja_matriculado EM turma ENTAO
        RETORNAR FALSO
    FIM SE
    SE turma.tem_turno_incompativel COM aluno.turno ENTAO
        RETORNAR FALSO
    FIM SE
    turma.vagas <- turma.vagas - 1
    RETORNAR VERDADEIRO
FIM
```

### Fase 4 — Projeto (20 min)

**Desafio: "Diagnóstico de um repositório"**
Cada dupla escolhe **1 repositório real do autor** e faz a decomposição em 4 camadas:

Opções (todas existentes e auditadas):
- `central-de-noticias` — pipeline RSS → resumo → TTS → PWA
- `esporte-sao-pedro` — Supabase + RLS + Edge Functions + IA + SEO
- `meu-treino` — PWA com Wake Lock, GPS, Web Share, localStorage
- `anyms` — gestão com IndexedDB, 17 tabelas, custo médio ponderado
- `hubias-estudos` — SQLite (WASM) no navegador + flashcards + Pomodoro + sync

**Entrega da atividade:**
- [ ] 1 folha com as 4 camadas preenchidas
- [ ] 1 regra real escrita em pseudocódigo
- [ ] **1 problema encontrado** (é o gancho para a aula de QA)

### Fase 5 — Mostra (5 min)

2 duplas apresentam. A turma responde a pergunta: *"Qual camada o bug mais provavel esta?"*
(o bug encontrado na atividade vira matéria-prima para a aula 08 de QA).

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Quadro de decomposição | 4 camadas preenchidas + 1 dado indevido identificado |
| Pseudocódigo | tem ENTRADA, SAÍDA, 1 condicional, 1 retorno |
| Diagnóstico de repositório | 4 camadas + 1 problema real encontrado |
| Participação | 1 pergunta ao vivo por aluno |
| Pergunta de saída | "Qual a diferença entre dado e regra?" |

**Rubrica (4 níveis) — critério "Decomposição":**
Semente = nomeia as 4 camadas / Broto = preenche 3 / Árvore = preenche 4 + pseudocódigo /
Floresta = preenche 4 + pseudocódigo + identifica dado indevido + problema real.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `02_decomposicao/exercicio_03_criar_site.txt` | Decomposição de um site |
| `02_decomposicao/exercicio_04_organizar_evento.txt` | Decomposição de um evento (bom para a escola) |
| `02_decomposicao/exercicio_06_cinco_porques.txt` | Causa raiz — base do mindset de QA |
| `03_reconhecimento_padroes/exercicio_04_tendencias.txt` | Identificar o que se repete num código |
| `04_abstracao/exercicio_03_generalizar.txt` | O que generalizar |
| `04_abstracao/exercicio_05_simplificar.txt` | Simplificar sem perder comportamento |
| `05_pensamento_algoritmico/exercicio_06_otimizacao.txt` | Complexidade: o que muda quando o dado dobra |
| `08_logica_proposicional/exercicio_06_paradoxos.txt` | Paradoxo do barbeiro (puro pensar) |
| `logica_programacao/15_exercicios_desafio/` | Desafios finais de lógica |

---

## 🏠 Para casa

Escolher **um app que você usa todo dia** e fazer a decomposição em 4 camadas.
Trazer impresso ou no celular.

---

## 🔗 Próximo módulo

[B2 — Lógica e Algoritmos](02-logica-e-algoritmos.md)

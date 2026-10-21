# A1 — Pensamento Computacional (8–12 anos)

**Duração:** 60 min · **Computador:** não obrigatório (dá para fazer no papel!) · **Aula 1 de 12**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de **dividir uma tarefa do dia a dia em 4 a 6 passos
numerados, sem pular etapas**.

**Objetivo secundário:** Reconhecer que uma receita de sanduíche é um algoritmo.

**Por que isso importa:** o `laboratorio-tech-social/docs/plano-pedagogico.md` define como
primeiro objetivo dos Exploradores: *"Compreender o que é um computador e como ele pensa (lógica)"*.

---

## 📚 Fontes no repositório

| Arquivo | O que traz |
|---|---|
| `laboratorio-tech-social/trilhas/criancas-8-12/modulo-01-pensamento-computacional.md` | Módulo canônico: objetivo, 3 atividades + desafio final, material complementar |
| `laboratorio-tech-social/site/trilhas/criancas/01-pensamento.html` | Versão web com quiz interativo de 4 perguntas |
| `pensamento_computacional/01_pensamento_computacional/` | 6 exercícios: autoavaliação, resolver problemas, mundo contrário, quatro pilares, desafio lógico, reflexão |
| `pensamento_computacional/02_decomposicao/` | 6 exercícios: montar móvel, planejar viagem, criar site, organizar evento, receita de bolo, cinco porquês |
| `pensamento_computacional/03_reconhecimento_padroes/` | 6 exercícios: sequências, visuais, rotinas, tendências, quebrar padrões, criar padrões |
| `pensamento_computacional/04_abstracao/` | 6 exercícios: resumir, mapas, generalizar, filtrar, simplificar, níveis |
| `laboratorio-tech-social/materiais/slides/aula-criancas-01-pensamento.html` | Slide pronto |

---

## 🧠 Conceitos da aula (com analogia — nunca definição seca)

| Conceito | Analogia | Pergunta que prova que aprendeu |
|---|---|---|
| **Decomposição** | Montar um móvel: caixa → peças → parafusos | "Um IKEA tem 300 peças. Como você monta?" |
| **Padrão** | Todo dia a gente faz a mesma coisa: acordar, escovar, comer | "O que se repete na sua manhã?" |
| **Abstração** | Desenhar um mapa: você ignora o que não precisa para chegar | "Se eu só preciso ir do ponto A ao B, o que do mapa eu ignoro?" |
| **Algoritmo** | A receita da mãe: passos que sempre funcionam | "A receita da vó dá sempre o mesmo resultado?" |

> **Alerta:** os 4 pilares (decomposição, padrões, abstração, algoritmos) estão em
> `pensamento_computacional/01_pensamento_computacional/exercicio_04_quatro_pilares.txt`.
> Para 8 anos, apresente **2 pilares por aula**, não os 4 de uma vez.

---

## ⏱️ Roteiro (ciclo do plano pedagógico)

### Fase 1 — Apresentação do problema (5 min)

**Gancho:** *"Quem já seguiu uma receita de montagem de móvel? Aquela que vem com pieceinha de plástico e você monta com a mão?"*
Espere as mãos levantarem. Conte 2 histórias rápidas.

**Quiz de recuperação** (é a aula 1 — adapte para "o que a gente vai aprender hoje"):
pergunte: *"O que um computador faz melhor que a gente?"*. Aceite 3 respostas diferentes
sem corrigir. Diga: *"Hoje a gente vai descobrir que a resposta é: ele segue passos exatos."*

**Declare o objetivo:** *"Hoje vocês vão virar Chef de receita — mas de um computador."*

### Fase 2 — Exploração (10 min)

Use o **Atividade 1 — Receita do sanduíche** do `modulo-01-pensamento-computacional.md`:

> "Escreva no papel a receita de montar um sanduíche, passo a passo, como se estivesse
> ensinando um robô que não sabe nada."
> Exemplo do repo: *"Pegue 2 fatias de pão. Coloque queijo em uma. Cubra com a outra."*

**Faça ao vivo na lousa** com a turma dictando. Depois mostre a versão **errada**:
*"Pegue o pão. Coloque o queijo. Pronto."* — Pergunte: *"O que falta?"*
A turma vai dizer: *"os detalhes, a ordem, os passos."*
Esse é o momento da aula. **Não pule.**

**Conceito-chave 2 — Decomposição:** pegue a receita e pergunte: *"Isso é 1 passo ou muitos?"*
Anote no quadro: 1 receita = 6 passos = 1 algoritmo.

### Fase 3 — Mão na massa (25 min)

**Atividade 2 — Sequência secreta** (do repo):
> "O professor pensa em uma ação (ex: escovar os dentes). A turma tenta adivinhar a ordem
> certa dos passos. Quem acerta, cria o próximo desafio."

Jogue 3 rodadas. Use uma folha para registrar as tentativas da turma no quadro.

**Atividade 3 — Labirinto de setas** (do repo):
> "Desenhe um labirinto e escreva a sequência de setas (⬆️⬇️⬅️➡️) que leva do início ao fim.
> Isso é um **algoritmo**!"

**Pares (o professor forma):** um desenha o labirinto, o outro escreve a sequência de setas.
Depois invertem. Dica do professor: **"comece sempre do mesmo ponto"** — é o conceito de *início de algoritmo*.

### Fase 4 — Projeto / Desafio (15 min)

**Desafio final (do repo):**
> "Explique para alguém de casa como fazer uma tarefa simples (regar uma planta) em 5 passos exatos."

**Critério de pronto (diga isso à turma):**
- [ ] Tem **exatamente 5** passos
- [ ] Cada passo é **um verbo de ação** (pegar, abrir, regar)
- [ ] Começa com "Primeiro..."
- [ ] Alguém de fora **consegue fazer** seguindo (teste real!)

### Fase 5 — Mostra de resultados (5 min)

- 3 alunos leem sua receita de planta.
- Turma aplica os "2 pontinhos": *"Uma coisa que eu gostei + uma sugestão"*.
- Professor fecha: *"Hoje vocês fizeram o que um computador faz: transformaram um problema
  do mundo real em passos que qualquer um pode seguir."*

---

## 📝 Avaliação

| Instrumento | Como aplicar |
|---|---|
| Quiz de 4 perguntas | Bloco `<script>` de `site/trilhas/criancas/01-pensamento.html` (copie o código das perguntas) |
| Observação | Rubrica Semente/Broto/Árvore/Floresta |
| Entrega | Folha "5 passos para regar uma planta" |
| Pergunta de saída | "O que você consegue fazer agora que não conseguia no começo?" |

**Perguntas do quiz (modelo do repo, adapte):**
1. O que é decomposição? → Dividir um problema grande em partes menores
2. Quantos passos deve ter um bom algoritmo? → Tantos quanto precisar, na ordem certa
3. "Pegue o pão. Coloque o queijo." isso é um algoritmo completo? → Não, faltam passos
4. O que um computador faz melhor que a gente? → Seguir passos exatos sem esquecer

---

## 🧩 Exercícios extras (do repositório, para quem terminou)

| Arquivo | Sobre |
|---|---|
| `pensamento_computacional/01_pensamento_computacional/exercicio_01_autoavaliacao.txt` | Autoavaliação inicial |
| `pensamento_computacional/01_pensamento_computacional/exercicio_03_mundo_contrario.txt` | Pensar como o computador (mundo contrário) |
| `pensamento_computacional/01_pensamento_computacional/exercicio_05_desafio_logico.txt` | Desafio lógico |
| `pensamento_computacional/02_decomposicao/exercicio_01_montar_movel.txt` | Decomposição de um móvel |
| `pensamento_computacional/02_decomposicao/exercicio_06_cinco_porques.txt` | Os 5 porquês |
| `pensamento_computacional/03_reconhecimento_padroes/exercicio_03_rotinas.txt` | Rotinas (a rotina da manhã) |
| `pensamento_computacional/04_abstracao/exercicio_01_resumir.txt` | Resumir/abstrair |

---

## 🏠 Para casa

1. Escrever a receita do próprio lanche em 8 passos (com desenho).
2. Perguntar a um adulto: *"Qual tarefa do dia a dia vocês fazem sempre do mesmo jeito?"*
3. Trazer a resposta na próxima aula.

---

## 🖥️ Atividade extra com computador (20 min, opcional)

`laboratorio-tech-social/site/exercicios/desafio-logica.html` — desafio de lógica no navegador.
`laboratorio-tech-social/site/exercicios/pensa-direito` (site `desafio-logica.html`).

---

## ⚠️ Erros comuns a evitar

| Erro | Correção |
|---|---|
| Explicar abstração nos 8 anos | Guarde para a aula A2 ou para 10+ anos |
| Deixar a turma só "brincar" sem registrar | Exija o papel — é o registro da decomposição |
| Corrigir a receita do aluno em vez de perguntar | *"Falta algum passo?"* |
| Pular a "versão errada" da receita | É a parte que faz a turma **sentir** o erro |

---

## 🔗 Próximo módulo

[A2 — Algoritmos e Lógica](02-algoritmos-e-logica.md)

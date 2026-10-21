# A2 — Algoritmos e Lógica (8–12 anos)

**Duração:** 60 min · **Computador:** opcional (Scratch) · **Aula 2 de 12**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de **desenhar um fluxograma de 5 blocos** para uma tarefa
com uma decisão (sim/não) e **ler um pseudocódigo** dizendo o que ele faz.

**Objetivo secundário:** Usar a linguagem "se... então... senão" corretamente.

---

## 📚 Fontes no repositório

| Arquivo | O que traz |
|---|---|
| `pensamento_computacional/05_pensamento_algoritmico/` | 6 exercícios: receita, montagem, decisões, repetições, algoritmo do dia a dia, otimização |
| `pensamento_computacional/06_fluxogramas/` | 6 exercícios: ligar o PC, pedir pizza, verificar idade, lotérica, montar fluxo, corrigir |
| `pensamento_computacional/07_pseudocodigo/` | 6 exercícios: hello world, calculadora, decisão, repetição, lista de compras, programa completo |
| `pensamento_computacional/08_logica_proposicional/` | 6 exercícios: identificar, E, OU, combinar, se-então, paradoxos |
| `laboratorio-tech-social/site/exercicios/desafio-logica.html` | Jogo de lógica no navegador |
| `laboratorio-tech-social/site/exercicios/verdadeiro-falso.html` | Jogo de V/F |
| `laboratorio-tech-social/site/exercicios/robo-labirinto.html` | Labirinto com setas |
| `laboratorio-tech-social/site/exercicios/moeda-dado.html` | Sorteio e aleatoriedade |
| `laboratorio-tech-social/materiais/slides/aula-criancas-01-pensamento.html` | Slide de apoio |

---

## 🧠 Conceitos da aula

| Conceito | Analogia infantil | Onde está |
|---|---|---|
| **Fluxograma** | Um mapa de decisões com setas | `06_fluxogramas/` |
| **Pseudocódigo** | Portuguese de robô — parece programa, mas é frases | `07_pseudocodigo/` |
| **Condicional (se/então)** | "Se estiver chovendo, então levo guarda-chuva" | `08_logica_proposicional/exercicio_05_se_entao.txt` |
| **Repetição (enquanto)** | "Enquanto não terminar a lista, continua" | `05_pensamento_algoritmico/exercicio_04_repeticoes.txt` |
| **Lógica E / OU** | "Precisa fazer **E** os dois" / "serve **OU** este" | `08_logica_proposicional/exercicio_02_e.txt`, `exercicio_03_ou.txt` |

---

## ⏱️ Roteiro

### Fase 1 — Apresentação (5 min)

**Gancho:** *"Quem já jogou um jogo onde você dá ordens e o boneco obedece? Nunca erra.
Nunca. Sabe por quê? Porque ele só faz o que você **escreveu**."*

**Quiz de recuperação (A1):** *"Me deem um exemplo de algoritmo que a gente usa todo dia."*
(Respostas esperadas: escovar dentes, arrumar mochila, fazer lanche.) Guarde no quadro —
você vai usar essas respostas na Fase 4.

### Fase 2 — Exploração (12 min)

**Parte 1 — Fluxograma (10 min).**
Desenhe no quadro um fluxograma de "Levantar e tomar café":

```
      [Acordar]
          |
     [Está com sono?]  -- Sim --> [Dormir mais 5 min] --> (volta ao início)
          |
         Não
          |
   [Levantar da cama]
          |
      [Fazer café]
          |
        [Tomar café]
```

Explique os 3 símbolos do fluxograma:
- **Retângulo** = uma ação
- **Losango (diamante)** = uma decisão (sim/não)
- **Seta** = o caminho

> **Erro comum a evitar:** fluxograma não é lista de tarefas. Fluxograma tem **caminhos
> que se dividem**. Se não tem losango, não é fluxograma.

**Parte 2 — Pseudocódigo (2 min).**
Escreva o mesmo em português de robô:

```
ALGORITMO: CafeDaManha
INICIO
    Acordar
    SE estiver com sono ENTAO
        Dormir 5 minutos
    FIM SE
    Levantar da cama
    Fazer café
    Tomar café
FIM
```

**Regra do pseudocódigo** (do repo `07_pseudocodigo/`): frases curtas, uma instrução por linha,
sem código de computador ainda.

### Fase 3 — Mão na massa (25 min)

**Atividade A — Fluxograma do "Pedir pizza"**
Base: `pensamento_computacional/06_fluxogramas/exercicio_02_pedir_pizza.txt`

Fluxo real: *Tem telefone? → Sim: ligar → Não: usar app → Tem dinheiro? → Sim: pedir → Não: pedir pra alguém com dinheiro.*

**Atividade B — Pseudocódigo do "Ligar o PC"**
Base: `pensamento_computacional/06_fluxogramas/exercicio_01_ligar_pc.txt`
e `07_pseudocodigo/exercicio_01_hello_world.txt`

**Atividade C — Jogo da lógica** (opcional, com computador):
`laboratorio-tech-social/site/exercicios/desafio-logica.html` e `verdadeiro-falso.html`.

**Regras para a turma:**
1. Cada grupo tem 1 folha grande.
2. **Máximo 6 blocos** no fluxograma.
3. **Todo losango precisa de SAÍDAS rotuladas** ("Sim" e "Não").
4. Antes de desenhar: **escreva em palavras**. Depois desenhe. (É decomposição de novo!)

### Fase 4 — Projeto / Desafio (13 min)

**Desafio:** pegue **uma receita da turma** que você anotou no quiz da Fase 1 e transforme
em fluxograma + pseudocódigo.

**Critério de pronto:**
- [ ] Tem pelo menos **1 losango** (uma decisão)
- [ ] Todo bloco está ligado por setas
- [ ] O pseudocódigo tem **a mesma lógica** que o fluxograma
- [ ] Alguém da turma consegue seguir os dois

### Fase 5 — Mostra (5 min)

2 grupos apresentam. Turma compara o fluxograma com o pseudocódigo: *"São a mesma coisa? Onde
ficou diferente?"*

---

## 📝 Avaliação

| Instrumento | Aplicação |
|---|---|
| Quiz | Bloco `<script>` de `site/trilhas/criancas/01-pensamento.html` (adaptar) + `verdadeiro-falso.html` |
| Observação | Rubrica de 4 níveis |
| Entrega | 1 folha com fluxograma + pseudocódigo |
| Pergunta de saída | "O que a seta faz no fluxograma?" |

**Perguntas para o quiz:**
1. Qual formato tem uma decisão? → Losango/diamante
2. "SE X ENTAO Y" é qual conceito? → Condicional
3. Fluxograma sem nenhuma seta é válido? → Não, o caminho sumiu
4. "Enquanto" serve para quê? → Repetição

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `06_fluxogramas/exercicio_03_verificar_idade.txt` | Condicional com idade (bom para 10–12 anos) |
| `06_fluxogramas/exercicio_04_loterica.txt` | Decisão com números |
| `06_fluxogramas/exercicio_06_corrigir.txt` | Ache o erro no fluxo |
| `07_pseudocodigo/exercicio_03_decisao.txt` | Pseudocódigo com decisão |
| `07_pseudocodigo/exercicio_04_repeticao.txt` | Pseudocódigo com laço |
| `07_pseudocodigo/exercicio_05_lista_compras.txt` | Lista de compras (dá para virar projeto de planilha na A5) |
| `05_pensamento_algoritmico/exercicio_06_otimizacao.txt` | "Como deixar o algoritmo mais rápido?" |

---

## 🏠 Para casa

Escolher uma tarefa da rotina da manhã e escrever **os passos + 1 decisão**.
Exemplo: "Se eu perdi o uniforme, então pego outro da gaveta; senão, uso o da mochila."

---

## 🔗 Próximo módulo

[A3 — História da Computação](03-historia-da-computacao.md)

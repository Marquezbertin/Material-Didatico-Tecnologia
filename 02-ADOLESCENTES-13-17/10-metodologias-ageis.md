# B10 — Metodologias Ágeis (Scrum e Kanban) (13–17 anos)

**Duração:** 90 min · **Aula 10 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Explicar **por que o modelo cascata falhou** e o que a abordagem **ágil** muda (entrega em ciclos curtos, feedback rápido, requisito que muda).
2. Descrever o **Scrum**: 3 papéis, os eventos da sprint e os 3 artefatos — incluindo a **definição de pronto**.
3. Montar um **quadro Kanban** (To Do / Doing / Review / Done, com **WIP limit**) e medir **Lead Time** e **Cycle Time**.
4. Rodar uma **sprint simulada de 2 semanas** no projeto da turma (planning, daily, refinamento, revisão, retrospectiva).
5. Calcular e interpretar **velocity**, **lead time**, **cycle time** e **burndown** — e explicar por que a velocity **não serve para comparar pessoas**.

**Objetivo secundário:** Reconhecer Scrum e Kanban como **práticas complementares**, não como religiões — dá para rodar sprint e usar quadro Kanban ao mesmo tempo.

---

## 📚 Fontes no repositório

`formacaoScrumMaster/` — **README + 4 estudos de caso** (repositório de análise crítica, sem código):

| Arquivo | Sobre |
|---|---|
| `formacaoScrumMaster/README.md` | Os 3 objetivos do repositório: aprender na prática, **desenvolver análise crítica** sobre quando usar Scrum, comunidade |
| `formacaoScrumMaster/Estudo de Caso Aplicando Metodologia Agil em QA.md` | Scrum aplicado a QA: DoD, testes contínuos, automação; métricas reais (tempo de execução de testes −40%, cobertura 60% → 85%, defeitos em produção −25%) |
| `formacaoScrumMaster/Estudo de Caso na ING BANK.md` | Transformação ágil de um banco: squads/tribes/chapters/guilds e o uso de **Scrum + Kanban + LeSS** juntos |
| `formacaoScrumMaster/Estudo de Caso Spotfy.md` | O modelo Spotify (squads, tribes, chapters, guilds), "Fail Walls" e post-mortem sem culpa — *o nome do arquivo tem erro de digitação no repositório* |
| `formacaoScrumMaster/Estudo de caso Projeto Scrum Distribuído para Ferrovias Holandesas.md` | **O caso da cascata que falhou**: 3 anos de documentação minuciosa e projeto cancelado; a virada para Scrum entregou no prazo e no orçamento |

`_framework_Scrum/` — **README + 1 imagem exportada do Miro**:

| Arquivo | Sobre |
|---|---|
| `_framework_Scrum/README.md` | O desafio: template do Miro → preencher os esquemas → exportar (PDF/imagem) → entregar via repositório no GitHub |
| `_framework_Scrum/Bruno Bertin - Desafio de Projeto - SCRUM.jpg` | Print do framework Scrum preenchido — modelo visual para desenhar o quadro da turma |

`listadetarefas_qualityAssurance/` — app web (HTML/CSS/JS) usado como **fonte de tarefas** da sprint:

| Arquivo | Sobre |
|---|---|
| `listadetarefas_qualityAssurance/index.html` | App "Lista de Tarefas" com os filtros **Todas / Concluídas / Pendentes** |
| `listadetarefas_qualityAssurance/Planilha de Requisitos.xlsx` | Planilha de requisitos — **origem do backlog** da sprint |
| `listadetarefas_qualityAssurance/Planilha Casos de Teste.xlsx` | Planilha de casos de teste — vira o **Incremento** da sprint |
| `listadetarefas_qualityAssurance/Testes manuais.md` | Testes positivos, negativos e cenários criativos — base da **definição de pronto** |
| `listadetarefas_qualityAssurance/testes_automatizados.md` | Roteiro dos scripts Selenium |
| `listadetarefas_qualityAssurance/tests/example.spec.js` | Teste E2E em Playwright |
| `listadetarefas_qualityAssurance/tests/test_hello_world.py` | Teste em pytest |
| `listadetarefas_qualityAssurance/tests/Testes E2E/` | Scripts E2E e `test_report.txt` |
| `listadetarefas_qualityAssurance/playwright.config.js` e `listadetarefas_qualityAssurance/pytest.ini` | Configuração dos dois frameworks de teste |
| `listadetarefas_qualityAssurance/script_test.py`, `script_test2.py`, `run_tests.bat` | Execução dos testes no Windows |

`laboratorio-tech-social/` — **trilha e site** do projeto:

| Arquivo | Sobre |
|---|---|
| `laboratorio-tech-social/site/exercicios/lista-tarefas.html` | Lista de tarefas jogável no navegador — quadro de papel pronto |
| `laboratorio-tech-social/site/exercicios/planilha.html` | Planilha para montar o backlog e o gráfico de burndown |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Gera dados **fictícios** para popular o backlog do projeto final |

**Links:**
[Scrum Guide oficial (em inglês)](https://scrumguides.org/scrum-guide.html) ·
[Kanban Guide oficial](https://kanban.guide/) ·
[Trello](https://trello.com/) ·
[GitHub Issues — documentação](https://docs.github.com/pt/issues)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Cascata** | "Planejar tudo, entregar no fim. O risco fica escondido até ser tarde demais." |
| **Ágil** | "Entregar **antes** para aprender **antes** de gastar tudo." |
| **Sprint** | "Ciclo curto e fixo (1 a 4 semanas) que termina em algo **usável**." |
| **Product Owner** | "Decide **o quê** e **em que ordem**. Não é o chefe do time." |
| **Scrum Master** | "Cuida do **processo** e remove impedimentos. Não é gerente." |
| **Time de Desenvolvimento** | "Quem constrói: pequena, multidisciplinar e auto-organizada." |
| **Daily (Daily Scrum)** | "15 minutos, de pé, três perguntas: o que fiz, o que farei, o que me trava." |
| **Refinamento** | "Ajustar as histórias **antes** de elas virarem trabalho." |
| **Retrospectiva** | "Olhar para o **processo**, não para a pessoa. Sempre sai 1 ação." |
| **Product Backlog** | "Lista ordenada do que ainda pode virar valor. Sempre muda." |
| **Sprint Backlog** | "O que a equipe **prometeu** fazer nesta sprint." |
| **Incremento** | "O entregável **utilizável** da sprint. Se não dá para usar, não é incremento." |
| **Definição de Pronto (DoD)** | "O checklist que diz 'acabou'. Sem ele, 'pronto' é opinião." |
| **Kanban** | "Fluxo contínuo, sem sprints, com limite de trabalho em andamento." |
| **WIP limit** | "Máximo de tarefas simultâneas por coluna. A coluna lotada **grita** onde está o gargalo." |
| **Lead Time** | "Do pedido até o valor entregue. Mede a **promessa** ao cliente." |
| **Cycle Time** | "Do início da tarefa até o fim. Mede a **eficiência** da equipe." |
| **Velocity** | "Pontos concluídos por sprint. Mede o **time**, nunca as pessoas." |
| **Burndown** | "Restante × dias. Mostra se o plano cabe no tempo." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"A cascata funciona assim: em janeiro a gente anota o que o cliente quer;
em dezembro a gente entrega. Sete meses depois o cliente descobre que mudou de ideia —
e o software já está pronto, errado. Ágil é o oposto: a gente entrega **toda semana**,
o cliente usa, corrige a rota, e a gente entrega de novo."*

**Demonstração ao vivo (5 min):** abra `listadetarefas_qualityAssurance/index.html`
no navegador e mostre a turma criando tarefas e filtrando por
**Todas / Concluídas / Pendentes**. Depois mostre
`listadetarefas_qualityAssurance/Planilha de Requisitos.xlsx` aberto na planilha.

Diga: *"Isso já é um quadro de trabalho. Falta transformar em **quadro**: colunas,
limite de tarefas e ritmo de entrega. É exatamente isso que a aula de hoje monta."*

Feche com a frase: *"Hoje a turma roda uma sprint de verdade — planning, daily,
refinamento, revisão e retrospectiva — em 90 minutos."*

### Fase 2 — Exploração (20 min)

**Parte 1 — Por que a cascata falhou (5 min).**

O caso real está no repositório:
`formacaoScrumMaster/Estudo de caso Projeto Scrum Distribuído para Ferrovias Holandesas.md`.
O projeto do sistema de informação das estações foi conduzido de forma **tradicional**:
documentação minuciosa de requisitos e a expectativa de que o cliente não se
envolvesse depois da entrega. **Três anos depois, o projeto foi cancelado.**
A nova empresa assumiu, adotou Scrum e entregou **dentro do prazo e do orçamento**.

Diga: *"O problema não foi incompetência técnica. Foi **três anos sem feedback**.
Ninguém olhou o software funcionando — e quando olhou, era tarde."*

Some com `formacaoScrumMaster/Estudo de Caso na ING BANK.md`: o banco apontou
**lentidão no desenvolvimento**, **dificuldade de adaptação** e **baixo engajamento**
como problemas do modelo tradicional.

Desenhe no quadro:
```
CASCATA                          ÁGIL
Requisitos ─┐                    Ideia → Sprint 1 → Feedback → ajuste
Análise    │                    Ideia → Sprint 2 → Feedback → ajuste
Desenho    │                    Ideia → Sprint 3 → entrega útil
Codificação├── meses ──▶ entrega
Testes     │
Entrega   ─┘
```
Diga: *"Ágil não é bagunça. É **entregar antes** para **aprender antes**."*

**Parte 2 — Scrum: papéis, eventos e artefatos (8 min).**

**Papéis (3):**

| Papel | O que decide | O que **não** faz |
|---|---|---|
| **Product Owner** | a ordem do backlog, o que é "mais valor agora" | não é gerente de ninguém; não escreve código |
| **Scrum Master** | o processo, remove impedimentos, ensina o Scrum | não é "chefe da equipe" |
| **Time de Desenvolvimento** | como construir, o plano técnico, auto-organização | não são "os outros": **todo mundo** desenvolve |

**Eventos (5, sendo a sprint o container):**

| Evento | Quando | Tempo típico | A pergunta que ele responde |
|---|---|---|---|
| **Sprint** | ciclo de 1 a 4 semanas | — | O que entregamos no fim do ciclo? |
| **Sprint Planning** | dia 0 da sprint | 1–2 h | O que vamos prometer fazer nesta sprint? |
| **Daily (Daily Scrum)** | todo dia útil | 15 min | O que fiz ontem? O que faço hoje? O que me trava? |
| **Refinamento (Backlog Refinement)** | no meio da sprint | 30–60 min | Esta história está pronta para virar trabalho? |
| **Revisão da Sprint** | fim da sprint | 1 h | O que foi entregue atende o que foi pedido? |
| **Retrospectiva** | fim da sprint | 45–60 min | O que vamos melhorar no processo? |

Explique que o **refinamento** não é um evento oficial do Scrum Guide, mas é a
prática mais usada para deixar o backlog com histórias "prontas para puxar".

**Artefatos (3):**

| Artefato | O que é | Quem mantém |
|---|---|---|
| **Product Backlog** | lista ordenada de tudo o que pode virar valor | Product Owner |
| **Sprint Backlog** | o que o time se comprometeu a entregar **nesta** sprint | o próprio time (pode mudar durante a sprint) |
| **Incremento** | o resultado **usável** da sprint (código + testes + documentação) | o time, somado a todos os anteriores |

**Definição de Pronto (DoD)** — monte com a turma, usando
`listadetarefas_qualityAssurance/Testes manuais.md` e
`listadetarefas_qualityAssurance/testes_automatizados.md` como fonte:

```
Definição de Pronto (exemplo real, deste repositório):
- [ ] o app roda no navegador sem erro no console
- [ ] os testes manuais positivos e negativos foram executados
- [ ] 1 teste automatizado passa (Playwright ou pytest)
- [ ] o caso de teste novo está na planilha
- [ ] há commit no Git com mensagem clara
- [ ] o README do repositório está atualizado
```

Diga: *"Sem DoD, cada um decide o que é 'pronto' do seu jeito — e a sprint
termina com 60% pronto e 40% 'quase'."*

**Parte 3 — Kanban (5 min).**

Desenhe o quadro e os limites:
```
   To Do            Doing            Review           Done
  (WIP: ∞)        (WIP: 2)         (WIP: 1)        (WIP: ∞)
┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐
│          │ ──▶ │          │ ──▶ │          │ ──▶ │          │
│  backlog │     │ em curso │     │  revisar │     │  pronto  │
└──────────┘     └──────────┘     └──────────┘     └──────────┘
```

Explicação: quando uma coluna enche, **a fila cresce na frente dela**. A coluna
`Review` lotada significa que **quem revisa é o gargalo** — e a resposta não é
"produzir mais rápido", é aumentar o WIP de `Review` ou adicionar revisor.

**Lead Time × Cycle Time:**
```
Pedido ─────────────────────────────────────────▶ Valor entregue
|<--------------- Lead Time --------------------->|

              Tarefa: entrada em Doing ──────▶ Done
                          |<--- Cycle Time --->|
```

Diga: *"Lead Time é o que o cliente sente. Cycle Time é o que a equipe controla.
Se o Lead Time é 10 dias e o Cycle Time é 2, existe **8 dias parados** em algum
lugar — normalmente na fila de espera, não no trabalho."*

**Parte 4 — Scrum × Kanban (2 min).**

| | **Scrum** | **Kanban** |
|---|---|---|
| Ritmo | Sprints fixas (1–4 semanas) | Fluxo contínuo, sem sprint |
| Quadro | Opcional | **O centro do método** |
| Limite de WIP | Não existe por padrão | **Existe** — é a regra principal |
| Papéis | 3 papéis definidos | Nenhum papel fixo |
| Planejar | No começo da sprint | A cada item, o time puxa quando há vaga |
| Mudança de prioridade | No backlog do produto | A qualquer momento, sem cerimônia |
| Entrega | No fim da sprint | Assim que o item passa pelo quadro |
| Métrica típica | Velocity + burndown | Lead time + cycle time + WIP |
| Risco típico | "Scrum de fachada": cerimônias vazias | Quadro bonito que ninguém olha |
| Serve bem para | Trabalho com escopo razoavelmente estável por ciclo | Suporte, manutenção, tarefas contínuas |

Regra de ouro: **não é "Scrum ou Kanban"**. Dá para rodar sprint de 2 semanas e,
dentro dela, usar um quadro Kanban para enxergar o fluxo. O próprio
`formacaoScrumMaster/Estudo de Caso na ING BANK.md` usa **os dois** — Scrum para
gerenciar o produto, Kanban para visualizar o fluxo e achar gargalos.

### Fase 3 — Mão na massa (40 min)

**Atividade A — Montar o quadro Kanban (15 min).**

Escolha **uma** das duas opções:

- **Planilha / CSV** (funciona offline): `laboratorio-tech-social/site/exercicios/planilha.html`,
  Google Sheets ou Excel.
- **Trello** (visual e gratuito): [trello.com](https://trello.com/) — quadro com 4 listas:
  `To Do`, `Doing`, `Review`, `Done`.

Colunas e limites (escreva o WIP limit **no quadro**, não na memória):
```
To Do    → WIP: ∞   (entrada)
Doing    → WIP: 2   (no máximo 2 tarefas em andamento ao mesmo tempo)
Review   → WIP: 1
Done     → WIP: ∞   (saída)
```

Formato do cartão (5 campos obrigatórios):
```
Título: "Campo vazio não mostra mensagem de erro"
Tipo:   bug | feature | melhoria | documentação
Pontos: 3
Responsável: Ana
Definição de pronto: (resumo ou link)
```

Coloque **10 cartões reais** no `To Do`, tirados de:
- `listadetarefas_qualityAssurance/Planilha de Requisitos.xlsx`
- `listadetarefas_qualityAssurance/Testes manuais.md` (cada item vira um cartão:
  "campo vazio mostra erro", "Enter sem texto não trava", "texto longo é recusado"…)
- `laboratorio-tech-social/site/exercicios/gerador-dados.html` (para popular o backlog
  do projeto final com dados **fictícios**)

**Atividade B — Sprint simulada de 2 semanas (20 min).**

Relógio: cada "dia útil" da sprint dura **2 minutos**. São 10 dias = 20 min.
As cerimônias são jogadas nos momentos indicados.

| Momento | O que acontece | Tempo |
|---|---|---|
| **Sprint Planning** (antes do dia 1) | O PO prioriza o backlog; o time escolhe itens até a capacidade; preenchem o Sprint Backlog | 4 min |
| **Daily** (todo dia) | Cada um responde as 3 perguntas; alguém move um cartão | ~10 s por dia, embutido no dia |
| **Refinamento** (dia 3) | O PO explica 2 histórias que ainda estavam vagas | 2 min |
| **Revisão da Sprint** (dia 10) | O time demonstra o que está pronto (usando o app do repositório!) | 3 min |
| **Retrospectiva** (dia 10) | 3 perguntas + **1 ação** com dono e prazo | 3 min |

Regras do jogo (cumpra, senão a simulação não ensina nada):

1. **O WIP limit é lei.** Se `Doing` já tem 2 cartões, ninguém puxa mais. Quem está
   travado fala na daily — e a turma **tira** o cartão para destravar.
2. Quando um cartão sai de `Doing` para `Review`, outro aluno (o revisor) responde:
   - "Does it work?" — funciona?
   - "Is it tested?" — tem teste?
   - "Is the commit message clear?" — o commit explica o que mudou?

   Dica de frase (do repositório `ingles-para-programadores/09_frases_comuns/exercicio_01_code_review.txt`):
   *"Looks good to me (LGTM)!"* ou *"Could you please add error handling?"*.
3. Cartão **volta** para `Doing` se o revisor pedir mudança.
4. Todo dia, a turma anota **pontos concluídos** e **pontos em andamento**.
5. **Nada de "acelerar" no dia 9** para fechar tudo: o objetivo é ter um dado real
   (com ou sem fila de espera), não um resultado bonito.

**Atividade C — Medir (5 min, dentro da Atividade B).**

Preencha esta tabela a cada dia:
| Dia | Pontos concluídos (Done) | Pontos em Doing | Pontos em Review |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| … | | | |
| 10 | | | |

E calcule, no fim:
- **Velocity** = total de pontos concluídos ÷ número de sprints (aqui: 1 sprint).
- **Lead Time** = tempo entre a entrada do cartão no `To Do` e a chegada ao `Done`.
  Some os tempos e divida pelo número de cartões concluídos → **lead time médio**.
- **Cycle Time** = tempo entre a entrada em `Doing` e a chegada ao `Done`.
- **Burndown**: gráfico de "pontos restantes × dia" (no papel ou em
  `laboratorio-tech-social/site/exercicios/planilha.html`).

Forma esperada do burndown:
```
Pontos
restantes
  30 │●
  25 │  ●
  20 │    ●
  15 │      ●●●
  10 │          ●●
   5 │             ●●
   0 └──────────────────── Dia
     0 1 2 3 4 5 6 7 8 9 10
```
Se a linha **não chega a zero** no dia 10, o plano não cabia na sprint — e isso é
uma descoberta, não um fracasso.

> ⚠️ **Aviso obrigatório sobre a velocity.** A velocity mede a **capacidade do
> time** em um dado momento. **Nunca** compare a velocity de uma pessoa com a de
> outra: isso vira ranking, vira pressão e desmotiva quem está começando. A
> velocity muda com o time, com a complexidade das histórias, com o ambiente e com
> a semana da turma — **não com o valor de uma pessoa**.

### Fase 4 — Projeto (15 min)

**Desafio: "Sprint funcionando na prática"**

Entregue o quadro do **projeto final da turma** com **1 sprint de 2 semanas já
rodada** (simulada em aula ou de verdade durante a semana):

**Critério de pronto:**
- [ ] Quadro Kanban com as **4 colunas** (To Do / Doing / Review / Done) e o **WIP limit escrito** ao lado de cada coluna
- [ ] **Product Backlog** com no mínimo **10 itens**, cada um com tipo, pontos, responsável e DoD
- [ ] Registro de **1 sprint completa**: planning, 2 dailies escritas, refinamento, revisão e retrospectiva
- [ ] Retrospectiva com **1 ação**, com **dono** e **prazo**
- [ ] Tabela de métricas com **velocity**, **lead time médio**, **cycle time médio** e o **gráfico de burndown**
- [ ] O arquivo de métricas commitado no repositório do projeto (é entregável da trilha)
- [ ] Commit com mensagem no padrão do repositório: `docs: add sprint metrics and burndown`

### Fase 5 — Mostra (5 min)

Cada dupla apresenta em **1 minuto**: o quadro (print ou projetor), o burndown e
**1 coisa** que a retrospectiva mudou. A turma pergunta: *"onde estava o gargalo
no fluxo de vocês — e como vocês descobriram?"*

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Quadro Kanban | 4 colunas + WIP limit visível + cartões com os 5 campos |
| Sprint registrada | Planning, dailies, refinamento, revisão e retrospectiva com 1 ação |
| Métricas | velocity, lead time, cycle time e burndown calculados a partir do quadro |
| Compreensão do Scrum | Aluno explica os 3 papéis, os eventos e os 3 artefatos sem consultar |
| Honestidade com métricas | Aluno explica por que a velocity **não** compara pessoas |
| Aplicação no projeto | O quadro usa backlog do repositório (`Planilha de Requisitos.xlsx`), não tarefas inventadas |
| Pergunta de saída | "O que é definição de pronto e por que ela muda o resultado da sprint?" |

**Pergunta de escrita:**
> "A turma rodou uma sprint de 2 semanas e fechou 18 pontos. Na sprint anterior, fechou
> 12. O membro mais novo do time entregou 6 pontos e o mais experiente, 12. O professor
> propõe usar a velocidade individual para decidir 'quem precisa de mais treino'. O que
> você responde, com base nas métricas que você acabou de calcular?"
> **Resposta:** A velocity (18 contra 12 pontos) mede a **capacidade do time** naquele
> ciclo — não o desempenho de ninguém. Os 6 e os 12 pontos individuais dependem de
> fatores que a velocity não separa: o tamanho e a complexidade da história que cada
> um pegou, em que dia pegou, quanto tempo ficou bloqueado esperando revisão ou
> ambiente, e quanto do trabalho era documentação e teste em vez de código. Transformar
> isso em ranking individual é **erro de método**: cria exposição desnecessária de
> adolescentes, desmotiva quem está começando e ainda é um número pequeno demais para
> concluir qualquer coisa (uma sprint só). O uso honesto da métrica é comparar **a
> sprint da equipe com a sprint da equipe**, ajustar a **previsão** do backlog e
> **encontrar o gargalo** — que, no nosso quadro, apareceu no WIP limit da coluna
> `Review`, e não na pessoa.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `formacaoScrumMaster/Estudo de Caso Aplicando Metodologia Agil em QA.md` | Scrum em QA: DoD, testes contínuos, automação e as métricas reais do repositório |
| `formacaoScrumMaster/Estudo de Caso na ING BANK.md` | Scrum **e** Kanban juntos em um banco; squads/tribes/chapters/guilds |
| `formacaoScrumMaster/Estudo de Caso Spotfy.md` | "Fail Walls" e post-mortem sem culpa (nome do arquivo com erro de digitação no repo) |
| `formacaoScrumMaster/Estudo de caso Projeto Scrum Distribuído para Ferrovias Holandesas.md` | O caso da cascata que falhou (3 anos, cancelado) e a virada para Scrum |
| `formacaoScrumMaster/README.md` | Por que a análise crítica do Scrum importa (não é solução única) |
| `_framework_Scrum/README.md` | O desafio do framework Scrum no Miro: template → exportar → GitHub |
| `_framework_Scrum/Bruno Bertin - Desafio de Projeto - SCRUM.jpg` | Print do framework preenchido — modelo visual do quadro |
| `listadetarefas_qualityAssurance/Planilha de Requisitos.xlsx` | Backlog de origem da sprint da turma |
| `listadetarefas_qualityAssurance/Planilha Casos de Teste.xlsx` | Itens que viram o Incremento |
| `listadetarefas_qualityAssurance/Testes manuais.md` | Testes positivos, negativos e criativos → base da DoD |
| `listadetarefas_qualityAssurance/testes_automatizados.md` | Roteiro dos scripts Selenium |
| `listadetarefas_qualityAssurance/tests/example.spec.js` | Teste E2E em Playwright |
| `listadetarefas_qualityAssurance/tests/test_hello_world.py` | Teste em pytest |
| `listadetarefas_qualityAssurance/tests/Testes E2E/test_report.txt` | Relatório de execução dos testes E2E |
| `listadetarefas_qualityAssurance/playwright.config.js` | Configuração do Playwright no repositório |
| `listadetarefas_qualityAssurance/pytest.ini` | Configuração do pytest no repositório |
| `laboratorio-tech-social/site/exercicios/lista-tarefas.html` | Quadro de tarefas jogável no navegador |
| `laboratorio-tech-social/site/exercicios/planilha.html` | Planilha para o backlog e o burndown |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Dados fictícios para popular o backlog |
| `ingles-para-programadores/05_vocabulario_qa/exercicio_04_sprint.txt` | Vocabulário de sprint em inglês (backlog, blockers, retrospective) |
| `ingles-para-programadores/09_frases_comuns/exercicio_01_code_review.txt` | "Looks good to me (LGTM)!" e frases de code review |

---

## 🏠 Para casa

1. Escolher **1** item do `listadetarefas_qualityAssurance/Planilha de Requisitos.xlsx`
   e escrevê-lo como **história de usuário**: "Como [persona], eu quero [ação], para que
   [benefício]" — com **1 critério de aceite** no formato Given/When/Then.
2. Rodar o quadro Kanban **de verdade** por **2 dias** (no projeto da turma ou na
   lição de casa). No fim de cada dia, registrar: pontos concluídos, pontos em
   `Doing` e o lead time de cada cartão concluído.
3. Escrever a **primeira retrospectiva** da história: as 3 perguntas
   (o que foi bem, o que não foi, o que melhorar) + **1 ação com dono e prazo**.
4. Ler `formacaoScrumMaster/Estudo de Caso Aplicando Metodologia Agil em QA.md` e
   responder: *"qual das métricas desse repositório eu usaria no projeto da turma —
   e por quê?"*

---

## 🔗 Próximo módulo

[B11 — Cibersegurança, Ética e Paradigmas](11-ciberseguranca-etica.md)

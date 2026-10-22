# 🚀 Trilha ADOLESCENTES (13–17 anos) — Makers/Devs

**Carga horária:** 16 aulas × 90 min = **24 horas**
**Público:** "Makers/Devs" (nome do plano pedagógico)
**Ambientação:** cada aluno com **notebook próprio** é o ideal; a trilha foi desenhada
para funcionar com **1 PC por 2 alunos** (papel → teclado).

> Fontes: `laboratorio-tech-social/trilhas/adolescentes-13-20/`,
> `laboratorio-tech-social/site/trilhas/adolescentes/`,
> `python-do-zero/`, `html-css-js-pratica/`, `banco-de-dados-sql/`,
> `git-github-iniciantes/`, `manual-qa-completo/`, `ia-para-iniciantes/`,
> `ingles-para-programadores/`, `formacaoScrumMaster/`, `qa-exercicios-praticos/`.

---

## Mapa da trilha (12 módulos, 16 aulas)

| Aula | Módulo | Repo-base | Entregável |
|---|---|---|---|
| 01 | [B1 — Pensamento Computacional Avançado](01-pensamento-computacional-avancado.md) | `pensamento_computacional` | Fluxograma + pseudocódigo de um sistema real |
| 02 | [B2 — Lógica e Algoritmos](02-logica-e-algoritmos.md) | `logica_programacao` (80 algoritmos) | 8 algoritmos em pseudocódigo + 2 em Visualg |
| 03 | [B3 — Python do Zero](03-python.md) | `python-do-zero` (15 módulos/90 exercícios) | 5 scripts rodando |
| 04 | [B4 — Python: projects](04-python-projetos.md) | `lista-de-exercicios-python-brasil` (112) | 1 mini-jogo + 1 script de automação |
| 05 | [B5 — Web: HTML, CSS, JS](05-web.md) | `html-css-js-pratica` (15 módulos) | Site responsivo de 3 páginas |
| 06 | [B6 — Banco de Dados e SQL](06-banco-de-dados-sql.md) | `banco-de-dados-sql` (15 módulos) | Schema + 10 consultas do projeto |
| 07 | [B7 — Git e GitHub](07-git-github.md) | `git-github-iniciantes` (15 módulos) | Repositório + 10 commits + README + Pages |
| 08 | [B8 — QA: Teste de Software](08-qa-teste-de-software.md) | `manual-qa-completo` + `qa-exercicios-praticos` | Plano de teste + 1 bug corrigido |
| 09 | [B9 — IA para Iniciantes](09-ia.md) | `ia-para-iniciantes` (15 módulos) | 1 chatbot/gerador com prompt avaliado |
| 10 | [B10 — Metodologias Ágeis (Scrum/Kanban)](10-metodologias-ageis.md) | `formacaoScrumMaster` | Sprint funcionando na prática |
| 11 | [B11 — Cibersegurança, Ética e Paradigmas](11-ciberseguranca-etica.md) | `pensamento_computacional/13 e 15` | Política de segurança do projeto + aula aberta |
| 12 | [B12 — Inglês Técnico](12-ingles-tecnico.md) | `ingles-para-programadores` | README do projeto em inglês |
| 13 | **Projeto Final — parte 1** | todos | Escopo + protótipo |
| 14 | **Projeto Final — parte 2** | todos | Implementação |
| 15 | **Projeto Final — parte 3** | todos | Testes + deploy |
| 16 | **Showcase** | todos | Apresentação + publicação |

**Plano de contingência:** se a escola só puder oferecer 8 aulas, use a marca ⭐ no
mapa acima (aula que é indispensável).

---

## Objetivos do plano pedagógico (Makers/Devs)

1. **Dominar uma linguagem de programação** (Python) com proficiência intermediária.
2. **Criar aplicações web** responsivas com HTML, CSS e JavaScript.
3. **Escrever e executar testes automatizados** entendendo o ciclo de vida do bug.
4. **Aplicar metodologias ágeis** em projetos colaborativos.
5. **Publicar projetos open source** que gerem impacto social na comunidade.
6. **Compreender implicações éticas** de decisões tecnológicas.

**Objetivo final do repositório:** *"Entregar um **projeto de impacto social** em open source
(..., bot de dados do Esporte São Pedro, ferramenta de QA educativa). Publicado no GitHub Pages."*

---

## Regras da sala com adolescentes

| Regra | Por quê |
|---|---|
| **Erro é método** — o professor pergunta, não entrega | autonomia |
| **"Commit ou não existe"** | versionamento desde o dia 1 |
| **Nada é secreto** — README documenta tudo | o README é a avaliação |
| ** IA é ferramenta, não autor** | todo código gerado por IA precisa de revisão humana |
| **Nenhum dado real de aluno em repositório público** | ver `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §9 |
| **Teste que não roda é bug** | aprendo QA na própria pele |

---

## Materiais e contas

| Item | Detalhe |
|---|---|
| Python 3.10+ | ou [Google Colab](https://colab.research.google.com/) — sem instalar nada |
| Navegador | Chrome ou Firefox |
| Editor | VS Code (o repositório `laboratorio-tech-social` sugere; ou o ID do Colab) |
| Git | instalado no notebook (ou [GitHub Desktop](https://desktop.github.com/)) |
| Conta GitHub | [https://github.com/signup](https://github.com/signup) — **obrigatória na aula 07** |
| Conta de IA | a escola define qual usar; ver `ia-para-iniciantes/01_ia_generativa/` |
| Scratch | não é mais necessário (a trilha de 8–12 já cobriu) |

**Todos os cursos do professor rodam offline**: `python-do-zero` traz os exercícios em `.txt`
com "Resposta Esperada" — pode ser aplicado **sem internet**, com o aluno testando no Colab
depois.

---

## Ambiente de trabalho padrão da turma (o "kit do Maker")

Crie um repositório-base para a turma e distribua:

```
projeto-da-turma/
├── README.md            # índice da turma (veja B12 para a versão em inglês)
├── docs/
│   ├── decisoes.md      # ADR simplificado: cada decisão técnica tem data e motivo
│   └──setup.md         # como rodar o projeto
├── src/                 # código
├── tests/               # testes automatizados
├── data/                # dados (CSV/JSON) — **sem dados pessoais reais**
└── notas/               # anotações das aulas
```

> Esse esqueleto vem da prática real dos repositórios do autor
> (`qa-automation-framework`, `central-de-noticias`, `esporte-sao-pedro`).

---

## Avaliação

| Componente | Peso | Onde está o critério |
|---|---|---|
| Participação e exercícios | 20% | `04-BANCO-DE-EXERCICIOS/` |
| Commits e histórico Git | 20% | `02-ADOLESCENTES-13-17/07-git-github.md` |
| Qualidade de código e testes | 20% | `08-qa-teste-de-software.md` |
| Projeto final | 30% | `13-projeto-final.md` |
| Mostra / Showcase | 10% | `13-projeto-final.md` |

Rubrica detalhada (4 níveis) em `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §4.1.

---

## Slides prontos (do repositório)

| Slide | Arquivo |
|---|---|
| Python | `laboratorio-tech-social/materiais/slides/aula-teens-01-python.html` |
| Web | `laboratorio-tech-social/materiais/slides/aula-teens-02-web.html` |
| QA | `laboratorio-tech-social/materiais/slides/aula-teens-03-qa.html` |
| Dados | `laboratorio-tech-social/materiais/slides/aula-teens-04-dados.html` |
| IoT | `laboratorio-tech-social/materiais/slides/aula-teens-05-iot.html` |
| Projeto | `laboratorio-tech-social/materiais/slides/aula-teens-06-projeto.html` |
| História | `laboratorio-tech-social/site/slides/aula-teens-07-historia-computacao.html` |

**Trilha web da turma (13–20):** `laboratorio-tech-social/site/trilhas/adolescentes/`
→ `01-python.html`, `02-web.html`, `03-qa.html`, `04-dados.html`, `05-iot.html`,
`06-projeto.html`, `07-historia-computacao.html`, `08-informatica.html`.

**Módulos em markdown do repositório:**
`trilhas/adolescentes-13-20/modulo-03-qa-testes.md`,
`modulo-04-ciencia-dados.md`, `modulo-05-iot-nuvem.md`, `modulo-06-projeto-social.md`.

---

## Onde a turma Treina por conta (games)

`QA_RUN/` — **71 jogos educativos** de QA, HTML5, jogáveis no navegador.
Os mais úteis para esta trilha:

| Jogo | Caminho | Conceito |
|---|---|---|
| Quiz Duel | `QA_RUN/js/games/quizduel.js` | Conceitos de QA |
| Caça-Bugs | `laboratorio-tech-social/site/exercicios/caca-bugs.html` | Encontrar bugs |
| Plano de Testes | `laboratorio-tech-social/site/exercicios/plano-testes.html` | Escrever plano de teste |
| Simulador de API | `laboratorio-tech-social/site/exercicios/simulador-api.html` | API e status HTTP |
| Validador de Regex | `laboratorio-tech-social/site/exercicios/validador-regex.html` | Expressões regulares |
| Desafios Python | `laboratorio-tech-social/site/exercicios/desafios-python.html` | Fixação de sintaxe |
| Code Builder | `laboratorio-tech-social/site/exercicios/code-builder.html` | Montar lógica em blocos |
| Simulador de Robótica | `laboratorio-tech-social/site/exercicios/simulador-robotica.html` | Sensores e automação |
| Despertar da Qualidade | `QA_RUN/js/games/quizduel.js` + `questionario_despertardaqualidade/` | Quiz de 10 questões V/F |

---

## 🔗 Próxima trilha

[03-JOVENS-E-ADULTOS-18+](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md)

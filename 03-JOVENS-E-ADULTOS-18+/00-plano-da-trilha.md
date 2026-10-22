# Trilha JOVENS E ADULTOS (18+) — Profissionais

**Carga horária:** 16 aulas × 90 min = **24 horas**
**Público:** adultos que já usam computador no dia a dia (trabalho, estudo ou
empreendedorismo) e querem **automatizar a rotina** e **entregar software com qualidade**.
**Ambientação:** 1 computador por aluno, com **terminal e Python 3.10+** instalados.

> Esta trilha **não está** no plano pedagógico original do autor (que cobre até 20 anos).
> Ela foi construída a partir dos repositórios `manual-qa-completo`,
> `qa-automation-framework`, `art-of-software-testing`, `agente_qaIA`, `formacaoScrumMaster`,
> `_framework_Scrum`, `saucedemo_robot`, `katalon_automatizacao`, `tdm-app`,
> `listadetarefas_qualityAssurance`, `Analise-de-Dados`, `Central-de-noticias`, `anyms`,
> `esporte-sao-pedro` e `hubias-estudos` — ver
> `00-GUIA-DO-PROFESSOR/01-plano-de-ensino-geral.md` §1.3.

---

## 🎯 Objetivo da trilha

Ao final das 16 aulas, o aluno será capaz de:

1. **Automatizar tarefas** da sua rotina real com scripts de shell e scripts Python
   versionados no Git.
2. **Diagnosticar problemas** lendo logs, testando hipóteses no terminal e usando o
   princípio do **menor privilégio** ao lidar com permissões e dados.
3. **Publicar código profissional**: repositório com README, testes, automação de
   integração contínua e deploy.
4. **Tratar dados** (CSV, planilhas, JSON) de forma confiável, com backup e operação
   reversível.
5. **Aplicar segurança e LGPD** em tudo que fizer — inclusive nos arquivos do projeto.
6. **Usar IA como ferramenta** com revisão humana, prompt versionado e critério de aceite.
7. **Entregar um projeto completo** no formato open source, com métricas e análise de risco.

---

## Público e pré-requisitos

| Item | Descrição |
|---|---|
| **Para quem é** | Profissionais, estudantes de nível superior, professores, PDEs e qualquer pessoa que trabalha com planilha e arquivo todo dia |
| **Pré-requisito obrigatório** | Ler e escrever arquivo de texto; usar navegador; instalar software |
| **Pré-requisito desejável** | Já ter usado Git; já ter programado qualquer linguagem |
| **Nível de programação** | Iniciante em Python, **intermediário** em shell é vantagem (não é pré-requisito) |
| **Não é pré-requisito** | Saber JavaScript, saber banco de dados, saber Linux avançado |
| **Idade mínima sugerida** | 18 anos (pela natureza dos temas: LGPD, dados, deploy) |

**Se o aluno nunca usou o terminal:** a aula 01 já começa do zero (abrir, navegar,
ler arquivos). Não é preciso preparo prévio.

---

## Carga horária

| Item | Valor |
|---|---|
| Aulas | 16 × 90 min |
| Carga total | **24 horas** |
| Módulos | 7 (todos escritos) |
| Percentual de prática | ~70% (regra do ciclo didático: 1/3 teoria, 2/3 prática) |
| Avaliação | Formativa, com **rubrica de 4 níveis** e **certificado** ao final |

**Plano de contingência:** se a empresa só puder oferecer 8 aulas, use as aulas
**01, 02, 03, 04, 05, 06 e 13–16** (o núcleo: automatizar, versionar, publicar e entregar).

---

## Mapa da trilha (7 módulos, 16 aulas)

| Aula | Módulo | Repo-base | Entregável |
|---|---|---|---|
| 01 | **[01 — Linha de Comando e Automação do Sistema](01-linha-de-comando.md)** (parte 1) | `manual-qa-completo` (`Makefile`, `run_all.py`) | Navegação, pipes, permissões e **script de shell** com log e código de saída |
| 02 | **01 — Linha de Comando** (parte 2) | `Central-de-noticias/.github/workflows/update-news.yml` (cron real) | **1 rotina automatizada com cron** + versionamento do script |
| 03 | **[02 — Python para Automatizar a Rotina](02-python-para-automatizar.md)** (parte 1) | `python-do-zero` (15 módulos / 90 exercícios `.txt`) | **1 script real rodando** (CSV/JSON) no ambiente `venv` |
| 04 | **02 — Python para Automatizar** (parte 2) | `manual-qa-completo/docs/03/scripts/estimate.py` | Script com **backup + `--dry-run`** + **teste automatizado** (`unittest`) |
| 05 | **[03 — Git e GitHub profissional](03-git-e-github-profissional.md)** (parte 1) | `git-github-iniciantes` (15 módulos) | Repositório profissional: 20+ commits, `.gitignore`, `README`, `LICENSE` |
| 06 | **03 — Git e GitHub profissional** (parte 2) | `git-github-iniciantes` (10–15) | Branch, PR com revisão, **GitHub Actions** em cada push |
| 07 | **[04 — Dados e Planilhas](04-dados-e-planilhas.md)** (parte 1) | `Analise-de-Dados` (7 datasets + notebook) | Leitura e limpeza de CSV/XLSX com `pandas` ou `openpyxl` |
| 08 | **04 — Dados e Planilhas** (parte 2) | `planilhaeletronicas` (Flask + Pandas → Excel) | Relatório automatizado em Excel, com histórico e backup |
| 09 | **[05 — Segurança Digital e LGPD](05-seguranca-digital-e-lgpd.md)** (parte 1) | `manual-qa-completo/docs/11` (OWASP) | Política de dados do projeto + **threat model** de 1 página |
| 10 | **05 — Segurança Digital e LGPD** (parte 2) | `manual-qa-completo/docs/11/scripts/secret_scan.py` | Scanner de segredos no repositório + checklist de LGPD |
| 11 | **[06 — IA no Trabalho](06-ia-no-trabalho.md)** (parte 1) | `ia-para-iniciantes` (15 módulos) | Prompt versionado com **critério de aceite** e 3 testes de saída |
| 12 | **06 — IA no Trabalho** (parte 2) | `agente_qaIA` (agente de QA com MCP e OpenCode) | Automação com revisão humana obrigatória + registro de uso |
| 13 | **[07 — Projeto Final](07-projeto-final.md)** (parte 1: escopo) | todos | Escopo, plano de testes e backlog priorizado |
| 14 | **07 — Projeto Final** (parte 2: implementação) | todos | Implementação com **métricas** (tempo, cobertura, KPI) |
| 15 | **07 — Projeto Final** (parte 3: qualidade e entrega) | `manual-qa-completo` (quality gates) | Testes verdes, pipeline, relatório de risco e documentação |
| 16 | **07 — Projeto Final** (parte 4: showcase) | todos | Repositório público + apresentação de 5 min + certificado |

> **Todos os 7 módulos estão escritos** e prontos para uso. Cada arquivo de módulo traz
> o ciclo didático completo (5 fases), avaliação, exercícios extras e "Para casa".

**Objetivo final do repositório do aluno:** *entregar uma **automação real da própria
rotina** (script de shell + script Python + testes), versionada, documentada e publicada
no GitHub — com dados **fictícios** ou autorizados.*

---

## Como usar este material fora da escola (autodidata)

Este material foi escrito para a **sala**, mas ele funciona **sozinho**. Se você está
estudando por conta, siga este roteiro:

### Passo 1 — Não tente fazer tudo de uma vez

Faça **1 módulo por semana**, no ritmo de 2 h por sessão. A trilha inteira leva **4 meses**
nesse ritmo — e isso é o esperado. Não existe atalho: o skill de automação se constrói
fazendo.

### Passo 2 — Use os repositórios como laboratório real

Todos os exercícios apontam para arquivos que **existem** em repositórios públicos do
autor. Em vez de copiar o exercício, **clone o repositório e rode o código**:

```bash
git clone https://github.com/Marquezbertin/manual-qa-completo.git
cd manual-qa-completo
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
python run_all.py               # roda os 5 scripts standalone
```

Você vai ver **scripts de verdade** rodando: estimativa PERT, triagem de severidade,
percentis p95/p99, *quality gate* e KPIs de qualidade.

### Passo 3 — Entregue no seu GitHub

Crie um repositório **seu** por módulo e publique. O objetivo não é o exercício — é o
**histórico**: 24 horas de trabalho versionado é o que prova que você aprendeu.

### Passo 4 — Substitua os dados de exemplo pelos seus (com cuidado)

Os exercícios usam dados fictícios. Quando trocar pelos seus dados reais, lembre:
- **LGPD vale para você também** (módulo 05).
- Faça **backup** antes de qualquer operação destrutiva (módulo 02).
- Nunca coloque **segredo** em repositório (módulo 03).

### Passo 5 — Use os jogos do `QA_RUN` como revisão

O hub tem **71 jogos educativos** que revisam conceitos de QA, Git, SQL, segurança e
sistemas — 15 min por semana, no intervalo, é suficiente para manter a base viva.

### Roteiro de autostudy por semana

| Semana | Módulo | Tarefa de 2 h |
|---|---|---|
| 1–2 | 01 — Linha de comando | Script de shell + rotina com cron no seu computador |
| 3–4 | 02 — Python | Script real da sua rotina + 3 testes `unittest` |
| 5–6 | 03 — Git e GitHub | Repositório dos 2 módulos anteriores, 20 commits, CI ativa |
| 7–8 | 04 — Dados | Relatório automatizado do seu CSV |
| 9–10 | 05 — Segurança e LGPD | Política de dados + scanner de segredos no seu repo |
| 11–12 | 06 — IA | Prompt versionado + automação com revisão humana |
| 13–16 | 07 — Projeto final | Consolide tudo num repositório público |

### Quando travar

1. Roda `man <comando>` e `--help`. A resposta está na própria ferramenta.
2. Lê o **código** do repositório do autor que está exercendo — ele é a documentação.
3. Procura no histórico do Git: `git log -S "termo"` encontra quem mudou e por quê.
4. Pergunta em fórum/issue do repositório — é o canal que o próprio autor usa.

---

## Materiais e contas

| Item | Detalhe | Custo |
|---|---|---|
| Sistema operacional | Windows 10/11, Linux ou macOS | — |
| Terminal | **Linux/macOS:** Terminal. **Windows:** [Subsistema Linux para Windows (WSL)](https://learn.microsoft.com/pt-br/windows/wsl/install) ou Git Bash | R$ 0 |
| Python 3.10+ | [python.org](https://www.python.org/downloads/) — ou [Google Colab](https://colab.research.google.com/) para quem não quer instalar | R$ 0 |
| Editor | VS Code | R$ 0 |
| Git | [git-scm.com](https://git-scm.com/downloads) | R$ 0 |
| Conta GitHub | [github.com/signup](https://github.com/signup) — **obrigatória na aula 05** | R$ 0 |
| Conta de IA | a empresa define qual usar (ver `ia-para-iniciantes/06_prompt_engeneering/`) | R$ 0 |
| Hospedagem do site | [GitHub Pages](https://pages.github.com/) | R$ 0 |
| Ferramentas extras | `sqlite3`, `jq`, `openpyxl`, `requests`, `pytest` | R$ 0 |

**Contas de serviço que exigem cartão (nunca use dados reais de cliente sem contrato):**
Supabase, Cloudinary, APIs de IA com plano pago. Para a trilha, **todas as ferramentas
usadas têm plano gratuito**.

**Todo o material roda offline:** os exercícios do `python-do-zero` e da
`lista-de-exercicios-python-brasil` são arquivos `.txt` com "Resposta Esperada".

---

## Regras da sala adulta

| Regra | Por quê |
|---|---|
| **Erro é método** — o professor pergunta, não entrega | autonomia; adulto aprende mais rápido testando do que ouvindo |
| **Dados fictícios por padrão** — nada de dado real de cliente sem autorização | LGPD e ética profissional |
| **LGPD vale para tudo** — planilha do RH, e-mail do cliente, foto do badge | o módulo 05 não é teórico: é a sua rotina |
| **Backup antes de operação destrutiva** | nenhum script apaga sem cópia |
| **Nada de segredo no repositório** — nem em arquivo, nem no histórico | `.env` no Git vaza para sempre |
| **Documentação é parte do trabalho** — README e log não são burocracia | o que não está escrito não existe para o próximo |
| **IA é ferramenta, não autor** — toda saída de IA passa por revisão humana | o modelo responde; a responsabilidade é sua |
| **Teste que não roda é bug** | inclusive em script pessoal |

> **Nota ao professor:** a turma adulta tem **horário de trabalho**. Evite a aula de
> segunda às 19h. A abordagem que funciona melhor é **aula de 90 min com entrega
> assíncrona**: o aluno termina a tarefa em casa e traz o resultado na aula seguinte.

---

## Avaliação e certificado

| Componente | Peso | Onde é medido |
|---|---|---|
| Participação e exercícios práticos | 20% | Scripts entregues e **rodando** |
| Qualidade do código e dos testes | 25% | Testes automatizados + tratamento de erro |
| Versionamento e documentação | 20% | Commits, README, estrutura de pastas |
| Projeto final | 25% | `07-projeto-final` da trilha de adultos |
| Showcase | 10% | Apresentação de 5 min |

**Rubrica (4 níveis, de `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §4.3):**

| Nível | Descrição |
|---|---|
| **1** | Não entregou. |
| **2** | Entregue com falha funcional ou sem documentação. |
| **3** | Entregue, testado, documentado. |
| **4** | Entregue, testado, documentado, com **métricas** (cobertura, KPI, tempo) e **análise de risco**. |

**Para chegar no nível 4**, use os scripts do `manual-qa-completo` como referência do
que se espera de um profissional: `docs/09/scripts/kpi.py` (KPIs), `docs/08/scripts/quality_gate.py`
(gate de qualidade), `docs/03/scripts/estimate.py` (estimativa PERT).

**Certificado:** modelo real em
`laboratorio-tech-social/materiais/templates/certificado/modelo-certificado.md`
e página navegável em `laboratorio-tech-social/site/certificado/index.html`
(com `verificar.html` para conferência). Preencha com **nome e CPF do aluno** (a trilha
é 18+, então os dados pessoais do certificado são do próprio aluno, com autorização) e
registre: trilha cursada, carga horária, data e código de verificação.

> O certificado do laboratório é o modelo **do curso**; para a trilha adulta, a
> certificação é **interna da empresa/instituição** e deve constar em registro próprio.

---

## Onde treinar por conta (games e laboratórios)

| Onde | O quê | Caminho real |
|---|---|---|
| **QA_RUN — Hub de jogos** | **71 jogos educativos** HTML5, jogáveis no navegador (teclado ou controle USB). Conceitos de QA, Git, SQL, segurança, sistemas e lógica | `QA_RUN/index.html` · `QA_RUN/js/games/*.js` (1 arquivo por jogo) |
| **QA_RUN — smoke test** | Teste de integração headless que valida o boot dos módulos, o registro dos 71 jogos e 40 frames de cada jogo | `QA_RUN/tests/smoke.js` (`node tests/smoke.js`) |
| **Laboratório Tech Social — exercícios** | 41 páginas de exercício interativo (HTML único por arquivo): simulador de API, validador de regex, caça-bugs, gerador de dados fictícios, plano de testes, quizzes | `laboratorio-tech-social/site/exercicios/` |
| **Laboratório Tech Social — trilhas** | Trilhas web de crianças e adolescentes (referência de ritmo e linguagem) | `laboratorio-tech-social/site/trilhas/` |
| **QA — simulados em Markdown** | 2 simulados com gabarito comentado (fundamentos; API, SQL e segurança) | `qa-exercicios-praticos/simulados/` |
| **QA — sites para testar** | 10 sites com bugs plantados para treinar a caça | `qa-exercicios-praticos/sites-para-testar/` |
| **QA — templates** | Bug report, plano de teste, caso de teste, checklist de smoke e aceite, relatório | `qa-exercicios-praticos/modelos-templates/` |
| **QA — planilha de casos** | Planilha de casos de teste e de requisitos de um projeto real (`.xlsx`) | `listadetarefas_qualityAssurance/` |
| **Scrum — casos reais** | 4 estudos de caso de Scrum (aplicando metodologia ágil em QA, ING Bank, projeto distribuído para ferrovias holandesas e Spotify) | `formacaoScrumMaster/` |

**Jogos do `QA_RUN` mais úteis para a trilha adulta:**

| Jogo | Arquivo | Conceito |
|---|---|---|
| Terminal Typer | `QA_RUN/js/games/` (jogo 23) | Comandos de terminal na ordem correta |
| Git Flow | `QA_RUN/js/games/` (jogo 44) | Próximo comando Git do fluxo de trabalho |
| Deploy Simulator | `QA_RUN/js/games/` (jogo 8) | Pipeline build → teste → staging → produção |
| Log Watch | `QA_RUN/js/games/` (jogo 63) | Varredura de logs: separar suspeito de legítimo |
| Phish Out | `QA_RUN/js/games/` (jogo 38) | Separar e-mail seguro de phishing |
| Password Fortress | `QA_RUN/js/games/` (jogo 39) | Escolher a senha mais forte |
| Bug Hunt | `QA_RUN/js/games/` (jogo 2) | Caçar bugs em 5 telas de app |

> Os arquivos em `QA_RUN/js/games/` são **1 por jogo** — abra `QA_RUN/index.html` e use o
> hub; não é preciso saber o nome exato do arquivo para jogar.

---

## 🔗 Próximo módulo

[01 — Linha de Comando e Automação do Sistema (18+)](01-linha-de-comando.md)

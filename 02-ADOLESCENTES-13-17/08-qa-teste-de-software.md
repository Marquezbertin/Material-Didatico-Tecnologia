# B8 — QA: Teste de Software (13–17 anos)

**Duração:** 90 min · **Aula 8 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Diferenciar **bug**, **defeito** e **falha**, e explicar por que **QA é processo** e não "achar erro".
2. Escrever **casos de teste** com pré-condição, passos numerados e resultado esperado, e transformar um caso falho em **bug report** completo.
3. Classificar um bug por **severidade** e **prioridade** (são coisas diferentes!) e acompanhar o **ciclo de vida do bug**.
4. Executar um **plano de teste** simples e corrigir **1 bug real** provando a correção com um teste automatizado em Python (`unittest`).

**Objetivo secundário:** Reconhecer os **4 níveis de teste** (unitário, integração, sistema, aceite) e explicar a **pirâmide de testes** com um exemplo do próprio projeto da turma.

---

## 📚 Fontes no repositório

`manual-qa-completo/` — **11 módulos bilíngues (PT/EN)**, com scripts Python executáveis e 8 templates prontos:

| Módulo | Conteúdo | Arquivos-chave |
|---|---|---|
| `docs/01/PT/indice.md` | QA vs QC vs Teste, 7 princípios ISTQB, custo da qualidade | `docs/01/PT/indice.md` |
| `docs/02/PT/indice.md` | ISO/IEC 25010, V-Model, atributos mensuráveis | `docs/02/PT/indice.md` |
| `docs/03/PT/indice.md` | Política / Estratégia / Plano de Teste, estimativa PERT | `docs/03/PT/indice.md` · `docs/03/scripts/estimate.py` |
| `docs/04/PT/indice.md` | Casos de teste, SBTM, **severidade × prioridade**, Nielsen | `docs/04/PT/indice.md` · `docs/04/scripts/triage.py` |
| `docs/05/PT/indice.md` | **Pirâmide de teste**, Page Objects, Playwright + Pytest | `docs/05/PT/indice.md` · `docs/05/scripts/tests/test_login.py` |
| `docs/06/PT/indice.md` | Verbos HTTP, contratos, `jsonschema` | `docs/06/PT/indice.md` · `docs/06/scripts/test_api.py` |
| `docs/07/PT/indice.md` | Carga, estresse, pico, resistência, p95/p99 | `docs/07/PT/indice.md` · `docs/07/scripts/locustfile.py` |
| `docs/08/PT/indice.md` | Cobertura, lint, quality gates, SAST | `docs/08/PT/indice.md` · `docs/08/scripts/quality_gate.py` |
| `docs/09/PT/indice.md` | TMMi, KPIs, Risk-Based Testing, PDCA | `docs/09/PT/indice.md` · `docs/09/scripts/kpi.py` |
| `docs/10/PT/` | **8 templates**: plano de teste, caso de teste, bug report, charter, checklist de aceite, matriz de rastreabilidade, glossário e soluções | `docs/10/PT/test_plan_template.md` · `docs/10/PT/test_case_template.md` · `docs/10/PT/bug_report_template.md` · `docs/10/PT/charter_template.md` · `docs/10/PT/checklist_aceite.md` · `docs/10/PT/matriz_rastreabilidade.md` · `docs/10/PT/glossario.md` · `docs/10/PT/solucoes.md` |
| `docs/11/PT/indice.md` | OWASP Top 10, SAST/DAST, secret scanning | `docs/11/PT/indice.md` · `docs/11/scripts/secret_scan.py` |

`qa-exercicios-praticos/` — **9 sites simulados com bugs intencionais** + roteiro de teste e gabarito para cada um:

| Empresa (pasta em `sites-para-testar/`) | Sistema | Dificuldade |
|---|---|---|
| `momento-matador/` | Loja de games (busca, descontos) | ★☆☆ |
| `techstore/` | Loja virtual (carrinho, cupons, frete) | ★★☆ |
| `portal-cliente/` | Cadastro e login (validações, duplicidade) | ★★☆ |
| `crm-connect/` | Gestão de clientes (CRUD, busca) | ★★☆ |
| `banco-abc/` | Internet banking (transferência, taxa, extrato) | ★★★ |
| `foodgo/` | Delivery (combos, troco, CEP, horário) | ★★★ |
| `hotel-reserva/` | Reservas de hotel (datas, promoção) | ★★★ |
| `calc-impostos/` | Calculadora de impostos (regra de negócio) | ★★★ |
| `agenda-medica/` | Agendamento médico (conflitos, domingo) | ★★★ |

Cada pasta tem **três arquivos**: `index.html` (o site com bug), `roteiro-de-teste.md` (o roteiro para percorrer) e `gabarito-bugs.md` (a resposta — **só abra depois**).

**Mais exercícios de código com bug:** `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-01-calculadora.py` ·
`exercicio-02-banco.py` · `exercicio-03-carrinho.py` · `exercicio-04-formulario.html` ·
`exercicio-05-datas.py` · `exercicio-06-cpf.py` (gabaritos em `encontre-o-bug/gabarito/`).

**Modelos prontos para copiar:** `qa-exercicios-praticos/modelos-templates/bug-report.md` ·
`test-case.md` · `test-plan.md` · `checklist-smoke-e-aceite.md` · `relatorio-teste.md`.

`art-of-software-testing/` — implementação prática do livro *The Art of Software Testing*:

| Pasta | Sobre |
|---|---|
| `Caso Classificador de Triangulo/Teste de Unidade/triangulo2.test.js` | Teste unitário com **Jest** (caixa branca) |
| `Caso Classificador de Triangulo/Teste de Interface/triangulo.test.js` | Teste de interface com **Selenium** |
| `Caso Classificador de Triangulo/Testes Manuais/Teste_manuais.txt` | Documentação de teste manual executado |

> **O mesmo caso, três níveis de teste.** É a melhor prova de que os níveis de teste
> não são teoria: o classificador de triângulo tem teste manual, teste unitário e teste
> de interface — porque o software **tem** três lugares onde pode quebrar.

**Laboratório Tech Social (exercícios jogáveis no navegador):**
`laboratorio-tech-social/site/exercicios/caca-bugs.html` (quiz de caça aos bugs) ·
`laboratorio-tech-social/site/exercicios/plano-testes.html` (montador de plano de teste com casos de referência).

**Trilha web e slides:**
`laboratorio-tech-social/site/trilhas/adolescentes/03-qa.html` ·
`laboratorio-tech-social/materiais/slides/aula-teens-03-qa.html`

**QA_RUN — 71 jogos educativos de QA** (`QA_RUN/js/games/`):

| Jogo | Arquivo | Conceito |
|---|---|---|
| Quiz Duel | `QA_RUN/js/games/quizduel.js` | Conceitos de QA contra o relógio |
| Bug Hunt | `QA_RUN/js/games/bughunt.js` | Caça aos bugs em 5 telas de app |
| Paciência QA | `QA_RUN/js/games/patiencia.js` | Pilhas de testes unitário / integração / E2E |
| Sort Steps | `QA_RUN/js/games/sortsteps.js` | Ordenar as etapas do ciclo de vida do bug |
| Penalty QA | `QA_RUN/js/games/penalty.js` | Escolher a estratégia de teste certa |

**Links:**
[QA_RUN (jogos de QA)](https://marquezbertin.github.io/QA_RUN/) ·
[Laboratório Tech Social](https://marquezbertin.github.io/laboratorio-tech-social/) ·
[Google Colab (para rodar os testes em Python)](https://colab.research.google.com/)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Defeito** | "O **código** está errado." |
| **Falha** | "O **comportamento** está errado — o defeito apareceu para o usuário." |
| **Bug** | "O nome informal que a gente usa para defeito + falha." |
| **QA** | "**Processo**. 'Estamos fazendo da maneira certa?'" |
| **QC** | "**Produto**. 'O produto está certo?'" |
| **Teste unitário** | "Testa **uma função sozinha**, sem banco, sem internet. Rápido." |
| **Teste de integração** | "Testa **duas partes conversando**. Onde nasce o bug de verdade." |
| **Teste de sistema** | "Testa o **produto inteiro**, do ponto de vista do usuário." |
| **Teste de aceite (UAT)** | "O **cliente** diz se pode usar. É o veredito final." |
| **Pré-condição** | "O que precisa ser **verdade antes** de eu começar." |
| **Resultado esperado** | "O que **deveria** acontecer, escrito antes de rodar." |
| **Severidade** | "**Quanto** estraga. Impacto no negócio." |
| **Prioridade** | "**Quando** corrigir. Urgência na fila." |
| **Matriz de rastreabilidade** | "A tabela que liga **requisito → teste → bug**. Sem ela, ninguém sabe o que falta." |
| **TDD** | "Teste primeiro (vermelho), código depois (verde), refatorar no fim." |
| **Custo do defeito** | "Bug achado no requisito é **barato**. Bug achado em produção é **caro**." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Todo aplicativo que você usa já teve bug. O WhatsApp, o TikTok, o app do banco.
A diferença entre eles e um app malfeito **não é que não têm bug** — é que alguém **testou**
antes de você passar raiva. Hoje você vai ser esse alguém."*

Não diga "QA é ficar caçando erro". Diga: **"QA é fazer o defeito aparecer cedo e barato."**

**Demonstração ao vivo (5 min):**
1. Abra `laboratorio-tech-social/site/exercicios/caca-bugs.html` e jogue uma rodada.
2. Abra `laboratorio-tech-social/site/exercicios/plano-testes.html` e monte um plano de 3 casos.
3. Peça para a turma dizer: *"Qual é a diferença entre um jogo de caça-bugs e o trabalho real de QA?"*
   Resposta esperada: no jogo o bug está garantido; no trabalho real, **testar é procurar onde
   ainda não olhou**.

### Fase 2 — Exploração (20 min)

**Parte 1 — As três palavras: defeito, falha, bug (4 min).**
Desenhe no quadro:
```
requisito: "o desconto vai de 0 a 50%"
     │
     ▼
DEFEITO ──(o código executa)──▶ FALHA ──(o usuário percebe)──▶ BUG (nome que o mundo usa)
```
- **Defeito**: algo no produto está errado (no código, no documento, no processo).
- **Falha**: o defeito se manifestou — o sistema não fez o que devia.
- **Bug**: o termo informal para defeito + falha. No dia a dia, todo mundo usa "bug".

**Parte 2 — QA, QC e Teste (2 min).**
| Termo | Foco | Pergunta |
|---|---|---|
| **QA (Quality Assurance)** | Processo | "Estamos fazendo da maneira certa?" |
| **QC (Quality Control)** | Produto | "O produto está certo?" |
| **Teste** | Atividade técnica | "Onde estão os defeitos?" |

Diga: *"Teste mostra a **presença** de defeitos, nunca a ausência deles. Ninguém prova que um
software não tem bug — o que se prova é que os testes que importam passam."*

**Parte 3 — Níveis de teste e a pirâmide (5 min).**
Desenhe a pirâmide no quadro:
```
              /─────────\
             /  E2E / UI \        poucos · lentos · frágeis
            /─────────────\
           /  Integração / API \     médios · estáveis
          /─────────────────────\
         /        Unidade          \  muitos · rápidos · estáveis
        /___________________________\
```
| Nível | Testa o quê | Exemplo do projeto da turma |
|---|---|---|
| **Unitário** | uma função isolada | `calcular_desconto(100, 10) == 90` |
| **Integração** | duas partes juntas | a API do GitHub + o `fetch` do site |
| **Sistema** | o produto inteiro | cadastrar no site e ver no banco |
| **Aceite (UAT)** | se o cliente aprova | o professor e a turma testando o site final |

**Parte 4 — Caso de teste e passos de reprodução (5 min).**
Mostre o template real (`manual-qa-completo/docs/10/PT/test_case_template.md`):
```
ID: TC-LOGIN-001
Pré-condições:
  - usuário cadastrado
Dados de entrada:
  - e-mail: user@teste.com
  - senha: Senha123
Passos:
  1. Acessar /login
  2. Informar e-mail válido
  3. Informar senha válida
  4. Clicar em "Entrar"
Resultado esperado: redireciona para /dashboard com o nome do usuário
Resultado obtido: (preenchido na execução)
Status: Pass | Fail | Blocked | Not Run
```
**Régua dos passos de reprodução:** numerados, exatos, curtos e partindo de um estado
conhecido. Teste de passagem: *"Se eu entregar esse bug report para uma pessoa que nunca
viu o sistema, ela consegue reproduzir? Se não, o report está ruim."*

**Exemplo real de bug report** (com os campos de
`manual-qa-completo/docs/10/PT/bug_report_template.md` e de
`qa-exercicios-praticos/modelos-templates/bug-report.md`):

| Campo | Valor |
|---|---|
| **ID** | BUG-014 |
| **Título** | Botão **Finalizar Compra** some após erro de cartão |
| **Produto / Módulo** | Checkout — módulo de pagamento |
| **Ambiente** | Chrome 120 / Windows 11 / Build 2.3.1 |
| **Pré-condições** | 1 item no carrinho; usuário logado |
| **Passos para reproduzir** | 1. Adicionar item ao carrinho · 2. Ir para o checkout · 3. Inserir cartão inválido (1234 5678 9012 3456) · 4. Submeter o formulário |
| **Resultado esperado** | Mensagem de erro na tela **e o botão permanece visível** |
| **Resultado obtido** | Tela de erro e o botão **desaparece** — impossível tentar de novo |
| **Severidade** | **Alto** (bloqueia a venda) |
| **Prioridade** | **Alta** |
| **Reprodutibilidade** | Sempre (10 de 10 tentativas) |
| **Evidência** | `screenshot_erro.png` |
| **Status** | Corrigido em `fix/checkout-validar-cartao` · reteste pendente |

**Matriz de rastreabilidade** — a tabela que liga o que foi pedido ao que foi testado
(formato de `manual-qa-completo/docs/10/PT/matriz_rastreabilidade.md`):

| Req ID | Requisito | Caso de Teste | Status | Bugs |
|---|---|---|---|---|
| REQ-01 | Login válido | TC-LOGIN-001 | Pass | — |
| REQ-02 | Senha inválida | TC-LOGIN-002 | Pass | — |
| REQ-03 | Logout | TC-LOGIN-003 | Fail | BUG-120 |
| REQ-04 | Recuperar senha | TC-PWD-001 | Pass | — |

Cobertura = (requisitos com teste ÷ total de requisitos) × 100.

**Parte 5 — Severidade × Prioridade, ciclo de vida do bug e TDD (4 min).**
Severidade = **quanto** estraga. Prioridade = **quando** corrigir. Não são a mesma coisa:
um texto torto numa tela de pagamento é severidade **Baixa** e prioridade **Alta** (é a
imagem da empresa na frente do cliente). A matriz oficial do repositório está em
`manual-qa-completo/docs/04/PT/indice.md` §4.5.1, e o script que calcula o SLA por
severidade+prioridade é `manual-qa-completo/docs/04/scripts/triage.py`.

Ciclo de vida do bug (brinde o cartaz na parede da sala):

| Estado | O que significa | Quem move |
|---|---|---|
| **Novo** | Bug relatado, ainda sem classificação | QA |
| **Triagem** | Classificado por severidade e prioridade | QA + desenvolvimento |
| **Atribuído** | Tem responsável e prazo | Coordenação |
| **Em correção** | Alguém está codando a correção | Desenvolvimento |
| **Corrigido** | Correção enviada e aguardando verificação | Desenvolvimento |
| **Verificado (reteste)** | QA reexecutou o caso de teste | QA |
| **Fechado** | Confirmado e publicado | QA |
| **Reaberto** | Voltou a falhar — o bug nunca foi corrigido | QA |

```
Novo → Triagem → Atribuído → Em correção → Corrigido → Verificado → Fechado
                                                                   └─► Reaberto
```

**TDD em 3 frases:**
1. Escreva **primeiro** o teste que descreve o comportamento esperado — ele vai **falhar** (vermelho).
2. Escreva o **código mínimo** para fazer o teste passar (verde).
3. **Refatore** o código com o teste protegendo você.

Diga: *"TDD não é sobre escrever mais código. É sobre **descobrir o erro antes do usuário**."*

**QA é cultura, não caça-de-erros.** Feche a exploração com estas três frases:
1. **A qualidade não é de uma pessoa, é da equipe.** QA não é o "guardião que pega o erro
   dos outros" — é quem ajuda o time a escrever requisito testável, revisar e retestar.
2. **Bug report é conversa, não armadilha.** O objetivo do report não é mostrar quem
   errou: é dizer *o que aconteceu, como reproduzir e qual é o impacto* para que o
   conserto saia rápido.
3. **Prevenir é mais barato que detectar.** O custo de corrigir um defeito cresce
   conforme a fase (requisito → projeto → produção). QA que só chega no fim vira QA
   que só homologa. Está em `manual-qa-completo/docs/01/PT/indice.md` §1.4 (7 princípios
   ISTQB) e §1.5 (custo da qualidade).

### Fase 3 — Mão na massa (35 min)

**Atividade A — Caça-bugs com roteiro (15 min).**
Abra `qa-exercicios-praticos/sites-para-testar/momento-matador/index.html`.
Cada dupla:
1. Lê `roteiro-de-teste.md` e percorre o site **sem** abrir o gabarito.
2. Anota cada bug em uma tabela: **ID | título | passos | esperado | obtido | severidade | prioridade**.
3. Só depois abre `gabarito-bugs.md` e confere: **quantos de vocês acharam?**
4. Repete com `techstore/index.html` (nível ★★☆), se der tempo.

> ⚠️ Os bugs são **de propósito**. O objetivo não é "ganhar pontos": é aprender a
> **descrever** o problema com clareza suficiente para outra pessoa corrigir.

**Atividade B — Casos de teste e bug report (10 min).**
Usando os modelos reais do repositório:
- `qa-exercicios-praticos/modelos-templates/test-case.md` → escrever **2 casos de teste**
  (um "caminho feliz" e um de **borda/negativo**) do site da turma.
- `qa-exercicios-praticos/modelos-templates/bug-report.md` → escrever **1 bug report**
  completo do bug encontrado na Atividade A.
- `manual-qa-completo/docs/10/PT/matriz_rastreabilidade.md` → montar a **matriz de
  rastreabilidade** (requisito → caso → status → bug).

**Atividade C — Corrigir 1 bug provando com teste automatizado (10 min).**
Rode no [Google Colab](https://colab.research.google.com/) (ou Python local).
O código abaixo é a versão **com bug** (adaptada de
`qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-01-calculadora.py`) com os
**testes já escritos** por um colega — é o papel do QA:

```python
import unittest


def calcular_desconto(preco, percentual_desconto):
    """Calcula o preço final aplicando um desconto em porcentagem.

    Regras do negócio: desconto entre 0 e 50% e preço maior que zero.
    """
    # BUG 1: o limite de desconto está errado (aceita até 100%)
    if percentual_desconto < 0 or percentual_desconto > 100:
        raise ValueError("Desconto inválido")
    # BUG 2: preço zero deveria ser rejeitado, mas passa como se fosse válido
    if preco < 0:
        raise ValueError("Preço inválido")
    return preco - (preco * percentual_desconto / 100)


class TesteCalcularDesconto(unittest.TestCase):
    """Testes unitários do cálculo de desconto."""

    def test_desconto_normal(self):
        self.assertAlmostEqual(calcular_desconto(100, 10), 90)

    def test_desconto_maximo(self):
        self.assertAlmostEqual(calcular_desconto(50, 50), 25)

    def test_desconto_acima_do_limite(self):
        with self.assertRaises(ValueError):
            calcular_desconto(100, 60)

    def test_preco_zero_deve_falhar(self):
        with self.assertRaises(ValueError):
            calcular_desconto(0, 10)


# argv=[""] e exit=False para o Colab não encerrar a célula
unittest.main(argv=[""], exit=False)
```

**O roteiro do aluno:**
1. **Roda o teste como está.** Dois testes falham (vermelho). Anota qual falhou e por quê —
   isso é o **relatório do bug**, em linguagem de programador.
2. **Corrige o código** (mude `> 100` para `> 50` e `preco < 0` para `preco <= 0`).
3. **Roda de novo.** Todos os testes passam (verde).
4. Preenche no bug report: `status: Corrigido · evidência: saída do unittest antes e depois ·
   commit: <hash> · reteste: OK`.

Diga: *"O teste que falha antes de corrigir é o que separa um programador de quem só
espera dar certo. Se o teste passa antes da correção, ele não está provando nada."*

### Fase 4 — Projeto (20 min)

**Desafio: "Plano de teste + 1 bug corrigido" do projeto da turma**

Usando o template real `manual-qa-completo/docs/10/PT/test_plan_template.md`, entregue:

1. **Plano de teste** do projeto final (aula 13) — seções: introdução, itens de teste,
   fora de escopo, abordagem, ambiente e dados, riscos, **critérios de entrada e saída**.
2. **Matriz de rastreabilidade** com pelo menos **3 requisitos**, 3 casos e o status
   (Pass/Fail) de cada um.
3. **1 bug report** completo do projeto da turma (pode ser do site da aula 05 ou do
   script da aula 03) **e a correção**, com o teste automatizado que prova que o
   bug foi resolvido.
4. **Commit** da correção no repositório da turma, com mensagem no padrão
   `fix: <o que foi corrigido>` (aula 07).

**Critério de pronto:**
- [ ] Plano de teste com **escopo claro** e **critérios de saída** escritos
- [ ] **3 casos de teste** com pré-condição, passos numerados e resultado esperado
- [ ] Matriz de rastreabilidade **requisito → caso → status → bug**
- [ ] **1 bug report** com os 10 campos preenchidos (incluindo severidade e prioridade)
- [ ] **1 bug corrigido** com teste automatizado **verde** (`unittest`)
- [ ] Commit da correção no Git, mensagem `fix: ...`

### Fase 5 — Mostra (5 min)

Duas duplas apresentam o bug report (sem mostrar o gabarito primeiro) e o teste que prova
a correção. A turma responde: *"O teste realmente falha antes da correção?"* — se ninguém
saber dizer, o teste não prova nada.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Caça-bugs com roteiro | Achou bugs **e** documentou com passos reproduzíveis |
| Casos de teste | Pré-condição, passos numerados e resultado esperado presentes |
| Bug report | 10 campos preenchidos, severidade e prioridade justificadas |
| Matriz de rastreabilidade | Requisito ligado a caso, status e bug |
| Bug corrigido | `unittest` **verde** depois da correção (e **vermelho** antes) |
| Plano de teste | Escopo, itens de teste, riscos e critérios de saída |
| Participação | Racionalizou, perguntou, Colaborou com a dupla |
| Pergunta de saída | "Severidade e prioridade são a mesma coisa?" |

**Pergunta de escrita:**
> "Um botão de finalizar compra some da tela quando o cartão digitado é inválido.
> O cliente não consegue tentar de novo. Classifique o bug quanto à severidade e à
> prioridade e justifique."
> **Resposta:** **Severidade Alta** (bloqueia a venda — o usuário não consegue concluir a
> compra) e **Prioridade Alta/Urgente** (é o caminho de receita e a tela de erro sem
> saída gera abandono e reclamação). Um bug de **severidade Baixa** (texto torto) pode
> ter **Prioridade Alta** se estiver na tela de pagamento, porque afeta a imagem da
> empresa — severidade mede impacto, prioridade mede urgência.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-01-calculadora.py` | 3+ bugs numa calculadora de desconto |
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-02-banco.py` | Bugs de regra de negócio bancária |
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-03-carrinho.py` | Bugs de cálculo de carrinho |
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-04-formulario.html` | Bugs de validação em HTML/JS |
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-05-datas.py` | Bugs de cálculo de datas |
| `qa-exercicios-praticos/encontre-o-bug/codigo/exercicio-06-cpf.py` | Bugs de validação de CPF |
| `qa-exercicios-praticos/casos-de-teste/exercicios-escrever-casos.md` | Exercícios de escrita de casos de teste |
| `qa-exercicios-praticos/tecnicas-de-teste/exercicios-tecnicas-de-teste.md` | Equivalência, valor-limite, tabela de decisão, estados, pairwise |
| `qa-exercicios-praticos/api-testing/exercicios-de-api.md` | Testes de API (Postman, `requests`, carga) |
| `qa-exercicios-praticos/sql-para-qa/exercicios-sql.md` | SQL para QA com schema pronto |
| `qa-exercicios-praticos/perguntas-respostas/perguntas-entrevista-QA.md` | Banco de perguntas de entrevista de QA |
| `qa-exercicios-praticos/simulados/simulado-01-fundamentos.md` | Simulado de múltipla escolha com gabarito |
| `qa-exercicios-praticos/simulacoes/cenarios-role-play.md` | Cenários de role-play (entrevista e trabalho) |
| `manual-qa-completo/docs/10/PT/checklist_aceite.md` | Checklist de homologação |
| `manual-qa-completo/docs/10/PT/charter_template.md` | Charter de sessão exploratória (SBTM) |
| `manual-qa-completo/docs/10/PT/glossario.md` | Glossário PT/EN de QA |
| `manual-qa-completo/docs/10/PT/solucoes.md` | Gabarito dos exercícios do manual |
| `manual-qa-completo/docs/04/scripts/triage.py` | Calcula o SLA (em horas) por severidade + prioridade |
| `manual-qa-completo/tests/test_manual_qa.py` | Testes do próprio manual (rodam com `pytest`) |
| `art-of-software-testing/Caso Classificador de Triangulo/Testes Manuais/Teste_manuais.txt` | Documentação de teste manual do classificador de triângulos |
| `art-of-software-testing/Caso Classificador de Triangulo/Teste de Unidade/triangulo2.test.js` | O mesmo caso em teste unitário (Jest) |
| `laboratorio-tech-social/site/exercicios/caca-bugs.html` | Quiz de caça aos bugs (navegador) |
| `laboratorio-tech-social/site/exercicios/plano-testes.html` | Montador de plano de testes (navegador) |
| `QA_RUN/js/games/bughunt.js` | Jogo de caça aos bugs |
| `QA_RUN/js/games/sortsteps.js` | Jogo de ordenação do ciclo de vida do bug |
| `QA_RUN/js/games/patiencia.js` | Jogo de pilhas de testes (unitário / integração / E2E) |

---

## 🏠 Para casa

1. Abrir `qa-exercicios-praticos/sites-para-testar/techstore/index.html` e rodar o roteiro
   inteiro, entregando **5 bug reports** no formato `BUG-<ID>-<descricao-curta>.md`.
2. Escolher **1 dos bugs** e escrever o **caso de teste** que pega esse bug
   (`qa-exercicios-praticos/modelos-templates/test-case.md`).
3. Escrever **1 caso de teste automatizado** em `unittest` que reproduza o bug —
   ele **tem que falhar** no código atual. Subir no repositório da turma com
   `test: reproduzir BUG-<ID>`.
4. Ler `manual-qa-completo/docs/01/PT/indice.md` §1.4 (7 princípios ISTQB) e §1.5
   (custo da qualidade) e responder no README: *"qual princípio você vai aplicar no
   projeto final?"*

---

## 🔗 Próximo módulo

[B9 — IA para Iniciantes](09-ia.md)

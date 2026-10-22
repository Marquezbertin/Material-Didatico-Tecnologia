# EX-Q6 — Banco de Exercícios: QA e Testes de Software (13–17 anos)

**Trilha:** Adolescentes [B8 — QA: Teste de Software](../02-ADOLESCENTES-13-17/08-qa-teste-de-software.md) ·
Adultos [07 — Projeto Final](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md) (plano de testes e métricas)

| Item | Descrição |
|---|---|
| **Faixa etária** | 13 a 17 anos (aproveitado como revisão para 18+) |
| **Nº de itens** | 15 — conceitos (4), plano de teste (2), caso de teste (3), severidade e prioridade (2), relato de bug (2), revisão de código (2) |
| **Nível** | ⭐ Fácil (2 itens) · ⭐⭐ Médio (9 itens) · ⭐⭐⭐ Difícil (4 itens) |
| **Tempo estimado** | 90 a 120 min (os itens práticos levam 5 a 10 min cada) |
| **Formato** | Enunciado (teórico ou prático) e **gabarito com o modelo preenchido** |

> ⚠️ **Licença de uso:** material livre, sob a licença **CC BY 4.0** (Creative Commons
> Atribuição 4.0 Internacional). Você pode copiar, adaptar e redistribuir, desde que cite a
> autoria (Bruno Bertin Marquez) e indique as mudanças. Licença:
> https://creativecommons.org/licenses/by/4.0/

---

## 🎯 Objetivo

Ao final da atividade, o aluno será capaz de:

1. Diferenciar **QA** (prevenir defeitos) de **QC** (encontrar defeitos).
2. Escrever um **plano de teste** com objetivo, escopo, riscos, estratégia e critérios de saída.
3. Escrever um **caso de teste** completo, com pré-condições, dados, passos e resultado esperado.
4. Classificar um defeito em **severidade** e **prioridade** — e saber que são coisas diferentes.
5. Escrever um **bug report** que o desenvolvedor consegue reproduzir sem perguntar nada.
6. Fazer uma **revisão de código** apontando problemas de legibilidade, robustez e estilo.

**Objetivo secundário:** entender que **testar é sistematicamente documentar**, e que um bom
relato economiza horas de alguém.

---

## 📚 Fontes no repositório

| Repositório | Pasta/arquivo usado | O que foi aproveitado |
|---|---|---|
| `manual-qa-completo` | `docs/01/PT/indice.md` e `docs/02/PT/indice.md` | QA × QC, princípios, ISO 25010, níveis de teste, STLC |
| `manual-qa-completo` | `docs/03/PT/indice.md` | Planejamento: política, estratégia, plano, estimativas |
| `manual-qa-completo` | `docs/04/PT/indice.md` | Manuais, exploratórios, caso de teste, bug report |
| `manual-qa-completo` | `docs/08/PT/indice.md` | Qualidade de código, cobertura, quality gates |
| `manual-qa-completo` | `docs/10/PT/test_plan_template.md` | Modelo de plano de teste usado no item 6 |
| `manual-qa-completo` | `docs/10/PT/test_case_template.md` | Modelo de caso de teste usado no item 7 |
| `manual-qa-completo` | `docs/10/PT/bug_report_template.md` | Modelo de bug report usado no item 12 |
| `manual-qa-completo` | `docs/11/PT/indice.md` | Segurança: OWASP Top 10, varredura de segredos |
| `qa-exercicios-praticos` | `modelos-templates/test-plan.md`, `test-case.md`, `bug-report.md` | Modelos completos em português |
| `qa-exercicios-praticos` | `tecnicas-de-teste/exercicios-tecnicas-de-teste.md` | Equivalência, valor-limite, tabela de decisão, estados, pairwise |
| `qa-exercicios-praticos` | `encontre-o-bug/codigo/` e `encontre-o-bug/gabarito/` | 6 exercícios de caça a bug com gabarito |
| `qa-exercicios-praticos` | `sites-para-testar/` | 9 sistemas com defeitos intencionais para treinar |
| `QualityHub` | `Casos de testes/` | Casos reais: Login, Cadastro de usuário, Recuperação de senha |
| `QualityHub` | `Cases QA/` | Falhas reais (reservas British Airways, NHS, Knight Capital) |
| `questionario_despertardaqualidade` | (10 perguntas V/F) | Quiz rápido de fixação |

**Sistemas para treinar:** `qa-exercicios-praticos/sites-para-testar/` — TechStore, Banco ABC,
Reserva Fácil, Portal Cliente, FoodGo, CRM Connect, Contabilidade KM, Vida+ Saúde e Momento
Matador. Todos com bugs propositais.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **QA** | "**Prevenir** defeitos. Vem antes do código." |
| **QC** | "**Encontrar** defeitos. Vem junto com o código." |
| **STLC** | "As **etapas** do trabalho de testar, na ordem." |
| **Smoke test** | "O teste de **fumaça**: a página abriu? Então pode testar." |
| **Regressão** | "O que já funcionava **ainda** funciona?" |
| **Caso de teste** | "Um **passo a passo** com o resultado esperado escrito." |
| **Pré-condição** | "O que precisa ser **verdadeiro antes** de começar." |
| **Severidade** | "Quão **grave** é o estrago?" |
| **Prioridade** | "Quão **urgente** é consertar?" |
| **Reprodutibilidade** | "Dá para fazer **de novo** e dá o mesmo resultado?" |
| **Bug report** | "Relato que **não exige pergunta nenhuma**." |
| **Revisão de código** | "Ler o código do outro **antes** de aprovar." |

---

## 📝 Bloco A — Conceitos de QA (1 a 4)

### Exercício 1 — QA × QC ⭐ · ⏱️ 2 min

Escolha a alternativa correta e **justifique em uma frase**:

A) QA e QC são exatamente a mesma coisa.
B) QA é o conjunto de atividades de **prevenção** (planejamento, padrões, treinamento), feita
**antes** de o defeito existir; QC é a atividade de **detecção** (testes, revisões), feita
**sobre** o produto pronto.
C) QC é feito antes do código e QA é feito depois.
D) QA serve para documento e QC serve para consertar bug.

### Exercício 2 — Smoke test ⭐ · ⏱️ 2 min

O que é um **smoke test** e por que ele existe? Escolha a melhor definição:

A) Uma bateria de testes que leva dias para ser executada antes de cada versão.
B) Um conjunto rápido de verificações que confirma se a versão **instala, sobe e tem as
funções principais de pé** — o "portão" antes dos testes completos.
C) O teste de aceitação feito com o cliente.
D) O teste que mede o tempo de resposta do servidor.

### Exercício 3 — Fases do STLC ⭐⭐ · ⏱️ 3 min

Coloque em ordem as fases do ciclo de teste: **Execução**, **Preparação do ambiente**,
**Análise de requisitos**, **Planejamento**, **Relatório de resultados**, **Avaliação de
saída**.

### Exercício 4 — Valor-limite ⭐⭐ · ⏱️ 3 min

Um sistema aceita idade entre **18 e 65 anos**. Usando **análise de valor-limite**, quais
valores você deve testar?

A) 18, 19, 64, 65
B) 17, 18, 65, 66
C) 0, 18, 65, 999
D) 17, 18, 19, 64, 65, 66

---

## 📝 Bloco B — Plano de teste (5 e 6)

**Contexto para os itens 5 e 6:** o produto é o **app de matrícula escolar** usado no
[EX-S5](05-exercicios-sql.md): o aluno entra, escolhe a turma, confirma a matrícula e recebe
o comprovante por e-mail.

### Exercício 5 — Objetivo e escopo ⭐⭐ · ⏱️ 5 min

Escreva, em **um parágrafo cada**:

1. o **objetivo** do plano de teste (o que será validado e com qual critério de aceite);
2. o **escopo**, separando o que está **incluído** e o que está **fora de escopo**.

### Exercício 6 — Plano de teste completo ⭐⭐⭐ · ⏱️ 10 min

Preencha as **nove seções** do plano de teste do app de matrícula escolar:

1. Objetivo · 2. Escopo · 3. Riscos e mitigações · 4. Estratégia · 5. Ambiente ·
6. Calendário · 7. Casos de teste (referência) · 8. Critérios de saída · 9. Decisões

Para a seção 3, registre **pelo menos dois riscos** reais (ambiente instável, massa de dados
suja, dependência de e-mail externo). Para a seção 4, escolha os **tipos de teste** e as
**técnicas** que você usaria.

---

## 📝 Bloco C — Caso de teste (7 a 9)

### Exercício 7 — Caso de teste de regra de negócio ⭐⭐ · ⏱️ 5 min

A turma 9B tem **vaga máxima de 30 alunos** e hoje tem 30 matriculados. Escreva um **caso de
teste** completo para a situação: "aluno tenta se matricular em uma turma lotada".

Preencha: ID, título, requisito relacionado, tipo, prioridade, pré-condições, dados de
entrada, passos, resultado esperado, status.

### Exercício 8 — Caso de teste negativo ⭐⭐ · ⏱️ 5 min

No formulário de cadastro, o campo **e-mail** deve aceitar apenas um endereço válido
(`tipo="email"`). Escreva um **caso de teste negativo**: um e-mail **inválido** que o sistema
precisa **rejeitar**.

### Exercício 9 — Tabela de decisão ⭐⭐⭐ · ⏱️ 6 min

O app de matrícula classifica a média do aluno assim:

| Média | Situação |
|---|---|
| ≥ 7,0 | Aprovado com mérito |
| entre 5,0 e 6,99 | Recuperação |
| < 5,0 | Reprovado |

1. Escreva a **tabela de decisão** completa (regra, condição, resultado esperado).
2. Escreva **dois casos de teste** tirados dela (um de classe válida e um de limite).

---

## 📝 Bloco D — Severidade e prioridade (10 e 11)

### Exercício 10 — Conceito ⭐⭐ · ⏱️ 3 min

Responda com suas palavras:

1. Qual a diferença entre **severidade** e **prioridade**?
2. É possível ter um bug de severidade **alta** e prioridade **baixa**? Dê um exemplo.

### Exercício 11 — Classificação de bugs ⭐⭐ · ⏱️ 6 min

Classifique cada bug abaixo quanto a **severidade**, **prioridade** e **tipo** (funcional,
lógica, segurança, UX, performance, visual). Justifique em **uma frase** cada.

- **A)** Ao clicar duas vezes no botão "Finalizar matrícula", o sistema cria **duas**
  matrículas duplicadas.
- **B)** O cadastro aceita um aluno com o campo **e-mail vazio**, e depois o envio do
  comunicado falha.
- **C)** Após **três** tentativas de senha erradas, o usuário fica **bloqueado para sempre**,
  sem forma de recuperar a conta.
- **D)** O botão "Salvar" aparece em **cinza claro** no celular e o texto fica quase ilegível.
- **E)** Ao registrar a nota da prova final, o sistema **fecha sozinho** e as notas dos 30
  alunos da turma **não foram gravadas**.

---

## 📝 Bloco E — Relato de bug (12 e 13)

### Exercício 12 — Bug report completo ⭐⭐ · ⏱️ 6 min

Escreva um **bug report** completo a partir desta descrição:

> "No app de matrícula, quando o aluno clica em 'Finalizar matrícula', aparece a mensagem de
> sucesso, mas a matrícula **não aparece** na lista 'Minhas matrículas'. Isso acontece
> **sempre**, no Chrome 131, no Windows 11, com a aluna Ana Souza (id 1) na turma 9A."

### Exercício 13 — O que faz um bom relato ⭐⭐ · ⏱️ 3 min

Marque as alternativas que tornam um bug report **útil** para quem vai corrigir:

A) Passos numerados para reproduzir.
B) Resultado esperado e resultado obtido, lado a lado.
C) Ambiente (navegador, sistema, versão, resolução).
D) "O sistema está com defeito, recomendo corrigir."
E) Evidências (print, vídeo ou trecho de log).
F) A causa do erro e a linha do código que deve ser alterada.

---

## 📝 Bloco F — Revisão de código (14 e 15)

### Exercício 14 — Revisar um trecho de código ⭐⭐⭐ · ⏱️ 6 min

Revise o código abaixo e liste **pelo menos 5 problemas**, separando-os em
**legibilidade**, **robustez** e **estilo**. Para cada problema, diga **como** corrigir.

```python
def media(notas):
    s = 0
    for n in notas:
        s = s + n
    return s / len(notas)


def resultado(notas):
    m = media(notas)
    if m >= 6:
        return "Aprovado"
    else:
        return "Reprovado"
```

### Exercício 15 — Checklist de revisão ⭐⭐⭐ · ⏱️ 8 min

Escreva uma **checklist de revisão de código** para uso em *pull request*, com **8 itens
verificáveis**. Cada item deve ser uma pergunta que o revisor responde com **sim ou não**,
não com "verifique o código".

---

## ✅ Gabarito comentado

### 1 — QA × QC

**Alternativa B.**

QA (Quality Assurance) é **preventivo**: vem antes, define padrões, processos, planos e
treina a equipe, para que o defeito **nem precise acontecer**. QC (Quality Control) é
**detetivo**: vem sobre o produto pronto e procura o defeito por meio de testes, revisões e
inspeção. Resumo para fixar: **QA impede, QC encontra**.

### 2 — Smoke test

**Alternativa B.**

O smoke test é a **verificação rápida que roda primeiro**: se a versão nem sobe, não adianta
gastar horas com a suíte completa. Ele funciona como um **filtro** (gate) entre o
desenvolvimento e a validação. Se o smoke falha, a build é **recusada** de imediato.

### 3 — Fases do STLC

**Ordem correta:**

1. **Análise de requisitos** — entender o que precisa ser testado e por quê.
2. **Planejamento** — definir estratégia, escopo, recursos, riscos e cronograma.
3. **Preparação do ambiente** — deixar servidor, banco e massa de dados prontos.
4. **Execução** — rodar os casos e registrar os resultados.
5. **Avaliação de saída** — conferir os critérios de saída e decidir se encerra.
6. **Relatório de resultados** — publicar o que passou, o que falhou e os bugs abertos.

> A ordem importa: pular o planejamento é o que faz a equipe testar **no susto**, e testar sem
> ambiente preparado é o que faz o resultado depender do dia.

### 4 — Valor-limite

**Alternativa B — 17, 18, 65, 66.**

A regra da análise de valor-limite é testar o **limite**, o valor **imediatamente abaixo** e
o valor **imediatemente acima**. Para o intervalo [18, 65], testam-se 17 (rejeitado), 18
(aceito) e 65 (aceito), 66 (rejeitado). A alternativa D não está errada por testar valores
a mais — apenas é **redundante**; B é o conjunto mínimo que cobre os dois limites.

### 5 — Objetivo e escopo

**Objetivo (modelo):**

> Validar o fluxo de matrícula escolar do início ao fim (login, escolha de turma, confirmação
> e comprovante por e-mail), incluindo as regras de vaga máxima (30 alunos por turma) e de
> matrícula duplicada. Critério de saída: 100% dos casos críticos executados e aprovados,
> nenhum bug de severidade Blocker ou Alta em aberto no escopo, e relatório de resultados
> entregue ao Product Owner.

**Escopo:**

- **Inclui:** autenticação do aluno; consulta das turmas disponíveis; matrícula em turma com
  vaga; bloqueio de matrícula em turma lotada; bloqueio de matrícula duplicada na mesma
  turma; envio do comprovante por e-mail; consulta de "Minhas matrículas".
- **Fora de escopo:** app do professor e lançamento de notas; matrícula de alunos
  transferidos de outra escola (prevista para a versão 2); envio de SMS; integração com o
  sistema de secretaria.

> Escrever o que está **fora** de escopo é o que evita a discussão infinita de
> "isso também tem que estar pronto?".

### 6 — Plano de teste completo

**Modelo preenchido:**

**Projeto:** App de Matrícula Escolar · **Versão testada:** 1.0.0 · **Autor:** [seu nome] ·
**Data:** [dd/mm/aaaa]

**1. Objetivo**
Validar o fluxo de matrícula ponta a ponta e as regras de negócio (vaga máxima, matrícula
única, e-mail obrigatório). Critério de saída: 100% dos casos críticos verdes e nenhum bug
Blocker/Alta aberto no escopo.

**2. Escopo**
- **Inclui:** login do aluno, consulta de turmas, matrícula com vaga, recusa em turma lotada,
  recusa de duplicidade, envio de comprovante, listagem de "Minhas matrículas".
- **Não inclui:** app do professor, lançamento de notas, matrícula de transferidos, SMS.

**3. Riscos e mitigações**

| Risco | Mitigação |
|---|---|
| Ambiente de homologação instável | Janela de deploy definida; ambiente reserva pronto |
| Dependência de servidor de e-mail externo | Usar servidor de e-mail de teste (Mailtrap) na homologação |
| Massa de dados inconsistente | Script de popular o banco com 30 matrículas na 9B antes da execução |

**4. Estratégia**
- Tipos de teste: [x] Smoke [x] Funcional [x] Negativo [x] Borda [x] Regressão
  [ ] Performance [x] Segurança
- Técnicas: [x] Equivalência [x] Valor-limite [x] Tabela de decisão [ ] Exploratório
- Manual vs automatizado: smoke e regressão do login **automatizados**; regras de negócio
  **manuais**, com massa de dados preparada por script.

**5. Ambiente**

| Item | Valor |
|---|---|
| URLs | `https://homologacao.escola.app/matricula` |
| Banco | SQLite `escola.db` (cópia populada do script de massa) |
| Dados de teste | 31 alunos na 9B (para estourar a vaga), 1 aluno já matriculado (duplicidade) |

**6. Calendário**

| Fase | Datas |
|---|---|
| Preparação do ambiente e da massa | 03/03 a 04/03 |
| Execução dos casos | 05/03 a 09/03 |
| Reteste dos bugs corrigidos e regressão | 10/03 a 11/03 |
| Relatório de resultados | 12/03 |

**7. Casos de teste (referência)**
Planilha `casos-de-teste/` · modelos em `qa-exercicios-praticos/modelos-templates/test-case.md`

**8. Critérios de saída**
- Todos os casos críticos e de alta prioridade executados.
- Nenhum bug Blocker ou Alto em aberto **no escopo**.
- Relatório de resultados enviado ao Product Owner.

**9. Decisões**

| Responsável | Aprovação |
|---|---|
| QA | [nome e data] |
| Product Owner | [nome e data] |

### 7 — Caso de teste de regra de negócio

**Modelo preenchido:**

| Campo | Valor |
|---|---|
| **ID do caso** | CT-MAT-007 |
| **Título** | Matricular aluno em turma lotada (9B com 30 de 30 vagas) |
| **Requisito relacionado** | REQ-012 — Vaga máxima por turma |
| **Autor** | [seu nome] |
| **Data** | [dd/mm/aaaa] |
| **Tipo** | [ ] Funcional [ ] Negativo [x] Borda [ ] Regressão [ ] Exploratório |
| **Prioridade** | [x] Alta [ ] Média [ ] Baixa |

**Pré-condições**
- Aluno logado com matrícula ativa e **sem** matrícula na turma 9B.
- Turma 9B com **30 de 30** vagas preenchidas.
- Ambiente de homologação no ar.

**Dados de entrada**

| Campo | Valor |
|---|---|
| Aluno | Elisa Nunes (id 5) |
| Turma | 9B (id 2) |

**Passos**
1. Fazer login com o usuário da aluna Elisa Nunes.
2. Abrir o menu **Matrícula**.
3. Selecionar a turma **9B**.
4. Clicar em **Finalizar matrícula**.
5. Tentar confirmar a matrícula.

**Resultado esperado**
- O sistema **não** cria a matrícula.
- Exibe a mensagem **"Turma 9B está sem vagas."**
- A aluna **não** aparece em "Minhas matrículas".
- A contagem de matrículas da 9B continua em 30.

**Resultado obtido**
[preenchido na execução]

**Status**
[ ] Não executado [ ] Passou [ ] Falhou [ ] Bloqueado

**Pós-condição**
- A turma 9B segue com 30 matrículas.
- Nenhum registro foi criado na tabela `matricula`.

> **Por que este caso é "de borda":** ele testa o **limite exato** (30 de 30). É a linha entre
> "cabe" e "não cabe" — o lugar onde a regra costuma estar errada.

### 8 — Caso de teste negativo

**Modelo preenchido:**

| Campo | Valor |
|---|---|
| **ID do caso** | CT-CAD-003 |
| **Título** | Recusar cadastro com e-mail inválido |
| **Requisito relacionado** | REQ-004 — Campo e-mail obrigatório e válido |
| **Autor** | [seu nome] |
| **Data** | [dd/mm/aaaa] |
| **Tipo** | [ ] Funcional [x] Negativo [ ] Borda [ ] Regressão [ ] Exploratório |
| **Prioridade** | [x] Alta [ ] Média [ ] Baixa |

**Pré-condições**
- Tela de cadastro aberta.
- Aluno ainda não cadastrado com o e-mail usado no teste.

**Dados de entrada**

| Campo | Valor |
|---|---|
| Nome | teste@escola |
| E-mail | `teste@escola` (sem arroba e sem domínio) |
| Senha | `Teste@2026` |

**Passos**
1. Preencher o campo **Nome** com `teste@escola`.
2. Preencher o campo **E-mail** com `teste@escola`.
3. Preencher a **Senha** com `Teste@2026`.
4. Clicar em **Cadastrar**.

**Resultado esperado**
- O formulário **não** é enviado.
- O navegador exibe a mensagem do campo: **"Digite um e-mail válido, como nome@escola.com"**.
- O foco volta para o campo **E-mail**.
- Nenhum aluno é criado no banco.

**Resultado obtido**
[preenchido na execução]

**Status**
[ ] Não executado [ ] Passou [ ] Falhou [ ] Bloqueado

**Pós-condição**
- O aluno de teste não existe na tabela `aluno`.
- Nenhum e-mail foi enviado.

### 9 — Tabela de decisão

**1) Tabela de decisão completa:**

| Regra | Condição | Resultado esperado |
|---|---|---|
| R1 | média ≥ 7,0 | Exibir "Aprovado com mérito" |
| R2 | 5,0 ≤ média < 7,0 | Exibir "Recuperação" |
| R3 | média < 5,0 | Exibir "Reprovado" |

**2) Casos de teste:**

**CT-NOT-001 — classe válida**

| Campo | Valor |
|---|---|
| **ID do caso** | CT-NOT-001 |
| **Título** | Exibir "Aprovado com mérito" para média 8,0 |
| **Tipo** | Funcional |
| **Prioridade** | Alta |
| **Pré-condições** | Aluno logado com notas já lançadas |
| **Dados de entrada** | Notas: 8,0 e 8,0 (média 8,0) |
| **Passos** | 1. Abrir o painel de notas.<br>2. Localizar a média do aluno.<br>3. Ler a situação exibida. |
| **Resultado esperado** | A situação exibida é **"Aprovado com mérito"** |
| **Status** | [ ] Não executado [ ] Passou [ ] Falhou [ ] Bloqueado |

**CT-NOT-002 — limite**

| Campo | Valor |
|---|---|
| **ID do caso** | CT-NOT-002 |
| **Título** | Exibir "Recuperação" exatamente na média 5,0 (limite inferior de R2) |
| **Tipo** | Funcional · **Prioridade** Alta |
| **Pré-condições** | Aluno logado com notas já lançadas |
| **Dados de entrada** | Notas: 5,0 e 5,0 (média exatamente 5,0) |
| **Passos** | 1. Abrir o painel de notas.<br>2. Localizar a média do aluno.<br>3. Ler a situação exibida. |
| **Resultado esperado** | A situação exibida é **"Recuperação"** — e **não** "Reprovado" |
| **Status** | [ ] Não executado [ ] Passou [ ] Falhou [ ] Bloqueado |

> **Por que 5,0 e não 4,9?** O valor 5,0 é o **limite** entre R2 e R3. É o ponto onde o `>=` ou
> o `>` costuma estar escrito errado.

### 10 — Conceito

**1) Diferença:**

- **Severidade** = **impacto** que o defeito causa (quão grave é o estrago: perde dados?
  bloqueia o usuário? é só visual?).
- **Prioridade** = **urgência** do conserto (quando a equipe deve atacar: agora, nesta
  sprint, na próxima?).

**2) Sim, é possível.** Exemplo real: o sistema **apaga o histórico de matrículas** do ano
anterior ao abrir o relatório de frequência — **severidade Alta** (perda de dados), mas **prioridade
Baixa**, porque ninguém consulta aquele relatório há meses e existe um caminho alternativo
(exportar em PDF antes da virada do ano).

> A frase que fixa: **severidade mede o estrago; prioridade mede a urgência.**

### 11 — Classificação de bugs

| Bug | Severidade | Prioridade | Tipo | Justificativa |
|---|---|---|---|---|
| **A** Duplicação de matrícula | Média | Alta | Funcional | O usuário consegue se matricular, mas o relatório fica com dados errados; corrigir é rápido e o dano é grande em uso real. |
| **B** E-mail vazio aceito | Média | Média | Funcional | Afeta apenas o envio de comunicado; há contorno manual e o cadastro do aluno está correto. |
| **C** Bloqueio permanente após 3 erros | Alta | Média | Funcional / UX | Impede o usuário de entrar (severidade alta), mas existe contorno — o professor ou o suporte redefine a senha. |
| **D** Contraste ruim no botão "Salvar" | Baixa | Baixa | Visual / UX | Não impede nenhuma ação; atrapalha apenas quem tem baixa visão. |
| **E** Perda das notas da prova final | Alta | Alta | Funcional / Dados | Perda de dados de 30 alunos, sem recuperação: é o pior caso da lista. |

> Note o bug **C**: severidade **Alta** com prioridade **Média**. É o exemplo que prova que os
> dois conceitos são diferentes. E o bug **E**: severidade **Alta** com prioridade **Alta**,
> o caso clássico de "vai para a frente da fila".

### 12 — Bug report completo

**Modelo preenchido:**

| Campo | Valor |
|---|---|
| **ID** | BUG-2026-014 |
| **Título** | Matrícula confirmada não aparece em "Minhas matrículas" |
| **Produto / Módulo** | App de Matrícula Escolar — Módulo Matrícula |
| **Ambiente** | Chrome 131 · Windows 11 · 1920×1080 · homologação v1.0.0 |
| **Severidade** | [ ] Blocker [x] Alta [ ] Média [ ] Baixa |
| **Prioridade** | [x] Alta [ ] Média [ ] Baixa |
| **Reprodutibilidade** | [x] Sempre [ ] Intermitente [ ] Raro |
| **Tipo** | [x] Funcional [ ] Lógica [ ] Segurança [ ] UX [ ] Performance [ ] Visual |

**Resumo**
A confirmação de matrícula é exibida ao aluno, mas o registro não aparece na lista "Minhas
matrículas". A aluna acredita ter se matriculado e não consegue comprovar a matrícula —
impacto direto em quem depende dela para a lista de chamada.

**Pré-condições**
- Aluna Ana Souza (id 1) cadastrada e **sem** matrícula na turma 9A (id 1).
- Turma 9A com vaga disponível.

**Passos para reproduzir**
1. Fazer login com `ana@escola.com`.
2. Abrir o menu **Matrícula**.
3. Selecionar a turma **9A**.
4. Clicar em **Finalizar matrícula**.
5. Confirmar na mensagem de sucesso.
6. Abrir o menu **Minhas matrículas**.

**Resultado esperado**
A matrícula na turma 9A aparece na lista "Minhas matrículas", com o comprovante enviado
para o e-mail da aluna.

**Resultado obtido**
A mensagem "Matrícula realizada com sucesso!" é exibida, mas a lista "Minhas matrículas"
continua vazia. Nenhum e-mail de comprovante é recebido.

**Evidências**
- [x] Print / vídeo (arquivo: `anexos/BUG-2026-014-minhas-matriculas.png`)
- [x] Log / console (trecho relevante)
- [x] Dados utilizados

```
2026-03-05 10:12:44 INFO  matricula.confirmar: aluno_id=1 turma_id=1 -> "Matrícula realizada com sucesso!"
2026-03-05 10:12:44 INFO  matricula.confirmar: INSERT não executado (nenhum registro retornado)
2026-03-05 10:12:45 INFO  matricula.listar: aluno_id=1 -> 0 matrículas
```

**Observações**
O usuário acredita estar matriculado, mas não há registro no banco. Suspeita de que a
gravação da matrícula não esteja sendo confirmada antes da mensagem de sucesso. Impacto em
relatórios de frequência.

> Nota sobre o português do relatório: bug report também é documento de trabalho. Escreva
> em português do Brasil, sem palavra em inglês solta ("believe", "handle", "bug") no meio do
> texto — a leitura fica mais rápida para todo mundo e passa mais confiança.

### 13 — O que faz um bom relato

**Alternativas corretas: A, B, C e E.**

- **A** Passos numerados — sem eles o tester precisa adivinhar como chegar no bug.
- **B** Esperado × obtido — é essa linha que separa "relato" de "reclamação".
- **C** Ambiente — o mesmo código falha em navegadores diferentes.
- **E** Evidências — print, vídeo ou log; o log costuma ser a evidência que **resolve** o bug.

**Incorretas:**

- **D** "O sistema está com defeito, recomendo corrigir." — Não diz **o quê**, **onde**,
  **quando** nem **como reproduzir**. Não é um relato, é uma reclamação.
- **F** "A causa do erro e a linha do código que deve ser alterada." — Quem relata **não
  conhece** o código. Inventar a causa leva o desenvolvedor para o caminho errado e ainda
  alimenta uma disputa. O tester relata **sintoma**; a causa é trabalho de quem corrige.

### 14 — Revisar um trecho de código

**Problemas identificados:**

**Legibilidade**

1. **Nomes abreviados** (`s`, `n`, `m`): o leitor precisa adivinhar o que é cada variável.
   *Correção:* `soma`, `nota`, `media`.
2. **Ausência de documentação**: nenhuma função diz o que recebe, o que devolve e qual regra
   aplica. *Correção:* adicionar docstring em `media()` e `resultado()`.
3. **`s = s + n` em vez de `s += n`**: mais longo e mais fácil de errar. *Correção:* `soma += nota`.

**Robustez**

4. **Divisão por zero**: `media([])` quebra com `ZeroDivisionError`. *Correção:*
   ```python
   def media(notas):
       if not notas:
           return 0.0
       soma = sum(notas)
       return soma / len(notas)
   ```
5. **Nenhuma validação das notas**: valores negativos ou acima de 10 são aceitos e contaminam
   a média. *Correção:* validar com `if not 0 <= nota <= 10: raise ValueError(...)`.
6. **Sem tratamento de entrada inválida**: se as notas vierem como texto, o `+` falha com
   `TypeError`. *Correção:* converter e validando antes de somar.

**Estilo**

7. **`else` desnecessário** depois de `return`: em Python, o `else` após um `return` é
   redundante. *Correção:* remover o `else` e deixar o `return` no mesmo nível do `if`.
8. **Falta de tipo de retorno documentado** e nomenclatura pouco descritiva
   (`resultado` → `classificar_situacao`). *Correção:* renomear a função e declarar o tipo.

**Versão revisada:**

```python
def media(notas: list[float]) -> float:
    """Devolve a média das notas. Retorna 0.0 se a lista estiver vazia."""
    if not notas:
        return 0.0

    for nota in notas:
        if not 0 <= nota <= 10:
            raise ValueError(f"Nota fora do intervalo 0-10: {nota}")

    return sum(notas) / len(notas)


def classificar_situacao(notas: list[float]) -> str:
    """Devolve a situação do aluno segundo a regra da escola (aprovado >= 6)."""
    media_aluno = media(notas)

    if media_aluno >= 6:
        return "Aprovado"

    return "Reprovado"
```

> A revisão não muda o **comportamento** do código original — ela muda o **custo** de manter
> esse código. É por isso que revisão de código é atividade de **qualidade**, não de caça a
> erro.

### 15 — Checklist de revisão

**Modelo (8 itens verificáveis):**

- [ ] **1.** O código **não contém** `print()` de depuração nem `console.log()` esquecidos?
- [ ] **2.** Todas as **variáveis** têm nome descritivo (sem abreviações de uma ou duas
      letras)?
- [ ] **3.** Toda função pública tem **documentação** dizendo o que recebe e o que devolve?
- [ ] **4.** Os **números mágicos** (valores soltos como `100` ou `1.15`) foram transformados em
      **constantes nomeadas**?
- [ ] **5.** Todo **tratamento de erro** previsto foi implementado (`try/except`, validação de
      entrada, `null`/vazio)?
- [ ] **6.** As **variáveis de ambiente** (URLs, senhas, chaves) estão **fora do código**?
- [ ] **7.** A alteração **não quebrou** nada: os testes existentes passam?
- [ ] **8.** A mensagem de **commit** explica **o que** mudou e **por quê**, em uma linha?

> Bônus (itens 9 e 10, para turmas mais avançadas):
> - [ ] 9. O código novo **não duplica** lógica que já existe em outro lugar do projeto?
> - [ ] 10. A alteração é **coberta por um teste** novo ou atualizado?

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Prova de QA | 10 ou mais acertos em 15 |
| Itens 5, 6 e 7 | O modelo está **completo** e serve para uso real |
| Item 11 | O aluno **justifica** a classificação, não só marca a letra |
| Item 12 | O bug report permite **reproduzir** sem pedir esclarecimento |
| Item 14 | O aluno separa **legibilidade**, **robustez** e **estilo** |

**Pergunta de escrita:**
> "Por que o bug report diz o que **deveria** acontecer, e não só o que aconteceu?"
> **Resposta:** porque quem lê o relato ainda não sabe o que o sistema faz. O "resultado
> esperado" é a **referência** contra a qual o defeito é medido — sem ela, o relato vira
> opinião, e o time de desenvolvimento perde o tempo discutindo se o comportamento atual
> "está certo".

---

## 🏠 Para casa

Baixe um dos sistemas com defeitos propositais (`qa-exercicios-praticos/sites-para-testar/`),
encontre **dois** bugs e escreva os bug reports correspondentes no modelo do item 12. Traga
para a aula seguinte: um dos bugs pode virar o seu **defeito da semana**.

---

## 🔗 Próximo módulo

[EX-PR7 — Banco de Provas: Simulados com gabarito comentado](07-provas.md)

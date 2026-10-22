# Projeto Final — Impacto Social em Open Source (13–17 anos)

**Duração:** 4 aulas × 90 min = **6 h** · **Aulas 13 a 16 de 16** (últimas 4 aulas da trilha)

> Entregável final: **repositório público no GitHub**, com `README.md`, histórico de
> commits, testes automatizados e deploy funcionando no GitHub Pages.

---

## 🎯 Objetivo

Ao final das 4 aulas, o aluno será capaz de:

1. **Definir o escopo** de um projeto de impacto social: escrever o problema, o público
   e uma lista de Histórias de Usuário com **critérios de aceitação** verificáveis.
2. **Implementar** o MVP (versão mínima viável) em HTML/CSS/JavaScript, Python ou a
   combinação que fizer sentido — versionando a cada pequena mudança no Git.
3. **Escrever e rodar testes** (manuais no plano de teste e automatizados no repositório)
   e registrar ao menos **1 bug corrigido** com evidência no histórico.
4. **Publicar** o projeto no GitHub Pages com `README.md`, licença e link funcionando.
5. **Apresentar** o projeto em 4 minutos, explicando o problema, a solução e **o que ficou
   para trás** (a parte que não coube no MVP).

**Objetivo secundário:** Assumir a responsabilidade de um código **público** — saber
explicar por que aquele dado está no repositório e por que aquele dado **não** está.

---

## 📚 Fontes no repositório

**Material-base real do próprio autor** (o roteiro do módulo 06 do laboratório):
`laboratorio-tech-social/trilhas/adolescentes-13-20/modulo-06-projeto-social.md` —
os 6 passos (problema → protótipo → teste → dados → publicar → mostra) e o **modelo de
README** que a turma vai usar.

**Trilha web e slides:**
`laboratorio-tech-social/site/trilhas/adolescentes/06-projeto.html` ·
`laboratorio-tech-social/materiais/slides/aula-teens-06-projeto.html` ·
`laboratorio-tech-social/site/trilhas/adolescentes/07-historia-computacao.html` (para a
"linha do tempo" da apresentação)

**Projetos reais do autor que mostram o "nível profissional" a atingir:**

| Projeto real | O que a turma pode copiar a ideia | Por que importa |
|---|---|---|
| `esporte-sao-pedro/` | Portal esportivo regional (notícias, campeonatos, artilharia, calendário, atletas, times) com Supabase + RLS + Edge Functions + IA + SEO + PWA | **Custo operacional zero** e stack 100% gratuita — o modelo de referência do projeto de avisos da escola |
| `Central-de-noticias/` | Reúne RSS de dezenas de fontes, resume de verdade, narra em áudio (`edge-tts`), deduplica, instala como PWA e **atualiza sozinho por `cron`** no GitHub Actions | O exemplo mais completo de "projeto útil + automação + deploy" |
| `qa-automation-framework/` | Framework em Python: `APIClient` com retry, Page Objects, dados falsos com `Faker`, relatórios Allure e CI | Modelo de **estrutura de pastas** e de teste automatizado |
| `manual-qa-completo/` | 11 módulos PT/EN, 7 scripts standalone, suítes pytest e `Makefile` (`make all`) | Modelo de **plano de teste** e de documentação |
| `hubias-estudos/` | SQLite no navegador (WASM) + flashcards + Pomodoro + sincronização | Exemplo de **app instalável** com dados no dispositivo |
| `anyms/` | IndexedDB, 17 tabelas e custo médio ponderado | Exemplo de **modelo de dados** mais elaborado |
| `lista_canais/` | Agregador de 70+ canais (arrays, filtro, agrupamento, ordenação) | Exemplo de **escopo pequeno e bem entregue** |

**Regra de ouro do professor:** se você vai mostrar um projeto do autor em aula,
**abra o código na frente da turma** e diga o que ele realmente faz. O README do
`esporte-sao-pedro` lista a stack e o custo zero — e o `index.html` dele tem a estrutura
completa do portal. Isso já é aula de ética e de pensamento crítico.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Impacto social** | "Resolve um problema **real** de gente real, com custo zero." |
| **MVP** | "A menor coisa **útil** que já resolve o problema. Não a menor coisa bonita." |
| **Escopo** | "Tudo que **não** está no MVP é 'fica para depois' — e isso está escrito." |
| **História de Usuário** | "Como **usuário**, eu quero ..., para poder ..." |
| **Critério de aceitação** | "O **como eu sei que acabou** — escrito antes de codar." |
| **Definition of Done** | "O checklist que diz que a história **pronto** está." |
| **Code review** | "O outro olho lê antes de virar 'oficial'." |
| **Open source** | "Código **aberto**: qualquer um pode ler, copiar e melhorar." |
| **Licença MIT** | "Permite usar, copiar e modificar — sem pedir licença." |
| **Deploy** | "O código **vira site**." |
| **Dado fictício** | "Dado inventado **para sempre** é mais seguro que dado real apagado." |
| **LGPD** | "Se tem nome de pessoa, tem responsável." |

---

## Regras da sala (a partir de hoje valem para o projeto final)

| Regra | Por quê |
|---|---|
| **Erro é método** — o professor pergunta, não entrega | autonomia |
| **"Commit ou não existe"** | sem histórico não há avaliação |
| **Nada é secreto** — o README documenta tudo | o README **é** a avaliação |
| **IA é ferramenta, não autor** | todo código gerado por IA precisa de revisão humana e ser reescrito em linguagem própria |
| **Nenhum dado real de aluno em repositório público** | ver seção "Política de dados" e `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §9 |
| **Teste que não roda é bug** | aprendo QA na própria pele |
| **Nenhum item quebrado entre a entrega e a apresentação** | se quebrar na hora da mostra, não tem conserto |

---

## Tema do projeto — escolha da turma (aula 13)

Cada dupla escolhe **1** tema. Todos os temas são **variantes de projetos reais do autor**,
então o "nível profissional" está ao alcance.

| # | Tema | Base real | Stack sugerida | Por que é um bom projeto social |
|---|---|---|---|---|
| **T1** | **Site de avisos da escola** — mural digital com eventos, prazos, editais e cardápio, com busca e filtro por categoria | `esporte-sao-pedro/` (estrutura de portal) | HTML, CSS, JavaScript | resolve o problema de todo mundo: "eu perdi o prazo" |
| **T2** | **Ferramenta de QA educativa** — um simulador web onde o aluno treina encontrar bugs (plano de testes, casos de teste, checklist de aceite) | `qa-automation-framework/` + `manual-qa-completo/` | HTML, CSS, JavaScript | transforma a própria aula de QA em jogo; foi a ideia do `Despertar QA` do autor |
| **T3** | **Bot/portal de dados do Esporte São Pedro** — página que consolida resultados, classificação e artilharia de um campeonato, alimentada por um arquivo JSON | `esporte-sao-pedro/` | HTML, CSS, JavaScript, JSON | o repo real usa Supabase; a versão da escola usa **JSON** para ficar no GitHub Pages |
| **T4** | **Portal de aulas gratuitas** — site com os exercícios do `python-do-zero` publicados, com progresso salvo no navegador | `python-do-zero/` | HTML, CSS, JavaScript, `localStorage` |material reaproveitado e publicado para a comunidade |
| **T5** | **Painel de dados do bairro** — gráfico e tabela com dados **fictícios** de reciclagem, com filtro por mês | `Central-de-noticias/` (dados + automação) | HTML, CSS, JavaScript, CSV/JSON | mostra o caminho de "dado → número → decisão" |
| **T6** | **Tema livre da dupla** — desde que responda às 3 perguntas: *qual problema real? para quem? o que a pessoa faz depois de usar?* | — | — | a turma propõe e o professor aprova na aula 13 |

> ⚠️ **Regra de escopo (vale para T1–T6):** o tema **precisa** caber em 6 horas de
> trabalho em dupla. Se não cabe, ele não é o tema — é o **sonho**. Troque por um MVP
> menor do mesmo tema.

**Como escolher (10 min, na aula 13):** cada dupla escreve o problema em **1 frase** e
diz em voz alta. Se o professor (ou a turma) não consegue dizer quem usa e o que ganha,
o tema volta para ajuste.

---

## Escopo — MVP e o que fica para depois

Escreva isto **no README** e **num issue** do repositório. É a primeira entrega da aula 13.

```
MVP (entra na entrega):
1. ...
2. ...
3. ...

FICA PARA DEPOIS (não conta como falha):
- ...
- ...
```

**Exemplo real (T1 — Site de avisos da escola):**

```
MVP:
1. Página inicial com a lista dos avisos (título, data, categoria)
2. Filtro por categoria (evento, prazo, edital, cardápio)
3. Busca por palavra no título
4. Botão "Novo aviso" que salva no navegador (localStorage)
5. Página "Sobre" com o contato da escola e a política de privacidade

FICA PARA DEPOIS:
- Envio de aviso por e-mail (precisa de servidor)
- Login de professor (precisa de backend)
- Notificação push
- PWA offline
```

> **Critério de qualidade do escopo:** se o MVP tem **mais de 7 itens**, corte. Corte de
> escopo **não** é falta de produtividade — é o que permite terminar.

---

## Backlog do projeto — Histórias de Usuário + critérios de aceitação

O backlog fica num arquivo `docs/backlog.md` no repositório (ou no GitHub Projects).
Cada história tem **critérios de aceitação** escritos **antes** de codar.

### Modelo de História de Usuário

```
US-01 — Como visitante, eu quero ver todos os avisos da escola em ordem de data,
        para não perder nenhum prazo.

Critérios de aceitação:
- [ ] A lista mostra título, data e categoria de cada aviso
- [ ] A ordenação é da data mais recente para a mais antiga
- [ ] Não existe aviso sem data
- [ ] Com 0 avisos, a tela mostra a mensagem "Nenhum aviso publicado" (sem erro no console)
```

### Backlog de exemplo (T1 — Site de avisos da escola)

| ID | História de Usuário | Critérios de aceitação (resumido) | Sprint |
|---|---|---|---|
| US-01 | Ver a lista de avisos em ordem de data | título, data e categoria visíveis; ordenado do mais novo para o mais antigo; mensagem amigável quando vazio | 13 |
| US-02 | Filtrar avisos por categoria | filtro mostra só a categoria escolhida; opção "Todas"; estado visível do filtro | 13 |
| US-03 | Buscar aviso por palavra | busca por título funciona; "nenhum resultado" é tratado; busca não quebra com acentuação | 13 |
| US-04 | Cadastrar um aviso novo | formulário valida título, data e categoria; aviso salvo no `localStorage`; aparece na lista sem recarregar a página | 14 |
| US-05 | Remover um aviso | botão "remover" apaga o item da lista e do armazenamento; a lista continua consistente | 14 |
| US-06 | Consultar a página "Sobre" | explica o propósito do site, quem mantém e onde reclamar; link para a política de privacidade | 14 |
| US-07 | Funcionar bem no celular | layout sem rolagem horizontal em 360 px de largura; menu e botões com área clicável mínima | 15 |
| US-08 | Não quebrar com dados vazios ou errados | aviso sem categoria, sem data ou com texto muito longo não quebra a página | 15 |

**O que conta como "feito"** (Definition of Done da história):
código no `main` + commit com mensagem no padrão `tipo: descrição` + critérios de
aceitação conferidos na tela + 0 erros no console do navegador.

---

## Definition of Done (o que "pronto" significa neste projeto)

Um item **só** está pronto quando **todas** as caixas abaixo estiverem marcadas:

- [ ] A história está no `docs/backlog.md` com os critérios de aceitação
- [ ] Todos os critérios de aceitação foram conferidos **na tela** (não no papel)
- [ ] O código está na branch `main`, com commit no padrão `tipo: descrição`
- [ ] Não há **erro** no console do navegador (F12 → Console → 0 erros)
- [ ] Não há **aviso** (warning) de console
- [ ] A página funciona no **celular** (testar em 360 px de largura)
- [ ] Tem **1 teste automatizado** que falha se a funcionalidade quebrar
- [ ] O `README.md` foi atualizado se a funcionalidade mudou o uso
- [ ] Nenhum dado real de aluno entrou no repositório (ver "Política de dados")
- [ ] Nenhum segredo (chave, token, senha) entrou no histórico do Git

---

## ⏱️ Plano das 4 aulas

### Aula 13 — Escopo e protótipo (90 min)

| Fase | Min | O que fazer |
|---|---|---|
| Apresentação | 10 | Mostre 3 projetos reais do autor (`esporte-sao-pedro`, `Central-de-noticias`, `qa-automation-framework`) e o `modulo-06-projeto-social.md` aberto. Diga: *"Today começa o que vai ficar no seu GitHub para sempre. Escolha com cuidado."* |
| Exploração | 15 | O roteiro de 6 passos do módulo 06 + a estrutura do README profissional. Ensine a diferença entre **escopo** e **lista de desejos**. |
| Mão na massa | 40 | **Atividade A:** cada dupla escreve o problema em 1 frase, escolhe o tema, escreve o MVP e o "fica para depois". **Atividade B:** escreve as **3 primeiras histórias** com critérios de aceitação no `docs/backlog.md`. **Atividade C:** protótipo de papel ou wireframe de baixa fidelidade — telas, campos, estados (vazio, erro, carregando). |
| Projeto | 20 | Cada dupla escreve o **README provisório** (modelo do `modulo-06-projeto-social.md`) e abre o repositório no GitHub com `README.md` e `LICENSE` (MIT). Primeiro commit: `chore: estrutura inicial do projeto`. |
| Mostra | 5 | 1 minuto por dupla: problema + público + 3 histórias. A turma diz "qual história eu escolheria" — e a dupla ajusta. |

**Entregável da aula 13:**
- [ ] `docs/backlog.md` com **3 a 8 histórias** e critérios de aceitação
- [ ] README provisório com **problema, público, tecnologias, como rodar, licença**
- [ ] Escopo escrito: MVP e "fica para depois"
- [ ] Repositório criado no GitHub, `LICENSE` MIT, `README.md` e `docs/backlog.md` commitados

### Aula 14 — Implementação (90 min)

| Fase | Min | O que fazer |
|---|---|---|
| Apresentação | 10 | Mostre o histórico `git log --oneline` de um projeto real e pergunte: *"Onde está a decisão de projeto aqui?"* Explique que **o histórico conta a história**. |
| Exploração | 10 | Regras de branch (`feature/`, `fix/`), PR e revisão. Mostre `git switch -c feature/us01`, `git add`, `git commit -m "feat: lista de avisos em ordem de data"`. |
| Mão na massa | 50 | Cada dupla implementa **1 história por vez**, no ritmo: **implementar (30 min) → testar no navegador (5 min) → commitar (5 min) →_pair review_ (10 min)**. |
| Projeto | 15 | Cada dupla termina **todas** as histórias do MVP e escreve um `docs/decisoes.md` curto: "por que usamos X em vez de Y". |
| Mostra | 5 | Troca de telas: cada dupla mostra o que já funciona no site de outra dupla e escreve 1 bug encontrado (título + como reproduzir). |

**Entregável da aula 14:**
- [ ] Todas as histórias do MVP implementadas e conferidas
- [ ] **10 ou mais commits** no padrão `tipo: descrição`
- [ ] `docs/decisoes.md` com pelo menos 2 decisões técnicas e o motivo
- [ ] 1 branch `feature/...` criada, usada e **mesclada**
- [ ] Ao menos **1 bug** encontrado na revisão de um colega e registrado

### Aula 15 — Testes e deploy (90 min)

| Fase | Min | O que fazer |
|---|---|---|
| Apresentação | 10 | Mostre o `tests/` do `qa-automation-framework` e o `Makefile` do `manual-qa-completo`. Explique: *"teste que não roda é bug"*. |
| Exploração | 15 | Plano de teste simples (caso, passo, esperado), testes automatizados de interface, e o passo a passo do GitHub Pages. |
| Mão na massa | 45 | **Atividade A:** escrever o plano de teste (mínimo 5 casos). **Atividade B:** automatizar **pelo menos 1** teste. **Atividade C:** publicar no GitHub Pages e configurar o workflow. |
| Projeto | 15 | Corrigir os bugs da revisão da aula 14, escrever o `CHANGELOG` do `v1.0` e criar a tag. |
| Mostra | 5 | Cada dupla mostra **o link do site publicado** e roda o teste automatizado na frente da turma. |

**Entregável da aula 15:**
- [ ] Plano de teste com **5 ou mais casos** (`docs/plano-de-testes.md`)
- [ ] **1 teste automatizado** que roda e falha se a funcionalidade quebrar
- [ ] Site **publicado no GitHub Pages** e linkado no README
- [ ] `0` erros e `0` warnings no console na versão publicada
- [ ] Tag `v1.0` criada
- [ ] 1 bug corrigido com **evidência** (issue + commit `fix:`)

> **Plano B (sem GitHub Pages por falta de conta):** o site é publicado no
> **GitHub Pages de uma conta da escola** (o professor cria e convida a dupla como
> colaborador). Nunca publique em conta pessoal do aluno para projeto da escola.

### Aula 16 — Showcase (90 min)

| Fase | Min | O que fazer |
|---|---|---|
| Apresentação | 10 | Retome as 12 aulas: "olha o caminho". Mostre o modelo de apresentação de 4 min (abaixo). |
| Exploração | 5 | Combinações e o que a turma aprendeu: versionamento, HTML, banco, QA, IA, ágil, ética, inglês. |
| Mão na massa | 55 | **Apresentações: 4 min por dupla** (2 min de fala + 2 min de perguntas). Formato obrigatório: nome do projeto (10 s) · o que é (30 s) · como fiz (60 s) · demonstração ao vivo (60 s) · o que ficou para trás (20 s). |
| Projeto | 15 | **Feira de projetos**: a turma circula entre as telas/tablets, testa o site de cada dupla e deixa um comentário no repositório (issue ou comentário no PR). |
| Mostra | 5 | Mural final: cada dupla cola 1 frase "o que eu descobri" e 1 "o que eu quero aprender agora". Fechamento do professor + entrega do certificado. |

**Entregável da aula 16:**
- [ ] Apresentação de 4 min feita pela dupla
- [ ] Site publicado funcionando **demonstrado ao vivo**
- [ ] **1 issue ou comentário** deixado por outro colega no repositório da dupla
- [ ] Frase do mural
- [ ] Repositório público, com README, commits, testes e Pages — **entregável final**

---

## Revisão de código em pares

Toda história implementada passa por **outro par**. Não é opcional: é o momento em que
o projeto aprende a ser lido por outra pessoa.

**Protocolo de revisão (12 min por história):**

1. O autor **explica** o que mudou em 1 minuto (`git diff` na tela).
2. O revisor responde as 4 perguntas do checklist abaixo.
3. O revisor escreve a findings no PR (ou no `docs/revisoes.md`) e **aprovou** ou **pediu ajustes**.
4. O autor responde: "ajustei" ou "não ajustei, e o motivo é X".

**Checklist de revisão (4 perguntas):**

- [ ] O código faz o que a História de Usuário diz? (nada a mais, nada a menos)
- [ ] Os critérios de aceitação estão **todos** marcados?
- ] Tem **nome de variável** que explica o que é? (sem `x`, `aux`, `dados2`)
- [ ] Tem **comentário** só onde é preciso? (o código deve se explicar sozinho)
- [ ] O commit está no padrão `tipo: descrição` e faz **uma** coisa só?

**Palavras que o revisor pode usar** (treine a turma a usar estas, e não xingamentos):
*"não entendi essa parte"*, *"esse nome não me diz o que é"*, *"falta um teste aqui"*,
*"esse commit faz duas coisas"*, *"falta o que fazer quando a lista está vazia"*.

> **Se der tempo, o exercise real de revisão está em**
> `git-github-iniciantes/07_pull_requests/` (fork, branch, PR e code review) e em
> `qa-exercicios-praticos/modelos-templates/` (bug report e checklist de aceite).

---

## Política de dados — sem dados reais de alunos

**Regra absoluta: nenhum dado real de aluno entra no repositório público.**

| Situação | O que fazer |
|---|---|
| Precisa de nome de pessoa | Use nome **fictício** ("Ana Souza", "Aluno Exemplo") |
| Precisa de e-mail | Use `aluno01@exemplo.com` (domínio reservado para exemplos) |
| Precisa de telefone | Não coloque telefone. Use `(00) 00000-0000` |
| Precisa de RG/CPF/endereço | **Nunca.** Nem em arquivo local, nem no histórico |
| Precisa de foto | Use imagem de exemplo genérica ou um **avatar** desenhado |
| Precisa de nota/resultado de aluno | Gere o dado com o gerador de dados fictícios (`laboratorio-tech-social/site/exercicios/gerador-dados.html`) |
| Tem dado real no histórico | Não dá para "apagar" com um commit novo. **Rotacione/anonimize o dado na origem** e reescreva o histórico (`git filter-repo`) — ver a aula de Git |

**Checklist antes de publicar (roda isso, não confie na memória):**

```bash
# 1. Procura e-mails reais no código e nos dados
grep -RIn "@" --include="*.html" --include="*.js" --include="*.json" --include="*.csv" .

# 2. Procura segredos (chaves, tokens, senhas) no histórico inteiro
git log --all --full-history -- "*.env" "*.pem" "*.key"
git grep -n -E "(api[_-]?key|secret|token|password)\s*[:=]" -- .

# 3. Lista os arquivos que serão publicados
git ls-files
```

**Se aparecer um dado real:** não publique. Avise o professor, remova o arquivo,
anonimize o conteúdo e **reescreva o histórico** antes de fazer o `push`. Um dado vazado
não "desaparece" com um commit novo — o objeto antigo continua no histórico, legível
por qualquer pessoa.

> Base legal e de conduta: [ANPD — Autoridade Nacional de Proteção de Dados](https://www.gov.br/anpd/pt-br)
> e `laboratorio-tech-social/docs/seguranca-criancas.md`.

---

## Checklist de publicação (o dia do `push` final)

```text
[ ] 1. `git status` → "nothing to commit, working tree clean"
[ ] 2. `git log --oneline` → 10 ou mais commits, todos no padrão "tipo: descrição"
[ ] 3. `git branch -a` → nenhuma branch de trabalho abandonada pela metade
[ ] 4. `git ls-files` → nenhum arquivo que não devia ir (planilha, foto, .env, senha)
[ ] 5. `grep -RIn "@"` → só e-mails de exemplo (@exemplo.com)
[ ] 6. `README.md` → nome, slogan, problema, público, o que faz, como rodar,
        tecnologias, licença e o LINK DO SITE PUBLICADO
[ ] 7. `LICENSE` → MIT, com o ano e o nome da escola/dupla
[ ] 8. `docs/backlog.md` → o escopo e o "fica para depois" estão escritos
[ ] 9. `docs/plano-de-testes.md` → o plano de teste existe
[ ] 10. Teste automatizado roda: `pytest` (ou o comando do projeto) → tudo verde
[ ] 11. Repositório está PÚBLICO e é o repositório certo (olhe a URL, não confie)
[ ] 12. GitHub Pages: Settings → Pages → branch main, pasta / (root) → URL abre
[ ] 13. Abri a URL publicada numa aba anônima e vi que funciona
[ ] 14. Console do site publicado sem erro e sem warning
[ ] 15. Não existe nenhum dado real de aluno nem segredo no repositório
[ ] 16. `git tag -a v1.0 -m "primeira versão pública"` criado
```

---

## 📝 Avaliação

| Componente | Peso | Onde é medido |
|---|---|---|
| Escopo e backlog | 15% | `docs/backlog.md` com critérios de aceitação |
| Implementação e histórico Git | 25% | 10+ commits, padrão `tipo: descrição`, branch mesclada |
| Testes | 20% | plano de teste + 1 teste automatizado verde |
| README e documentação | 15% | README, `docs/decisoes.md`, licença |
| Política de dados | 10% | nenhum dado real nem segredo no repositório |
| Deploy e Showcase | 15% | site publicado + apresentação de 4 min |

**Rubrica resumida (4 níveis, adaptada de `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §4.2):**

| Nível | Descrição |
|---|---|
| **1** | Entregou parcial: site sem publicar, README vazio, sem testes. |
| **2** | Entregou o MVP funcionando, mas sem README, sem testes ou com escopo estourado. |
| **3** | Entregou completo, **documentado**, **testado** e **publicado**, com commits padronizados. |
| **4** | Entregou tudo do nível 3 **e** revisou o código de um colega, **corrigiu 1 bug** encontrado por ele, e o repositório está limpo de dados pessoais. |

**Pergunta de escrita:**
> "O site de avisos da escola precisa mostrar o nome e o telefone do professor responsável
> pelo evento. O professor disse: 'coloca o meu número, é só um site da escola'.
> O que você faz?"
> **Resposta:** Você **não** publica telefone nem dado pessoal sem autorização clara e
> base legal. O caminho profissional é: (1) registrar no README a **política de privacidade**
> e os dados de contato **institucionais** (e-mail do departamento, não o celular
> pessoal); (2) pedir autorização por escrito e registrar a base legal (LGPD); (3) preferir
> um e-mail institucional e **não** número de telefone; (4) se o contato for mesmo
> necessário, usar formulário que **encaminha** a mensagem em vez de exibir o dado. E
> lembrar: **repositório público é público para sempre** — o `git log` não esquece.
> (Ver `laboratorio-tech-social/docs/seguranca-criancas.md` e o guia da
> [ANPD](https://www.gov.br/anpd/pt-br).)

---

## Lista final de verificação do repositório

> Marque esta lista **no próprio README** do projeto (como caixa de seleção) ou em
> `docs/checklist.md`. É a mesma lista do professor, então ninguém surpreende ninguém.

```markdown
## ✅ Checklist do repositório

### Código
- [ ] O código está organizado em pastas com nome claro (src/, data/, docs/, tests/)
- [ ] Tem um README.md na raiz
- [ ] Tem LICENSE (MIT)
- [ ] Tem .gitignore (venv/, __pycache__/, .env, node_modules/, *.db)
- [ ] Nenhum arquivo temporário ou backup commitado

### Versionamento
- [ ] 10 ou mais commits, todos no padrão "tipo: descrição"
- [ ] Existe pelo menos uma branch feature/ já mesclada
- [ ] Existe a tag v1.0
- [ ] O histórico conta a história do projeto (mensagens explicam o porquê)

### Testes
- [ ] Existe docs/plano-de-testes.md com casos de teste
- [ ] Existe pelo menos 1 teste automatizado que roda
- [ ] O comando de teste está escrito no README
- [ ] Existe um bug corrigido, com issue ou registro

### Documentação
- [ ] README tem: problema, público, o que faz, como rodar, tecnologias, licença, link
- [ ] docs/backlog.md tem o escopo e o "fica para depois"
- [ ] docs/decisoes.md explica pelo menos 2 decisões técnicas

### Publicação
- [ ] Repositório público no GitHub
- [ ] GitHub Pages ativo e a URL abre em aba anônima
- [ ] Console sem erro e sem warning
- [ ] Funciona no celular (360 px)

### Segurança e ética
- [ ] Nenhum dado real de aluno
- [ ] Nenhum segredo, token ou chave
- [ ] Política de privacidade citada no site
```

---

## 🏠 Para casa

1. Escreva o **`CONTRIBUTING.md`** do repositório, seguindo o modelo real do autor em
   `laboratorio-tech-social/CONTRIBUTING.md`: como contribuir, como rodar os testes,
   padrão de commit e código de conduta.
2. Abra **1 issue** no repositório de outra dupla com um **bug real** encontrado na
   apresentação (com passos para reproduzir). Isso é o exercício de review de verdade.
3. Escreva a versão em **inglês** do `README.md` — a aula 12 ([B12 — Inglês Técnico](12-ingles-tecnico.md))
   serve exatamente para isso.
4. (Opcional) Publique o mesmo projeto em um serviço gratuito de páginas estáticas
   alternativo para comparar (por exemplo, [Cloudflare Pages](https://pages.cloudflare.com/)).

---

## 🔗 Próxima trilha

[Trilha JOVENS E ADULTOS (18+) — Profissionais](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md)

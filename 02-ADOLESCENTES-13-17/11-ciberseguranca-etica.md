# B11 — Cibersegurança, Ética e Paradigmas (13–17 anos)

**Duração:** 90 min · **Aula 11 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Explicar os **4 pilares** da segurança da informação — **confidencialidade, integridade, disponibilidade e não-repúdio** — com um exemplo do próprio projeto.
2. Reconhecer **phishing, malware e engenharia social** e aplicar **senha forte + 2FA**.
3. Fazer **higiene digital**: segredos no `.gitignore`, atualizações, backup **3-2-1**.
4. Discutir **ética em tecnologia**: impacto em terceiros, privacidade, **viés de algoritmo**, IA responsável, **licença e autoria**.
5. Explicar a **LGPD** em linguagem simples — e perceber que, com 13 a 17 anos, **você é titular dos seus próprios dados**.
6. Entregar a **Política de Segurança do Projeto** (1 página) e abrir a **aula aberta** para a turma.

**Objetivo secundário:** Entender que "anônimo" na internet não existe e que a responsabilidade ética de quem escreve o código é com quem vai usá-lo.

> ⚠️ **As regras do repositório vêm primeiro.** O projeto tem um documento específico
> sobre menores (`laboratorio-tech-social/docs/seguranca-criancas.md`). Esta aula
> **aplica** essas regras: **nenhum dado pessoal real** de aluno, **nenhum contato
> direto** (telefone, e-mail, @, endereço), nenhuma comunicação de menor por canal
> privado e **consentimento por escrito do responsável** antes de qualquer publicação
> (imagem, vídeo, nome ou trabalho).

---

## 📚 Fontes no repositório

`pensamento_computacional/13_ciberseguranca/` — **README + 6 exercícios `.txt`**:

| Arquivo | Sobre |
|---|---|
| `pensamento_computacional/13_ciberseguranca/README.md` | O que é cibersegurança e as **5 ameaças principais** (phishing, malware, senhas fracas, Wi-Fi público, engenharia social) e as boas práticas |
| `pensamento_computacional/13_ciberseguranca/exercicio_01_senhas.txt` | Classificar 10 senhas como FRACA / MÉDIA / FORTE + a pergunta sobre gerenciador de senhas |
| `pensamento_computacional/13_ciberseguranca/exercicio_02_phishing.txt` | Identificar e-mails e sites falsos |
| `pensamento_computacional/13_ciberseguranca/exercicio_03_golpes.txt` | Reconhecer golpes comuns |
| `pensamento_computacional/13_ciberseguranca/exercicio_04_boas_praticas.txt` | Checklist de segurança |
| `pensamento_computacional/13_ciberseguranca/exercicio_05_criptografia.txt` | Como funciona a criptografia |
| `pensamento_computacional/13_ciberseguranca/exercicio_06_simulacao.txt` | "Pense como um hacker" (3 cenários) — a resposta do repo: *"a maior vulnerabilidade de um sistema são os **usuários**"* |

`pensamento_computacional/15_etica_sociedade/` — **README + 6 exercícios `.txt`**:

| Arquivo | Sobre |
|---|---|
| `pensamento_computacional/15_etica_sociedade/README.md` | *"A tecnologia não é neutra"* + 5 grandes questões: privacidade, IA e empregos, desigualdade digital, dependência tecnológica, meio ambiente |
| `pensamento_computacional/15_etica_sociedade/exercicio_01_dilemas.txt` | 4 dilemas éticos (IA no hospital, carro autônomo, reconhecimento facial, vazamento de dados) |
| `pensamento_computacional/15_etica_sociedade/exercicio_02_privacidade.txt` | Seus dados |
| `pensamento_computacional/15_etica_sociedade/exercicio_03_ia_emprego.txt` | O futuro do trabalho |
| `pensamento_computacional/15_etica_sociedade/exercicio_04_desigualdade.txt` | Acesso à tecnologia |
| `pensamento_computacional/15_etica_sociedade/exercicio_05_saude.txt` | Tecnologia e bem-estar |
| `pensamento_computacional/15_etica_sociedade/exercicio_06_manifesto.txt` | Manifesto pessoal de 1 página (entregável da aula) |

`laboratorio-tech-social/` — **as regras que esta aula aplica**:

| Arquivo | Sobre |
|---|---|
| `laboratorio-tech-social/docs/seguranca-criancas.md` | **As 5 regras obrigatórias** (nunca expor dados de alunos; locais públicos autorizados; sem canal privado com menores; imagens/vídeos só com autorização por escrito), as regras de **LGPD e menores** e a conduta |
| `laboratorio-tech-social/inscricao/index.html` | Formulário real com campo de **consentimento (LGPD/ECA)** do responsável |
| `laboratorio-tech-social/inscricao/README.md` | *"Coletamos o mínimo necessário, com consentimento dos responsáveis"*; dados de menores não são repassados a terceiros para marketing |
| `laboratorio-tech-social/.gitignore` | **Modelo real de higiene**: já ignora `.env`, `__pycache__/`, `*.pyc`, `.venv/`, `venv/`, `.DS_Store`, `Thumbs.db` |
| `laboratorio-tech-social/site/exercicios/quiz-ciberseguranca.html` | Quiz de Cidadania Digital (senha, LGPD, Wi-Fi público) com **gabarito por pergunta** |
| `laboratorio-tech-social/site/exercicios/gerador-senhas.html` | Gerador de senhas fortes, com botão de copiar |
| `laboratorio-tech-social/site/exercicios/verdadeiro-falso.html` | Verdadeiro ou falso (inclui *"A LGPD protege os dados pessoais no Brasil"*) |
| `laboratorio-tech-social/site/exercicios/quiz-criancas.html` | Quiz da faixa 8–12 (o professor usa para preparar a aula) |
| `laboratorio-tech-social/site/exercicios/quiz-teens.html` | Quiz da faixa 13–17 |
| `laboratorio-tech-social/site/trilhas/criancas/05-cidadania.html` | *"No Brasil, a LGPD protege seus dados pessoais. Você tem direito de saber como usam suas informações e de pedir para apagar."* |

`o-despertar-qa/` — site de QA com **página de segurança**:

| Arquivo | Sobre |
|---|---|
| `o-despertar-qa/README.md` | README **em inglês** de um site real — usado na aula 12 |
| `o-despertar-qa/O Despertar para Qualidade de Software.md` | Objetivo do site: transformar a teoria de qualidade em ação prática |
| `o-despertar-qa/src/pages/` | Páginas do site, entre elas `testes de segurança .jrmxa.js` e `Simulador de APIs REST.w8c58.js` |
| `o-despertar-qa/.gitignore` | Ignora `node_modules/`, `.vscode/`, `.idea/`, `.wix/` |

`questionario/` — **questionário HTML com gabarito embutido** (modelo de material):

| Arquivo | Sobre |
|---|---|
| `questionario/index.html` | Página única com todas as perguntas e as respostas comentadas no próprio arquivo |
| `questionario/Guia da Questões/sumário.md` | Índice dos guias de estudo — modelo de "índice do material" |
| `questionario/Guia da Questões/Exercicios resolvidos - Introdução.md` | Guia de introduction com respostas |
| `questionario/Imagens/Arquitetura.jpg` | Imagem usada no material |
| `questionario/.gitignore` | `.gitignore` real do projeto — ignora artefatos de build, `*.pfx`, `*.publishsettings`, `*.snk` |

`CyberSec-_Crosswords/` — ⚠️ **contém apenas `README.md`** (um único arquivo, sem os
crosswords). Serve de exemplo honesto de **primeira contribuição open source**:
ler o README, abrir uma issue perguntando o que falta e contribuir com o que se sabe.

**Links:**
[ANPD — Lei Geral de Proteção de Dados](https://www.gov.br/anpd/pt-br) ·
[Laboratório Tech Social](https://marquezbertin.github.io/laboratorio-tech-social/) ·
[Git — Pro Git (pt-BR)](https://git-scm.com/book/pt-br) ·
[Documentação do GitHub](https://docs.github.com/pt)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Confidencialidade** | "Só quem pode ver, vê." |
| **Integridade** | "Ninguém alterou o meu dado sem autorização." |
| **Disponibilidade** | "Quando eu preciso, está lá." |
| **Não-repúdio** | "Não dá para negar que foi você." |
| **Phishing** | "A isca vem por e-mail, SMS ou DM. Confira o **domínio**, não o desenho." |
| **Malware** | "Software feito para estragar: vírus, trojan, ransomware, spyware." |
| **Engenharia social** | "A pessoa é o sistema. O golpe usa medo, pressa e confiança." |
| **Senha forte** | "Longa, com letras + números + símbolos, e **diferente em cada conta**." |
| **2FA** | "Senha **mais** um segundo fator. Senha sozinha já vaza." |
| **Gerenciador de senhas** | "Uma senha forte bem guardada vale mais do que cinco senhas fracas lembradas." |
| **`.gitignore`** | "O arquivo que diz ao Git: **nunca** versione isto." |
| **Backup 3-2-1** | "3 cópias, 2 mídias, 1 fora do lugar." |
| **LGPD** | "Lei brasileira de proteção de dados. O dono dos dados é **você**." |
| **Titular dos dados** | "Com 13–17 anos, **você** é o titular — não os seus pais." |
| **Consentimento** | "Autorização informada, específica, para um fim. Pode ser revogada." |
| **Impacto em terceiros** | "Seu código mexe com a vida de quem não está na sala." |
| **Viés de algoritmo** | "O modelo repete o viés dos dados que o alimentaram." |
| **IA responsável** | "Transparência, supervisão humana e direito de contestação." |
| **Licença** | "As regras do que você **pode** fazer com o código — e do que não pode." |
| **Autoria** | "Declare o que é seu e o que veio de IA ou de outra pessoa." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Todo mundo aqui tem 13 a 17 anos. Isso significa que, pela LGPD, **vocês
são os titulares dos próprios dados** — não os pais. E quase todo mundo aqui já
entregou um dado real sem pensar: nome completo, escola, localização. Hoje são duas
aulas na mesma hora: **como proteger** e **como não ferir ninguém**."*

**Demonstração ao vivo (5 min):** abra
`laboratorio-tech-social/site/exercicios/quiz-ciberseguranca.html` e jogue 3 perguntas
com a turma (é o quiz real do repositório, com gabarito por pergunta: senha segura,
o que é a LGPD, Wi-Fi público e banco).

Depois abra `laboratorio-tech-social/site/exercicios/gerador-senhas.html` e gere uma
senha — sem digitar senha real no gerador de ninguém.

### Fase 2 — Exploração (20 min)

**Parte 1 — Os 4 pilares (6 min).**

| Pilar | Pergunta que ele responde | Exemplo no projeto da turma |
|---|---|---|
| **Confidencialidade** | "Só quem pode ver, vê?" | A chave da API fica no `.env`, fora do Git; os dados dos usuários no banco não aparecem no site |
| **Integridade** | "Ninguém alterou isso sem autorização?" | Ninguém mexe no arquivo de dados; o histórico do Git mostra quem mudou o quê |
| **Disponibilidade** | "Está lá quando eu preciso?" | O site no GitHub Pages não cai no dia da apresentação |
| **Não-repúdio** | "Dá para provar que foi você?" | Commit com autor e data; log de acesso; histórico do repositório |

Diga: *"Quatro perguntas. Se a resposta de qualquer uma for 'não', o problema
existe — e a aula 08 (QA) é justamente a busca por essas respostas."*

**Parte 2 — Ameaças (4 min).**

| Ameaça | Como aparece | Defesa |
|---|---|---|
| **Phishing** | E-mail/SMS/DM com link falso e urgência ("sua conta será bloqueada hoje") | conferir o **domínio real** do link, nunca clicar sob urgência, ir ao site digitando o endereço |
| **Malware** | Vírus, trojan, ransomware, spyware | sistema atualizado, antivírus, não abrir anexos estranhos, não instalar programa pirata |
| **Engenharia social** | Golpe do WhatsApp, golpe do banco, "suporte" pedindo o código | responder "vou verificar e te ligo de volta"; **nunca** dar senha ou código de verificação |
| **Senha fraca** | `123456`, `senha`, data de nascimento | senha forte e **única por conta** + 2FA |
| **Wi-Fi público** | Rede aberta na escola, no shopping, no café | não acessar banco em rede aberta; usar dados móveis |

Lembrete do repositório (`pensamento_computacional/13_ciberseguranca/exercicio_06_simulacao.txt`):
a resposta do gabarito é *"a maior vulnerabilidade de um sistema são os **usuários**"*.

**Parte 3 — Senha forte, 2FA e higiene digital (6 min).**

Senha forte, com os exemplos reais do
`pensamento_computacional/13_ciberseguranca/exercicio_01_senhas.txt`:
`123456`, `abcdef`, `111111` e `senha` são **fracas**; `Maria1990` e `P@ssw0rd` são
fracas por adivinháveis; `AbCdEf123!@#` e `Tr@b@lho2024!` são **fortes**.
Regra prática: **comprimento vence complexidade** — uma frase-índice longa
("meu-gato-ruim-gosta-de-pesca") é mais forte do que `Abc@1`.

**2FA (verificação em duas etapas):** a senha entra **e** vem um segundo fator
(código no aplicativo autenticador, no SMS ou a confirmação no e-mail). Serve porque
senha sozinha vaza — e é exatamente o que o golpe do SMS tenta roubar.

**Higiene digital — o checklist:**
```
[ ] Nenhum segredo no repositório: senhas, chaves de API e tokens vão em .env
[ ] .gitignore com: .env, __pycache__/, *.pyc, node_modules/, .venv/, *.db
[ ] Sistema, navegador e extensões atualizados
[ ] Backup 3-2-1: 3 cópias, 2 mídias diferentes, 1 fora do lugar
[ ] 2FA ligado nas contas que importam (e-mail, GitHub, conta da escola)
[ ] Site do banco acessado digitando o endereço, nunca pelo link da mensagem
```

`.gitignore` real (modelo de `laboratorio-tech-social/.gitignore`):
```gitignore
# Variáveis de ambiente com segredos — NUNCA versionar
.env
.env.*

# Python
__pycache__/
*.pyc
.venv/
venv/

# Node
node_modules/

# Sistema
.DS_Store
Thumbs.db
```

Explique o ponto que ninguém avisa: **se o segredo já foi commitado, apagar o arquivo
não resolve.** O segredo continua no histórico do Git — é preciso **rotacionar**
(trocar) a chave. Por isso o `.gitignore` se escreve **antes** do primeiro commit,
não depois.

**Parte 4 — LGPD em linguagem simples (4 min).**

- A **LGPD** (Lei nº 13.709/2018) protege os dados pessoais no Brasil.
- Com 13 a 17 anos, **você** é o **titular** dos seus dados — o titular é quem tem
  o direito de decidir sobre eles.
- **Direitos do titular** (os mais importantes para a turma):
  saber quem tem seus dados; pedir correção; pedir anonimização/bloqueio/eliminação;
  revogar o consentimento; pedir a portabilidade dos dados.
- Para **menores**, o consentimento do **responsável legal** é específico e em
  destaque, e vale o **melhor interesse da criança e do adolescente**.
- O lado do responsável: coletar o **mínimo** necessário, ter um motivo legal e
  explicar o que vai fazer com os dados.

Diga: *"A LGPD não é 'a lei contra a internet'. É a lei que diz: os dados são
**seus** — e alguém precisa pedir licença."*

### Fase 3 — Mão na massa (35 min)

**Atividade A — Checklist de segurança do projeto (15 min).**

Em duplas, com `pensamento_computacional/13_ciberseguranca/exercicio_01_senhas.txt`,
`exercicio_04_boas_praticas.txt` e `exercicio_06_simulacao.txt`:

1. Avaliem a senha que a equipe pretende usar: classifiquem de FRACA a FORTE e
   **reescrevam** usando a regra da frase-índice.
2. Listem as contas que precisam de **2FA** (e-mail, GitHub, conta da escola,
   repositório do projeto) e marquem quais já têm.
3. Escrevam o `.gitignore` do projeto da turma e **testem**: criem um `.env` falso
   com `CHAVE_TESTE=valor_falso`, rodem `git add .` e conferem no `git status` que
   o `.env` **não** entrou.
4. Respondam `exercicio_06_simulacao.txt`: *"qual é a maior vulnerabilidade de um
   sistema?"* (gabarito do repo: os **usuários**) e *"o que você vai mudar nos seus
   hábitos depois deste exercício?"*.

**Atividade B — Dilemas éticos (10 min).**

Com `pensamento_computacional/15_etica_sociedade/exercicio_01_dilemas.txt` — 4 dilemas:
1. IA que acerta 95% no hospital: de quem é a culpa nos 5% de erro?
2. Carro autônomo: atropelar uma pessoa ou bater na árvore?
3. Reconhecimento facial para prevenir crimes: é ético?
4. A empresa descobre que houve vazamento: avisa na hora ou espera ter certeza?

Regras do debate:
- Cada dupla pega **2 dilemas** e escreve **um argumento a favor** e **um contra**.
- A dupla diz qual **regra** usaria para decidir — não qual resposta está "certa".
- Ninguém usa argumento pessoal ("meu avô foi roubado"): o argumento tem que valer
  para qualquer pessoa.

Feche montando no quadro a **régua de decisão** do projeto da turma:
```
Para decidir se meu código é aceitável, eu pergunto:
1. Quem é afetado — e essa pessoa sabe?            (impacto em terceiros)
2. De quem são os dados? preciso de todos eles?     (privacidade / LGPD)
3. O modelo ou os dados que usei têm viés?         (viés de algoritmo)
4. Consigo explicar em 1 frase como funciona?       (transparência)
5. Estou creditando a fonte? a licença permite?     (licença e autoria)
```

**Atividade C — Política de segurança do projeto (10 min).**

Cada aluno preenche o **template de 1 página** (entregável da aula):

```markdown
# Política de Segurança e Ética — <Nome do Projeto>

**Responsável:** <turma/equipe> · **Data:** <dd/mm/aaaa> · **Versão:** 1

## 1. O que é o projeto e o que ele faz?
(2 frases)

## 2. Que dados ele guarda?
| Dado | De quem | Para quê | Onde fica | Por quanto tempo |
|---|---|---|---|---|
| (ex.) tarefas cadastradas | de quem usa o app | mostrar a lista | SQLite local | enquanto o app existir |

> Regra do projeto: **nenhum dado real de aluno**, nenhum contato direto
> (telefone, e-mail, @, endereço).

## 3. Senhas e acesso
- Onde ficam as senhas e chaves? (variável de ambiente / .env, fora do Git)
- Quem tem acesso ao repositório?
- 2FA ligado em quais contas? (sim/não — quais)

## 4. Backup e recuperação
- Backup 3-2-1 (3 cópias, 2 mídias, 1 fora do lugar): onde ficam?

## 5. Dependências e licenças
- Quais bibliotecas o projeto usa? (nome + tipo de licença)

## 6. Autoria e IA
- O que foi escrito pela equipe?
- O que veio de ferramenta de IA (e foi revisado por humano)?
- De onde vieram os dados de exemplo? (fictícios? cite a fonte)

## 7. Consentimento e publicação
- O que será publicado (site, GitHub, imagem, vídeo)?
- Quem autorizou (responsável legal, por escrito)?
- Como tiramos do ar se alguém pedir?

## 8. Riscos que a equipe aceitou
(lista curta e honesta)
```

### Fase 4 — Projeto (20 min)

**Desafio: "Política de segurança do projeto + aula aberta"**

Entregue a **Política de Segurança e Ética do projeto final** (1 página, as 8 seções
acima) e conduza **15 minutos de aula aberta** com a turma.

**Critério de pronto:**
- [ ] Política com as **8 seções preenchidas** — sem "TODO" e sem seção em branco
- [ ] **Nenhum dado pessoal real** e **nenhum contato direto** (telefone, e-mail, @, endereço)
- [ ] `.gitignore` do projeto com `.env` e segredos — **testado** (o `.env` não aparece no `git status`)
- [ ] Tabela de dados com **dono do dado** e **tempo de guarda**
- [ ] Seção de licenças com **nome + tipo** de cada dependência usada
- [ ] Seção de autoria: o que é da equipe, o que veio de IA (com revisão humana), o que veio de terceiros
- [ ] Seção de consentimento: o que será publicado e quem autorizou
- [ ] **5 minutos de aula aberta**: o aluno apresenta a política e a turma faz perguntas
- [ ] Commit com `docs: add security and ethics policy to the project`

### Fase 5 — Mostra (5 min)

**Aula aberta.** Três duplas apresentam a política (1 minuto cada) e a turma pergunta
*"onde está o risco que vocês aceitaram?"*.

O professor fecha lendo em voz alta as regras de
`laboratorio-tech-social/docs/seguranca-criancas.md`: sem expor dados de alunos, sem
comunicação por canal privado, com autorização por escrito do responsável para
publicar imagem ou vídeo de menores.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Política de segurança | 8 seções preenchidas, sem "TODO" |
| Dados e privacidade | Nenhum dado real de aluno, nenhum contato direto; tabela com dono e prazo |
| Segredos no Git | `.env` ignorado — verificado com `git status` |
| LGPD | Aluno explica que é titular dos próprios dados e cita 2 direitos |
| Os 4 pilares | Aluno dá um exemplo de cada pilar **no projeto da turma** |
| Ética | 1 dilema com argumento dos dois lados + a régua de decisão |
| Licença e autoria | Dependências com licença nomeada; uso de IA declarado |
| Aula aberta | 3 perguntas respondidas com honestidade (inclusive o que a equipe **não** vai fazer) |
| Pergunta de saída | "Você tem 15 anos e um app que pede nome e telefone. O que você faz?" |

**Pergunta de escrita:**
> "Você está terminando o projeto final. Um colega sugere colocar no `README` o nome
> completo, o telefone e a escola de cada membro da equipe, 'para o avaliador saber com
> quem falar'. O repositório é público e vai ficar no GitHub para sempre. O que você
> faz — e por quê?"
> **Resposta:** Não publico, e por três motivos que vêm da mesma regra.
> **(1) É dado pessoal de menor.** Com 13–17 anos eu sou a titular dos meus dados; a
> LGPD e as regras do projeto exigem consentimento do responsável e coleta mínima —
> nome completo, telefone e escola **não são necessários** para o avaliador entender
> o projeto. **(2) Não tem como reverter.** O GitHub é público e um commit é
> praticamente permanente: apagar o arquivo depois não apaga o histórico, e o buscador
> do Google já indexou. **(3) O risco é concreto.** Telefone e escola juntos num
> repositório facilitam golpe e expõem um adolescente de verdade. O caminho correto:
> identificação neutra (apelido do projeto, ou nome social, se a pessoa quiser),
> dados de contato **fora do repositório**, combinados direto com o professor; e, se a
> equipe realmente quiser publicar dados de contato, apenas com **autorização por
> escrito do responsável** — lembrando que "comunicar-se com menores por canais
> privados" é vedado pelas regras do próprio projeto.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `pensamento_computacional/13_ciberseguranca/exercicio_01_senhas.txt` | Classificar 10 senhas + gerenciador de senhas |
| `pensamento_computacional/13_ciberseguranca/exercicio_02_phishing.txt` | Identificar e-mails e sites falsos |
| `pensamento_computacional/13_ciberseguranca/exercicio_03_golpes.txt` | Reconhecer golpes comuns |
| `pensamento_computacional/13_ciberseguranca/exercicio_04_boas_praticas.txt` | Checklist de segurança |
| `pensamento_computacional/13_ciberseguranca/exercicio_05_criptografia.txt` | Como a criptografia funciona |
| `pensamento_computacional/13_ciberseguranca/exercicio_06_simulacao.txt` | Pense como um hacker (3 cenários) |
| `pensamento_computacional/15_etica_sociedade/exercicio_01_dilemas.txt` | 4 dilemas éticos para debate |
| `pensamento_computacional/15_etica_sociedade/exercicio_02_privacidade.txt` | Seus dados |
| `pensamento_computacional/15_etica_sociedade/exercicio_03_ia_emprego.txt` | IA e o futuro do trabalho |
| `pensamento_computacional/15_etica_sociedade/exercicio_04_desigualdade.txt` | Desigualdade digital |
| `pensamento_computacional/15_etica_sociedade/exercicio_05_saude.txt` | Tecnologia e saúde mental |
| `pensamento_computacional/15_etica_sociedade/exercicio_06_manifesto.txt` | Manifesto de 1 página (entregável pessoal) |
| `laboratorio-tech-social/docs/seguranca-criancas.md` | **As 5 regras obrigatórias do projeto** — ler antes da aula |
| `laboratorio-tech-social/inscricao/index.html` | Formulário real com consentimento LGPD/ECA do responsável |
| `laboratorio-tech-social/inscricao/README.md` | Coleta mínima; dados de menores não vão para marketing |
| `laboratorio-tech-social/.gitignore` | `.env` já ignorado — modelo para o projeto da turma |
| `laboratorio-tech-social/site/exercicios/quiz-ciberseguranca.html` | Quiz de Cidadania Digital com gabarito |
| `laboratorio-tech-social/site/exercicios/gerador-senhas.html` | Gerador de senhas (copia e cola) |
| `laboratorio-tech-social/site/exercicios/verdadeiro-falso.html` | Verdadeiro/falso (inclui LGPD) |
| `laboratorio-tech-social/site/exercicios/quiz-criancas.html` | Quiz da faixa 8–12 (para o professor preparar) |
| `laboratorio-tech-social/site/trilhas/criancas/05-cidadania.html` | Aula de cidadania digital (8–12): LGPD em linguagem simples |
| `o-despertar-qa/src/pages/` | Páginas do site de QA, entre elas `testes de segurança .jrmxa.js` |
| `o-despertar-qa/.gitignore` | Ignora `node_modules/`, `.vscode/`, `.idea/` |
| `questionario/index.html` | Modelo de página de perguntas **com gabarito embutido** |
| `questionario/Guia da Questões/sumário.md` | Índice dos guias de estudo — modelo de índice do material |
| `questionario/.gitignore` | `.gitignore` real: ignora artefatos de build, `*.pfx`, `*.publishsettings` |
| `CyberSec-_Crosswords/README.md` | Repositório com **só um README** — exercício real de primeira contribuição open source |

---

## 🏠 Para casa

1. Escrever a **versão final** da política de segurança (2 páginas) e colocar no
   repositório do projeto, em `docs/politica-de-seguranca.md`.
2. Ler `pensamento_computacional/15_etica_sociedade/exercicio_06_manifesto.txt` e
   responder às 6 perguntas (1 página). Trazer para a aula 13 (projeto final).
3. Ativar **2FA** em pelo menos 2 contas (e-mail e GitHub) e escrever no README
   **quais** contas têm 2FA — sem escrever código, senha ou segredo em lugar nenhum.
4. Auditar o repositório do projeto: rodar `git log -p` procurando string de chave ou
   segredo. Se encontrar, **rotacionar** a chave e avisar o professor.

---

## 🔗 Próximo módulo

[B12 — Inglês Técnico](12-ingles-tecnico.md)

# B7 — Git e GitHub (13–17 anos)

**Duração:** 90 min · **Aula 7 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Explicar o ciclo **working tree → staging area → repositório → remote** e usar `git status`, `git add`, `git commit`, `git log` e `git diff`.
2. Versionar o site da aula anterior com **10 commits** descritivos no padrão `tipo: descrição` (`feat`, `fix`, `docs`, `test`, `refactor`, `chore`).
3. Criar **branches** (`git branch`, `git switch`, `git merge`) e **resolver um conflito de merge** na prática.
4. Conectar o repositório local ao **GitHub** (`git remote`, `git push`, `git pull`) e publicar o site com **GitHub Pages**.
5. Proteger o projeto: **nunca commitar senha ou chave** — usar `.gitignore` e variáveis de ambiente.

**Objetivo secundário:** Escrever um `README.md` que explique o que o projeto faz e como rodar, em menos de um minuto de leitura.

---

## 📚 Fontes no repositório

`git-github-iniciantes/` — **15 módulos × 6 exercícios = 90 arquivos `.txt`**, cada um com bloco **"Saída esperada"** e **"Verificação"**:

| Módulo | Conteúdo | Exercícios |
|---|---|---|
| `01_o_que_e_git` | Conceitos, instalação, `git config`, identidades, editor padrão | 6 |
| `02_primeiro_repositorio` | `git init`, `git add`, `git commit`, `git status`, `git log` | 6 |
| `03_trabalhando_com_mudancas` | `git diff`, `git stash`, `git restore`, desfazer commits | 6 |
| `04_branches` | Criar, trocar, `git merge`, **conflitos** | 6 |
| `05_remotes_e_push` | `origin`, `git remote`, `git push`, `git pull`, `git fetch` | 6 |
| `06_github` | Conta, repositórios, **README**, chaves SSH | 6 |
| `07_pull_requests` | Fork, branch, **PR**, **code review** | 6 |
| `08_issues_e_projetos` | Issues, labels, milestones, project board | 6 |
| `09_github_pages` | Criar site, ativar Pages, deploy, domínio próprio | 6 |
| `10_git_avancado` | `rebase`, `cherry-pick`, tags, `bisect` | 6 |
| `11_trabalho_em_equipe` | Fluxo da equipe, estratégia de branches, `CODEOWNERS` | 6 |
| `12_ci_cd_basico` | GitHub Actions, workflows, automação | 6 |
| `13_open_source` | Contribuir, `CONTRIBUTING.md`, licenças | 6 |
| `14_ferramentas` | VS Code, GitHub Desktop, GitHub CLI | 6 |
| `15_projeto_pratico` | Criar repo, branches, CI, publicar e documentar | 6 |

**Checklist do projeto final do próprio repo** (modelo para a sua entrega):
`git-github-iniciantes/15_projeto_pratico/README.md` — README profissional com badges, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `LICENSE`, templates de issue e de PR, CI, **3 ou mais commits descritivos**, branch `develop`, tags e contribuições reais.

**Trilha web, slides e referência real:**
`laboratorio-tech-social/site/index.html` (site do laboratório, publicado no GitHub Pages) ·
`laboratorio-tech-social/.github/workflows/pages.yml` (workflow real que publica o site a cada `push` na `main`) ·
`laboratorio-tech-social/CONTRIBUTING.md` (guia de contribuição real do repositório) ·
`laboratorio-tech-social/site/trilhas/adolescentes/02-web.html` (trilha da aula 05, que é o site que você vai publicar) ·
`laboratorio-tech-social/materiais/slides/aula-teens-02-web.html`

**Links oficiais:**
[github.com](https://github.com/) · [Criar conta no GitHub](https://github.com/signup) ·
[GitHub Pages](https://pages.github.com/) · [Pro Git em português](https://git-scm.com/book/pt-br) ·
[GitHub Desktop](https://desktop.github.com/) (para quem prefere os botões aos comandos)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Working tree** | "A pasta que você abre no editor: onde o código vive **agora**." |
| **Staging area** | "A **próxima** foto. O que você escolheu para registrar." |
| **Repositório (`.git`)** | "O histórico completo: todas as fotos, em ordem." |
| **Remote (`origin`)** | "A cópia do histórico na nuvem (o GitHub)." |
| **Commit** | "Uma **fotografia** com autor e data. Não se reescreve." |
| **`git status`** | "A pergunta mais útil do Git: *o que mudou?*" |
| **`git diff`** | "O **antes** e o **depois**, linha por linha." |
| **Branch** | "Uma **linha do tempo paralela** de trabalho." |
| **Merge** | "Juntar duas linhas do tempo." |
| **Conflito** | "As duas linhas mexeram na mesma coisa. Só um humano decide." |
| **Push / Pull** | "Push = mandar. Pull = buscar." |
| **Pull Request** | "Pedir **revisão** antes de entrar na `main`." |
| **`.gitignore`** | "A lista do que **nunca** entra no histórico." |
| **Segredo (secret)** | "Senha, token, chave: **nunca** no Git. Uma vez enviado, vaza para sempre." |
| **README** | "A **primeira** página do seu repositório: o cara lê antes do código." |
| **GitHub Pages** | "Site grátis publicado direto do repositório." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Vocês já editaram um vídeo, montaram um robô, inventaram um jogo no Scratch — e na primeira vez que algo quebrou, tudo sumiu. Isso acontece porque **ninguém guardou o histórico**. Git é a máquina do tempo do programador: você não apaga o erro, você **commita** o erro e depois escreve o conserto em cima."*

**Demonstração ao vivo (6 min):** num repositório de exemplo, rode e comente:
```bash
git log --oneline --graph --all
git diff HEAD~1 HEAD
```
Depois mostre que dá para **voltar**:
```bash
git switch HEAD~1     # "volta no tempo" para o commit anterior
git switch -          # volta para onde você estava
```

Feche: *"Cada commit é uma foto datada. Um mês depois, quando algo quebrar, você responde 'quando isso começou?' olhando as fotos."*

**A regra da sala (já vale na trilha):** *"Commit ou não existe."* Quem só tem o código no PC e não tem histórico vai ter dificuldade na avaliação do módulo — está no plano da trilha.

### Fase 2 — Exploração (25 min)

**Parte 1 — As três áreas (7 min).** Desenhe no quadro:

```
   working tree            staging area             repositório (.git)
   (seus arquivos)  git add     (index)    git commit     (histórico)
        │                                                 │
        └───────────────── git push ──────────────────────┘
                             (remote: GitHub)
```

| Comando | O que faz |
|---|---|
| `git init` | Cria o repositório local (pasta `.git/`) |
| `git status` | Mostra o estado: o que está **untracked**, o que está **staged**, o que foi **modificado** |
| `git add .` | Manda as mudanças para o *staging* |
| `git commit -m "..."` | Grava a "foto" no histórico |
| `git log --oneline` | Lista os commits, um por linha |
| `git diff` | Mostra as mudanças **não** preparadas |
| `git diff --staged` | Mostra as mudanças **já** preparadas |

**Parte 2 — A mensagem de commit no padrão `tipo: descrição` (4 min).**

| Tipo | Quando usar | Exemplo |
|---|---|---|
| `feat` | Funcionalidade nova | `feat: adiciona formulário de contato` |
| `fix` | Correção de bug | `fix: corrige validação de e-mail inválido` |
| `docs` | Só documentação | `docs: explica como rodar o projeto` |
| `test` | Só testes | `test: cobre consulta de pedidos pendentes` |
| `refactor` | Código reorganizado, sem mudar o comportamento | `refactor: extrai a query do total para uma função` |
| `chore` | Manutenção (config, dependências) | `chore: adiciona .gitignore` |

Três regras: **imperativo** ("adiciona", não "adicionado"), **uma linha curta** (até ~72 caracteres) e **explique o porquê**, não só o quê. O repo reforça isso em `git-github-iniciantes/02_primeiro_repositorio/exercicios/04_mensagens_commit.txt`.

**Parte 3 — Branches e merge (5 min).**

```bash
git branch                       # lista as branches locais
git branch -a                    # lista as locais e as remotas
git switch -c feature/cadastro   # cria a branch e já entra nela
git switch main                  # volta para a main
git merge feature/cadastro       # junta a branch na main
```

O diagrama do repo (`git-github-iniciantes/04_branches/README.md`):

```
main:     A --- B --- C --- D
                       \
feature:                E --- F
```

**Parte 4 — Conflito de merge resolvido ao vivo (5 min).** Digite no terminal, junto com a turma:

```bash
$ git init
$ git config user.name "Seu Nome"        # configure uma vez só, antes do primeiro commit
$ git config user.email "seu@email.com"
$ echo "Linha 1" > config.txt
$ git add . && git commit -m "chore: configuração inicial"
$ git switch -c feature/tema-escuro
$ echo "Tema: escuro" > config.txt
$ git commit -am "feat: aplica tema escuro"
$ git switch main
$ echo "Tema: claro" > config.txt
$ git commit -am "feat: aplica tema claro"
$ git merge feature/tema-escuro
Auto-merging config.txt
CONFLICT (content): Merge conflict in config.txt
Automatic merge failed; fix conflicts and then commit the result.
```

O arquivo ficou assim:

```
<<<<<<< HEAD
Tema: claro
=======
Tema: escuro
>>>>>>> feature/tema-escuro
```

Explique: `<<<<<<< HEAD` é a **sua** versão, `=======` separa, `>>>>>>> branch` é a **outra**. O Git não escolhe por você — ele **não sabe** qual texto faz sentido.

Resolva (escolhendo uma e removendo os marcadores):

```
Tema: claro
```

```bash
$ git add config.txt
$ git commit -m "merge: resolve conflito de tema no config.txt"
$ git log --oneline --graph
```

E diga a saída de emergência: `git merge --abort` volta atrás e desfaz o merge.

> Se o seu `git init` criou a branch `master` em vez de `main`, rode `git branch -m master main` **uma vez** e siga com `main` — é o nome usado nesta aula e no repositório do curso.

**Parte 5 — Remoto, push, pull e GitHub Pages (4 min).**

```bash
git remote -v                                              # lista os remotos e as URLs
git remote add origin https://github.com/SEU-USUARIO/MEU-PROJETO.git
git push -u origin main                                    # envia e cria o "tracking"
git pull                                                   # busca e mescla
```

No GitHub: **Settings → Pages → Source: "Deploy from a branch" → branch `main`, pasta `/ (root)`**. O site fica em `https://SEU-USUARIO.github.io/MEU-PROJETO`. Mostre o exemplo real do laboratório: `laboratorio-tech-social/.github/workflows/pages.yml` faz o deploy automático a cada `push` na `main`, com a pasta `site/` como origem.

### Fase 3 — Mão na massa (35 min)

**Atividade A — Repositório + 10 commits (13 min).**
Pegue o site da aula 05 (B5) e versione:

```bash
mkdir projeto-da-turma && cd projeto-da-turma
git init
git config user.name "Seu Nome"
git config user.email "seu@email.com"
```

Antes de tudo, crie o `.gitignore`:

```gitignore
# Dependências e build
node_modules/
dist/

# Banco de dados local da aula 06
*.db
*.sqlite3

# Segredos: NUNCA versionar
.env
*.pem
*.key

# Sistema operacional e editor
.DS_Store
Thumbs.db
.vscode/
```

Agora faça **10 commits pequenos**, um de cada vez, no padrão `tipo: descrição`:

| # | Mensagem do commit | O que entra nele |
|---|---|---|
| 1 | `chore: adiciona .gitignore` | o `.gitignore` |
| 2 | `chore: estrutura inicial de pastas` | `src/`, `docs/`, `data/` |
| 3 | `feat: adiciona a página inicial` | `index.html` |
| 4 | `feat: adiciona o CSS responsivo` | `styles.css` |
| 5 | `feat: cria o script do menu e do formulário` | `script.js` |
| 6 | `fix: corrige o alinhamento dos cards no celular` | ajuste de CSS |
| 7 | `docs: escreve o README com o objetivo do projeto` | `README.md` |
| 8 | `test: adiciona checklist dos requisitos da aula` | `docs/checklist.md` |
| 9 | `refactor: separa o CSS por componentes` | `css/` |
| 10 | `chore: prepara a publicação no GitHub Pages` | `.nojekyll` ou ajuste final |

Regra da atividade: **um commit = uma ideia**. Nada de `git add . && git commit -m "tudo"` no final. Entre commits, rode `git status` e `git diff` para ver o que está entrando.

**Atividade B — Branch + conflito (10 min).**
1. `git switch -c feature/cadastro`
2. Mude uma linha do `styles.css` e faça o commit.
3. `git switch main` e mude **a mesma linha** com outro valor; commit.
4. `git merge feature/cadastro` → conflito.
5. Resolva o conflito **combinando** as duas versões (não escolhendo uma), remova os marcadores, `git add` e `git commit`.
6. `git log --oneline --graph` — mostre as duas linhas de tempo se juntando.

**Atividade C — Push e GitHub Pages (8 min).**
1. Crie o repositório no [github.com](https://github.com/) (ou no [GitHub Desktop](https://desktop.github.com/)).
2. `git remote add origin ...` + `git push -u origin main`.
3. Ative o Pages (**Settings → Pages**).
4. Abra a URL `https://SEU-USUARIO.github.io/MEU-PROJETO` no navegador e cole no `README.md`.
5. Faça um commit novo (`docs: adiciona o link do site publicado`) e veja o site se atualizar sozinho.

**Atividade D — 3 exercícios do repo (4 min).**
- `git-github-iniciantes/02_primeiro_repositorio/exercicios/04_mensagens_commit.txt` — mensagens de commit
- `git-github-iniciantes/04_branches/exercicios/04_merge_com_conflito.txt` — conflito de merge (o exercício já traz o cenário e o arquivo `conflito_resolvido.txt` para preencher)
- `git-github-iniciantes/09_github_pages/exercicios/02_ativar_github_pages.txt` — ativar o Pages

Cada arquivo traz o bloco **"Verificação"** com as perguntas de conferência.

### Fase 4 — Projeto (15 min)

**Desafio: "Repositório profissional do projeto da turma"**

Entregáveis:
- Repositório local com **10 ou mais commits** no padrão `tipo: descrição`
- `.gitignore` no padrão da Atividade A
- `README.md` com: nome, slogan, o que o projeto faz, **como rodar**, tecnologias, licença e o **link do site no Pages**
- 1 branch `feature/...` criada, mesclada e resolvida
- 1 tag `v1.0` marcando a primeira versão
- O site publicado no GitHub Pages

**Critério de pronto:**
- [ ] `git status` responde **"nothing to commit, working tree clean"**
- [ ] `git log --oneline` mostra **10 ou mais commits**, todos no padrão `tipo: descrição` (nenhum "asdfgh", "update" ou "mudanças")
- [ ] `.gitignore` existe e cobre pelo menos `node_modules/`, `*.db` e `.env`
- [ ] `README.md` tem objetivo, como rodar, tecnologias e o link do Pages
- [ ] O site publicado abre e é idêntico ao que está na pasta local
- [ ] Existe 1 branch `feature/...` **já mesclada** e 1 tag `v1.0`
- [ ] **Nenhum segredo no histórico.** Confira com:

```bash
# Lista commits que tocaram arquivos de segredo — não pode devolver nada
git log --all --full-history -- "*.env" "*.pem" "*.key"
```

- [ ] Nenhum dado pessoal real de aluno no repositório (ver `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §9)

### Fase 5 — Mostra (5 min)

Cada dupla abre a **URL do Pages** no projetor e mostra o próprio `git log --oneline`. A turma vota em três categorias: **melhor histórico**, **melhor README**, **melhor site**.

**Pergunta de saída:** "Qual a diferença entre `git commit -am "..."` e `git add .` + `git commit`? E em qual dos dois um arquivo que não devia no repositório pode acabar entrando sem você perceber?"

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Histórico Git | 10+ commits, todos no padrão `tipo: descrição`, nenhum commit "vazio" |
| `.gitignore` e segurança | Segredos fora do histórico; `git status` limpo; `git log --all --full-history -- "*.env"` vazio |
| `README.md` | Objetivo, como rodar, tecnologias e link do Pages |
| Branch e merge | 1 `feature/` criada, mesclada e com conflito resolvido |
| GitHub Pages | Site publicado no ar e igual ao local |
| Pull request e code review | Aluno sabe dizer o que é um PR e consegue revisar o PR de um colega |

**Pergunta de escrita:**
> "Você criou um arquivo `.env` com `DATABASE_URL=postgres://usuario:senha123@localhost:5432`
> e commitou sem querer. Depois fez `push` e a senha foi para o GitHub. O que você faz agora?"
> **Resposta:** Não dá para "apagar" do histórico com um commit novo — o objeto antigo continua lá e
> qualquer pessoa pode lê-lo. O caminho correto é: **(1) rotacionar a credencial agora** (trocar a
> senha/invalidate o token no serviço) — é o passo mais urgente, porque enquanto o histórico não for
> reescrito, a senha está exposta; **(2)** `git rm --cached .env` e adicionar `.env` ao `.gitignore`;
> **(3)** reescrever o histórico (`git filter-repo`/BFG ou `git rebase`) e reenviar para um repositório
> limpo; **(4)** avisar o professor e a equipe. A lição: **segredo nunca entra no Git** — use
> variáveis de ambiente e versione apenas um `.env.example` com os **nomes** das chaves e valores
> fictícios.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `git-github-iniciantes/03_trabalhando_com_mudancas/` | `git diff`, `git stash`, `git restore` |
| `git-github-iniciantes/05_remotes_e_push/` | `git remote`, `push`, `pull`, `fetch` |
| `git-github-iniciantes/06_github/exercicios/02_escrever_readme.txt` | Escrever um README profissional |
| `git-github-iniciantes/06_github/exercicios/03_configurar_ssh.txt` | Chave SSH para parar de digitar a senha |
| `git-github-iniciantes/07_pull_requests/` | Fork, PR e **code review** |
| `git-github-iniciantes/08_issues_e_projetos/` | Issues, labels, milestones e project board |
| `git-github-iniciantes/10_git_avancado/` | `rebase`, `cherry-pick`, tags e `bisect` |
| `git-github-iniciantes/11_trabalho_em_equipe/` | Fluxo de equipe, estratégia de branches, `CODEOWNERS` |
| `git-github-iniciantes/12_ci_cd_basico/` | GitHub Actions (checks automáticos em cada PR) |
| `git-github-iniciantes/13_open_source/` | `CONTRIBUTING.md` e licenças |
| `git-github-iniciantes/14_ferramentas/exercicios/02_github_desktop.txt` | Fazer tudo sem terminal |
| `git-github-iniciantes/15_projeto_pratico/` | Checklist do projeto final profissional |
| `laboratorio-tech-social/CONTRIBUTING.md` | Exemplo real de guia de contribuição de um repositório aberto |

---

## 🏠 Para casa

1. Publique o site da aula 05 (B5) no GitHub Pages e cole a URL no `README.md`.
2. Escreva o `README.md` do projeto **em inglês** — a aula 12 ([B12 — Inglês Técnico](12-ingles-tecnico.md)) vai reutilizar exatamente esse texto.
3. Abra **1 Pull Request** de uma correção real (no repositório `laboratorio-tech-social` ou no repositório da turma), com título no padrão `tipo: descrição` e uma descrição que diga o que mudou e por quê.
4. (Opcional) Leia o [Pro Git em português](https://git-scm.com/book/pt-br), capítulos 2 e 3 — é o livro oficial, gratuito, escrito pelo autor do Git.

---

## 🔗 Próximo módulo

[B8 — QA: Teste de Software](08-qa-teste-de-software.md)

# Módulo 3 — Git e GitHub profissional (18+)

**Duração:** 90 min · **Aula 3 de 16**
**Pré-requisito:** Módulo 2 (Python para automatizar) ou experiência equivalente.
**Entregável:** repositório versionado + pull request revisado + site publicado no GitHub Pages.

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Explicar o fluxo profissional **branch → commit → pull request → revisão → merge** e por que ele existe.
2. Recuperar trabalho perdido com `git reflog` e desfazer um commit com `git revert` sem reescrever o histórico.
3. Publicar um site estático no **GitHub Pages** e proteger segredos com `.gitignore` e variáveis de ambiente.

**Objetivo secundário:** escrever mensagens de commit no padrão `tipo: descrição` e revisar o código de outra pessoa com comentários úteis.

---

## 📚 Fontes no repositório

| Repositório | O que usar |
|---|---|
| `git-github-iniciantes/` | 15 módulos, do primeiro repositório ao projeto prático (`15_projeto_pratico/README.md`) |
| `git-github-iniciantes/04_branches/` | Exercício real de merge com conflito (`exercicios/04_merge_com_conflito.txt`) |
| `git-github-iniciantes/06_github/` | Escrever README (`exercicios/02_escrever_readme.txt`) e configurar SSH (`03_configurar_ssh.txt`) |
| `git-github-iniciantes/09_github_pages/` | Ativar o Pages (`exercicios/02_ativar_github_pages.txt`) |
| `laboratorio-tech-social/` | `.github/workflows/pages.yml` (deploy automático) e `CONTRIBUTING.md` |
| `dio-lab-open-source/` | Exemplo de contribuição em projeto open source por fork e pull request |

**Links:**
[Pro Git em português](https://git-scm.com/book/pt-br) ·
[Documentação do GitHub](https://docs.github.com/pt) ·
[GitHub Pages](https://pages.github.com/) ·
[GitHub Desktop](https://desktop.github.com/) ·
[criar conta no GitHub](https://github.com/signup)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Working tree** | "Onde você edita; nada aqui está salvo no histórico." |
| **Staging area** | "A bandeja do próximo commit: só entra o que você escolheu." |
| **Commit** | "Uma foto do projeto com autor, data e motivo." |
| **Branch** | "Uma linha de trabalho isolada, para não misturar com o que já funciona." |
| **Pull request** | "O pedido de revisão: outra pessoa leu antes de entrar." |
| **Merge** | "Juntar duas linhas de trabalho em uma." |
| **Conflito** | "Duas pessoas mudaram a mesma linha: o Git pede que um humano decida." |
| **`reflog`** | "O diário de bordo do HEAD: quase tudo é recuperável." |
| **`revert`** | "Cria um commit novo que desfaz o anterior, sem apagar a história." |
| **Tag** | "Um marcador de versão, como `v1.0.0`." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Você já perdeu um arquivo por ter salvado `trabalho_final_v3_agoravai.docx`? O Git resolve isso — e resolve também quando o problema é outra pessoa mexendo no mesmo arquivo."*

Mostre ao vivo o `git log --oneline --graph` de um repositório real com branches e merges. Pergunte: *"Se este commit quebrou o sistema, como voltar sem apagar o trabalho dos outros?"* — anote as respostas no quadro e retome no fim.

**Demonstração (4 min):** no terminal, `git status` → `git add` → `git commit` → `git log` em um repositório de teste. Diga: *"Três áreas: onde você edita, onde você prepara e onde você registra."*

### Fase 2 — Exploração (20 min)

**Parte 1 — O fluxo profissional (8 min).**

```bash
git switch -c feature/relatorio-mensal     # cria a branch e entra nela
# ... edita os arquivos ...
git status                                 # o que mudou
git diff                                   # o que exatamente mudou
git add relatorio.py                       # prepara só o que interessa
git commit -m "feat: gera relatório mensal em CSV"
git push -u origin feature/relatorio-mensal
```

No GitHub, abra o pull request, peça revisão e faça o **merge** (preferencialmente *squash*: um commit limpo na branch principal).

**Parte 2 — Mensagem de commit (4 min).**
Padrão `tipo: descrição no imperativo`:

| Tipo | Quando usar |
|---|---|
| `feat` | nova funcionalidade |
| `fix` | correção de defeito |
| `docs` | apenas documentação |
| `test` | testes |
| `refactor` | reorganização sem mudar comportamento |
| `chore` | manutenção (dependências, configuração) |

Exemplo ruim: `alterações`. Exemplo bom: `fix: corrige soma de valores negativos no CSV`.

**Parte 3 — Desfazer com segurança (4 min).**

```bash
git revert <hash>        # cria um commit que desfaz outro (seguro em equipe)
git reflog               # lista para onde o HEAD já apontou
git reset --soft HEAD~1  # desfaz o commit e mantém as mudanças preparadas (só local)
```

Regra: **`reset` reescreve história — nunca em branch compartilhada. `revert` é público e seguro.**

**Parte 4 — Segredos e `.gitignore` (4 min).**

```gitignore
.env
*.key
__pycache__/
.venv/
```

```python
import os
chave = os.environ.get("CHAVE_API")   # nunca escreva a chave no código
```

Se um segredo já foi commitado, **revogue a chave** — apagar o arquivo não apaga o histórico.

### Fase 3 — Mão na massa (40 min)

**Atividade A — Repositório profissional (20 min).**
1. Crie um repositório no GitHub com README, `.gitignore` de Python e licença MIT.
2. Clone, crie a branch `feature/primeira-melhoria`, faça **3 commits pequenos** com mensagens no padrão.
3. Abra um pull request descrevendo: o que mudou, por que e como testar.
4. Peça a um colega para revisar; aplique ao menos **uma sugestão** da revisão.

**Atividade B — Conflito de merge (10 min).**
Siga `git-github-iniciantes/04_branches/exercicios/04_merge_com_conflito.txt`: duas branches alteram a mesma linha, o merge gera conflito, você resolve manualmente e conclui o merge. Registre no README qual foi a decisão.

**Atividade C — Recuperação (10 min).**
Apague um commit com `git reset --hard HEAD~1`, recupere com `git reflog` e `git reset --hard <hash>`. Depois simule um erro já publicado e corrija com `git revert`.

### Fase 4 — Projeto (15 min)

**Desafio: "Meu projeto no ar"**
Publique no **GitHub Pages** uma página do projeto do Módulo 2 (documentação da automação, com print, instruções de uso e limitações).

**Critério de pronto:**
- [ ] Repositório público com README completo (o que é, como rodar, como testar, licença)
- [ ] Histórico com pelo menos 10 commits pequenos e mensagens no padrão
- [ ] Uma branch e um pull request revisado
- [ ] `.gitignore` impede o envio de `.env` e de pastas geradas
- [ ] Site acessível em `https://usuario.github.io/repositorio/`
- [ ] Nenhuma chave, senha ou dado pessoal no histórico

### Fase 5 — Mostra (5 min)

Cada aluno mostra **um commit** e **um pull request** no projetor. A turma responde: *a mensagem explica o motivo? a revisão foi específica ou genérica?*

**Pergunta de saída:** *"Por que `git revert` é preferível a `git reset` em uma branch compartilhada?"*

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Repositório | README completo, licença e `.gitignore` corretos |
| Histórico | 10 commits atômicos com mensagens no padrão |
| Pull request | Descrição clara e revisão aplicada |
| Conflito | Resolvido manualmente e explicado no README |
| Pages | Site público funcionando |
| Segurança | Nenhum segredo no histórico |

**Pergunta de escrita:**
> "Você commitou sem querer um arquivo `.env` com uma chave de API. Apagar o arquivo e commitar de novo resolve? Justifique."
> **Resposta:** Não. O conteúdo continua no histórico (qualquer pessoa pode recuperá-lo). O correto é **revogar/rotacionar a chave**, remover o arquivo do rastreamento (`git rm --cached .env`), adicionar ao `.gitignore` e, se necessário, limpar o histórico com ferramentas próprias — avisando a equipe.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `git-github-iniciantes/02_primeiro_repositorio/exercicios/04_mensagens_commit.txt` | Boas mensagens de commit |
| `git-github-iniciantes/06_github/exercicios/03_configurar_ssh.txt` | Chave SSH |
| `git-github-iniciantes/09_github_pages/exercicios/02_ativar_github_pages.txt` | Publicação |
| `git-github-iniciantes/14_ferramentas/exercicios/02_github_desktop.txt` | Interface gráfica |
| `laboratorio-tech-social/.github/workflows/pages.yml` | Deploy automático a cada push |

---

## 🏠 Para casa

Adicione **tags de versão** (`v0.1.0`, `v1.0.0`) e uma release com notas do que mudou. Depois, contribua com **um pull request** em um projeto open source real (documentação ou correção pequena), seguindo o `CONTRIBUTING.md` do projeto.

---

## 🔗 Próximo módulo

[Módulo 4 — Dados e Planilhas](04-dados-e-planilhas.md)

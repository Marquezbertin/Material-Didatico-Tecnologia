# Módulo 1 — Linha de Comando e Automação do Sistema (18+)

**Duração:** 90 min · **Aula 1 de 16** (módulo em 2 aulas: 01 e 02)

**Entregável do módulo:** **script de shell + 1 rotina automatizada com cron**.

---

## 🎯 Objetivo

Ao final do módulo, o aluno será capaz de:

1. Explicar a diferença entre **terminal** e **interface gráfica**, e dizer quando o
   terminal é melhor (e quando é pior).
2. Navegar no sistema de arquivos com `pwd`, `ls`, `cd`, `mkdir`, `cp`, `mv` e `rm`,
   entendendo o que cada comando **realmente** faz.
3. Aplicar o **princípio do menor privilégio** ao ler permissões (`chmod`, `chown`) e ao
   criar usuário/senha de script.
4. Encadear comandos com **pipes** e **redirecionamento** (`>`, `>>`, `<`, `2>`, `2>&1`).
5. Extrair informação de arquivos de texto com `grep`, `find`, `sort`, `uniq`, `head`,
   `tail` e `wc`.
6. Escrever um **script de shell** com variáveis, teste condicional, laço e **código de
   saída** (`exit 0` / `exit 1`), e rodá-lo com `bash`.
7. Agendar a execução com **cron** (e conhecer o **systemd timer** como alternativa).
8. Diagnosticar problemas lendo **logs** e o **código de saída** do comando.
9. **Versionar o script** no Git — porque script sem histórico é script que ninguém
   consegue corrigir.

**Objetivo secundário:** Escrever, em 1 frase, por que `rm -rf /` nunca deve ser digitado
sem pensar.

---

## 📚 Fontes no repositório

A trilha adulta **não tem um repositório de shell script** — e isso é proposital: os
comandos desta aula são **do sistema operacional**, não do material. O que o repositório
oferece são **automações reais** para ler a estrutura e serve de referência:

| Fonte real | O que mostra |
|---|---|
| `manual-qa-completo/Makefile` | Automação real com **alvos nomeados** (`scripts`, `test-api`, `test-ui`, `check-mermaid`, `all`), cada um rodando comandos `python`/`pytest` |
| `manual-qa-completo/run_all.py` | O mesmo "make all" em Python: executa uma **lista de scripts**, conta falhas e devolve **código de saída** (`return 1 if failures else 0`) |
| `Central-de-noticias/.github/workflows/update-news.yml` | **Cron real** em YAML (dois agendamentos, guarda "já atualizou hoje?", `git add` condicional com `|| true`, `git diff --cached --quiet`) |
| `qa-automation-framework/` | Estrutura de pastas profissional: `config/`, `core/`, `pages/`, `tests/`, `utils/`, `requirements.txt`, `pyproject.toml` |
| `laboratorio-tech-social/site/exercicios/` | 41 páginas de laboratório interativo para treinar fora da aula |

> **A regra do módulo:** nada de "digite e acredite". Todo comando é executado **na frente
> da turma**, com saída real. Se o comando não roda, corrige-se na hora — e o aluno vê a
> correção.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Terminal** | "A janela de texto que conversa com o sistema. O clique é uma **ótima** forma de pedir — mas é lenta e não se automatiza." |
| **Interface gráfica** | "O botão já faz a ordem por você. O terminal faz a ordem **na sua frente**." |
| **Prompt** | "A linha que mostra onde você está e espera o comando. `$` = usuário comum, `#` = root." |
| **`pwd` / `ls` / `cd`** | "Onde estou, o que tem aqui, ir para lá." |
| **Caminho absoluto vs relativo** | "`/home/ana` é **endereço**; `../planilhas` é **referência**." |
| **`cp` / `mv` / `rm`** | "Copiar, mover, apagar. Na ordem dessa força: `cp` é reversível, `rm` **não** é." |
| **Permissão (`rwx`)** | "`r` ler, `w` escrever, `x` executar. O **dono**, o **grupo** e os **outros**." |
| **Menor privilégio** | "Dê a **menor** permissão que faz o trabalho — e só a ela." |
| **Pipe (`|`)** | "A saída de um comando vira **entrada** do próximo. Uma linha, muitas ferramentas." |
| **Redirecionamento (`>`)** | "`>` **sobrescreve**. `>>` **acrescenta**. `2>` manda o erro para outro lugar." |
| **`grep` / `find`** | "`grep` procura **dentro** do arquivo; `find` procura **o arquivo**." |
| **`sort` / `uniq` / `wc`** | "Ordenar, contar repetidos, contar linhas." |
| **Variável de shell** | "`NOME=valor` cria. `$NOME` usa. Sem `$` é só texto." |
| **Código de saída** | "O número que o comando deixa para o próximo: `0` = deu certo, `!= 0` = deu errado." |
| **`set -euo pipefail`** | "Pare na primeira falha, erro não declarado é erro, e pipe que quebra é falha." |
| **cron** | "O despertador do sistema: roda este comando às 6h de todo dia." |
| **systemd timer** | "O cron com mais controle: reinício, dependência, log próprio." |
| **Log** | "O **diário** do sistema. Sem log, você adivinha." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Toda vez que você renomeia 300 arquivos, ou repara que o relatório do mês
passado foi gerado com a planilha errada, você repete o mesmo trabalho. Nenhuma dessas
tarefas precisa de um mouse. O terminal é o jeito mais rápido de(**e o único** que
automatiza) — e é o mesmo terminal que roda o deploy do site que você usa todo dia."*

**Demonstração ao vivo (6 min):** abra o terminal e rode, sem explicar nada ainda:

```bash
# 1. Onde eu estou?
pwd

# 2. O que tem aqui?
ls -la

# 3. O tamanho de cada arquivo, do maior para o menor
ls -lhS

# 4. Quantas linhas tem o arquivo de log?
wc -l /var/log/syslog
```

Depois rode, **com o mesmo resultado e sem clicar em nada**:

```bash
# A mesma informação, em uma linha só, encadeada
ls -lh | sort -k5 -h | tail -3
```

Diga: *"A segunda forma eu **escrevo**; a primeira eu **clico**. Daqui a 4 aulas você vai
escrever a segunda."*

**Demonstração do "antes e depois" (3 min):** pegue um arquivo de log fictício da pasta
do exercício e mostre o comando que encontra a informação:

```bash
grep -c "ERROR" log_exemplo.txt      # quantos erros existem
grep -n "ERROR" log_exemplo.txt      # em quais linhas
```

### Fase 2 — Exploração (25 min)

**Parte 1 — Terminal × interface gráfica (4 min).**

| | Interface gráfica | Terminal |
|---|---|---|
| Velocidade | 1 ação por clique | 1 linha faz 10 ações |
| Repetição | você repete | o **script** repete |
| Documentação | difícil de descrever | o comando **é** a documentação |
| Erro | botão desabilitado | mensagem de erro **com texto** |
| Automação | macro gravada | script versionável |

> Diga: *"A interface gráfica é um **atalho** que alguém já pensou para você. O terminal é
> a linguagem. Na aula 02 do módulo de Python, você vai ver que a automação de verdade é
> código."*

**Parte 2 — Navegação (7 min).**

```bash
pwd                 # onde estou (print working directory)
ls                  # lista o conteúdo (com cor)
ls -la              # inclui ocultos (.git, .env) e permissões
ls -lhS             # legível, ordenado por tamanho
cd ~/Documentos      # vai para a pasta
cd ..                # sobe um nível
cd -                 # volta para a pasta anterior
mkdir ~/projeto-linha-de-comando      # cria pasta
touch notas.txt                      # cria arquivo vazio
cp notas.txt copia-notas.txt          # copia
mv copia-notas.txt documento-final.txt # move (ou renomeia)
rm documento-final.txt                # apaga
rm -r pasta-antiga                    # apaga pasta e conteúdo
```

**As 3 regras de segurança que valem para a vida toda:**

1. `rm` **não** tem "lixeira". Não existe como desfazer no terminal.
2. Antes de `rm -r`, rode `ls` **na mesma pasta** e leia o que vai ser apagado.
3. `rm -rf /` (com barra) apaga o sistema inteiro. **Nunca digite isso.**

> ⚠️ **Demonstre o perigo no slide, não no terminal.** Escreva `rm -rf /` num arquivo de
> texto do editor e mostre a tela. Explique que o comando existe de verdade e que
> **ninguém** digita na pressa.

**Parte 3 — Permissões e menor privilégio (6 min).**

```
-rwxr-xr--   1 ana  staff  4096  script.sh
│└┬┘└┬┘└┬┘
│ │  │  └── outros (r-- = só ler)
│ │  └───── grupo (r-x = ler e executar)
│ └──────── dono (rwx = ler, escrever, executar)
```

```bash
ls -l                       # mostra as permissões
chmod +x script.sh          # adiciona permissão de execução ao dono
chmod 644 notas.txt         # dono: rw; grupo e outros: só leitura
chmod 755 meu-programa.sh   # padrão para scripts executáveis
chown ana:ana script.sh     # muda dono e grupo (só root/administrador)
```

**Princípio do menor privilégio (a frase que fixa):** *"O script só precisa de ler o
arquivo de entrada e gravar o arquivo de saída. Ele **não** precisa de `chmod 777` nem de
`sudo`. Se você precisa de `sudo` para o script rodar, o script está errado — ou o
usuário do sistema está errado."*

**Parte 4 — Pipes e redirecionamento (5 min).**

```bash
# Pipe: a saída de um comando vira entrada do próximo
cat notas.txt | grep " urgente"

# Redirecionamento: > sobrescreve, >> acrescenta
python3 notas.py > resultado.txt     # guarda a saída no arquivo (apaga o que tinha)
python3 notas.py >> historico.txt    # acrescenta ao histórico

# Erro em outro lugar
python3 notas.py 2> erros.txt        # só o erro vai para o arquivo
python3 notas.py > saida.txt 2>&1    # saída e erro no mesmo arquivo
python3 notas.py 2>&1 | tee tela.txt # mostra na tela E grava no arquivo
```

**Parte 5 — As ferramentas de texto (3 min).**

```bash
grep -n "erro" app.log          # linha e número da linha
grep -rin "erro" app.log        # sem diferenciar maiúsculas/minúsculas
grep -c "erro" app.log          # só a contagem
grep -r "TODO" src/             # recursivo numa pasta

find . -name "*.log"            # arquivos pelo nome
find . -name "*.log" -mtime -7  # modificados nos últimos 7 dias
find . -type f -size +100M      # arquivos com mais de 100 MB

sort nomes.txt                  # ordena
sort -u nomes.txt | uniq -c    # conta repetidos, do mais comum ao menos comum
head -5 arquivo.txt             # primeiras 5 linhas
tail -5 arquivo.txt             # últimas 5 linhas
tail -f app.log                 # acompanha o log em tempo real (Ctrl+C para sair)
wc -l arquivo.txt               # conta linhas
```

> **Mostre ao vivo:** `tail -f` com um log sendo escrito por outro terminal. É o
> "grito" do administrador de sistemas.

### Fase 3 — Mão na massa (30 min)

**Atividade A — Do clique ao comando (10 min).**
Cada aluno cria a pasta de trabalho e executa, **na ordem**, registrando a saída de cada
comando no arquivo `notas-de-aula.md`:

```bash
mkdir -p ~/projeto-linha-de-comando/{dados,logs,scripts}
cd ~/projeto-linha-de-comando
printf 'urgente\nrotina\nurgente\nrelatorio\nurgente\n' > dados/tarefas.txt
ls -la
wc -l dados/tarefas.txt
grep -c "urgente" dados/tarefas.txt
sort dados/tarefas.txt | uniq -c
```

**Entregável da Atividade A:** `notas-de-aula.md` com **a saída real** de cada comando
(colada, não reescrita).

**Atividade B — Script de shell completo (20 min).**
Crie `scripts/backup-relatorio.sh`:

```bash
#!/usr/bin/env bash
# backup-relatorio.sh
# Copia os relatórios do dia para a pasta de backup com data no nome.
# Uso: bash scripts/backup-relatorio.sh

set -euo pipefail   # para na primeira falha; erro não declarado é erro; pipe quebrado é falha

DATA="$(date +%Y-%m-%d)"
ORIGEM="dados"
DESTINO="backups/${DATA}"
LOG="logs/backup-${DATA}.log"

# Função auxiliar: escreve no log e na tela
registrar() {
  echo "[$(date +%H:%M:%S)] $1" | tee -a "$LOG"
}

# Garante que a pasta de logs exista ANTES de qualquer escrita no log
mkdir -p "$(dirname "$LOG")"

# Validação: a pasta de origem precisa existir
if [ ! -d "$ORIGEM" ]; then
  registrar "ERRO: a pasta de origem '$ORIGEM' não existe."
  exit 1        # código de saída 1 = falha
fi

# Cria a pasta de destino
mkdir -p "$DESTINO"

registrar "Iniciando backup de '$ORIGEM' para '$DESTINO'"

# Laço: um arquivo por vez
CONTAGEM=0
for ARQUIVO in "$ORIGEM"/*.txt; do
  [ -e "$ARQUIVO" ] || continue          # ignora o caso de nenhum arquivo encontrado
  cp -p "$ARQUIVO" "$DESTINO/"
  CONTAGEM=$((CONTAGEM + 1))
  registrar "Copiado: $(basename "$ARQUIVO")"
done

registrar "Backup finalizado: $CONTAGEM arquivo(s)."

# Código de saída 0 = tudo certo
exit 0
```

Rode e ensine a ler o resultado:

```bash
chmod +x scripts/backup-relatorio.sh
bash scripts/backup-relatorio.sh
echo "código de saída: $?"      # 0 = sucesso
cat logs/backup-$(date +%Y-%m-%d).log
```

**Demonstre a falha de propósito** (renomeie a pasta de origem e rode de novo):
o script **para**, escreve no log e devolve **código de saída 1**. Diga: *"É assim que
o script avisa quem agendou ele. Um script que falha em silêncio é o pior tipo de
script que existe."*

**Entregável da Atividade B:** `scripts/backup-relatorio.sh` executável, com `set -euo pipefail`,
log em arquivo e **código de saída** correto nos dois cenários (sucesso e falha).

### Fase 4 — Projeto (20 min)

**Desafio: "A rotina que roda sozinha"**

Cada aluno transforma o script da Atividade B em uma rotina agendada e versionada:

**Parte 1 — Agendar com cron (10 min).**

```bash
# Abre o crontab do usuário
crontab -e
```

Linha a acrescentar (ajuste os caminhos):

```cron
# Backup dos relatórios todo dia às 6h30, com log no arquivo
30 6 * * * cd ~/projeto-linha-de-comando && bash scripts/backup-relatorio.sh >> logs/cron.log 2>&1
```

**Os 5 campos do cron, na ordem:** `minuto hora dia-do-mês mês dia-da-semana`.

| Exemplo | Quando roda |
|---|---|
| `*/5 * * * *` | a cada 5 minutos |
| `0 6 * * *` | todo dia às 6h00 |
| `30 6 * * 1-5` | de segunda a sexta, às 6h30 |
| `0 9 1 * *` | dia 1 de cada mês, às 9h |

Verifique e teste sem esperar até amanhã:

```bash
crontab -l                    # mostra o que está agendado
# TESTE: copia a linha do cron trocando o horário por "a cada minuto" e espere 1 minuto
```

> **No Windows, sem WSL:** use o **Agendador de Tarefas** do Windows para executar
> `bash.exe scripts/backup-relatorio.sh` — o script é o mesmo. Aulamos a equivalência:

| Tarefa | Linux (cron) | Windows (Agendador de Tarefas) |
|---|---|---|
| Agendar | `crontab -e` | Programador de Tarefas → Criar Tarefa |
| Testar | troque para `* * * * *` | "Executar agora" |
| Log | redirecione `>>` | campo "Argumentos" ou o próprio script |

**Alternativa: `systemd timer` (visão geral).**

Em servidores Linux modernos, o `cron` foi substituído pelo `systemd timer`, que usa os
**mesmos 5 campos** de horário, mas ganha recursos:

| Recurso | `cron` | `systemd timer` |
|---|---|---|
| Reinício automático se falhar | não | sim (`RestartSec=60s`) |
| Depender de outro serviço | não | sim (`After=`/`Requires=`) |
| Log próprio e centralizado | não (você redireciona) | sim (`journalctl -u`) |
| Aviso de falha | não | sim (`OnFailure=` para notificar) |
| Janela de manutenção ("só roda entre 2h e 5h") | não | sim (`Persistent=`, `RandomizedDelaySec=`) |

Um par de arquivos resolve (visão geral, **não** precisa saber escribir):

```ini
# /etc/systemd/system/backup-relatorio.service
[Unit]
Description=Backup dos relatórios do dia

[Service]
Type=oneshot
ExecStart=/home/ana/projeto-linha-de-comando/scripts/backup-relatorio.sh
```

```ini
# /etc/systemd/system/backup-relatorio.timer
[Unit]
Description=Roda o backup todo dia às 6h30

[Timer]
OnCalendar=*-*-* 06:30:00
Persistent=true

[Install]
WantedBy=timers.target
```

```bash
systemctl daemon-reload
systemctl enable --now backup-relatorio.timer
systemctl list-timers                    # o que está agendado
journalctl -u backup-relatorio.service  # o log do serviço
```

> **Por que isso importa na sua rotina de trabalho:** o `cron` é simples e ainda está em
> todo lugar; o `systemd timer` é o que os servidores de empresa usam. Se você vai
> automatizar algo **na empresa**, converse com a equipe de TI antes — o agendamento de
> tarefa é, em boa parte das organizações, uma tarefa **doTI**, não do usuário.

**Parte 2 — Versionar no Git (10 min).**

```bash
cd ~/projeto-linha-de-comando
git init
git config user.name "Seu Nome"
git config user.email "seu@email.com"

# .gitignore: o que NÃO entra no histórico
printf '.venv/\n__pycache__/\nlogs/*.log\nbackups/\n*.env\n' > .gitignore

git add .
git commit -m "feat: script de backup com log e código de saída"
git log --oneline
```

**Critério de pronto:**
- [ ] `scripts/backup-relatorio.sh` existe, tem `#!/usr/bin/env bash` e `set -euo pipefail`
- [ ] O script usa **variáveis** (nada de caminho repetido 5 vezes no código)
- [ ] O script tem **teste condicional** (`if`) que trata o caso de pasta ausente
- [ ] O script tem **laço** (`for`) e **contador**
- [ ] O script grava **log** em arquivo e mostra na tela (`tee`)
- [ ] O script devolve **código de saída 0** no sucesso e **1** na falha (teste os dois!)
- [ ] Existe **1 rotina com cron** (ou tarefa no Agendador do Windows) agendar o script
- [ ] Existe **README.md** com: o que o script faz, como rodar, como agendar, onde fica o log
- [ ] O script está **versionado no Git** com pelo menos 2 commits descritivos
- [ ] O `.gitignore` cobre `logs/`, `backups/` e `.env`

### Fase 5 — Mostra (5 min)

Cada aluno (ou dupla) mostra **o cron agendado** na tela e responde 2 perguntas da turma:
1. "Qual arquivo esse script mexe?"
2. "Se ele falhar amanhã às 6h30, eu descubro onde?"

> **Pergunta de saída:** "Qual a diferença entre `>` e `>>`? E por que um script que
> executa todo dia precisa obrigatoriamente de um log?"

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Script de shell | Executa sem erro, tem `set -euo pipefail`, variáveis, `if`, `for` |
| Codes de saída | `0` no sucesso e `1` na falha (testado e **mostrado** na aula) |
| Log | Arquivo de log gerado, com data/hora e mensagem por operação |
| Rotina agendada | `crontab -l` mostra a rotina; equivalente no Agendador do Windows |
| Versionamento | Repositório Git com 2+ commits descritivos e `.gitignore` |
| README | Explica o que faz, como rodar, como agendar e onde fica o log |
| Compreensão | O aluno explica o que cada comando faz **sem** ler o slide |

**Pergunta de escrita:**
> "Você agendou um backup diário às 6h30. Na quarta-feira, o log mostra que o backup
> parou de rodar no domingo. O `crontab -l` continua com a mesma linha, e o script, rodado
> na mão, funciona. O que você investigar, **nesta ordem**?"
> **Resposta:**
> 1. **Ambiente do cron.** O cron roda com um `PATH` e um `HOME` **mais pobres** que o seu
>    terminal. Quase sempre o culpado é um comando que existe no seu shell e não existe
>    para o cron (por exemplo, `python` instalado via `pyenv` ou `conda`). Solução: usar
>    caminho **absoluto** do interpretador e `set -euo pipefail` no script.
> 2. **Diretório de trabalho.** O cron inicia em `$HOME`, não no diretório do script. Por
>    isso o caminho relativo (`dados/`) quebra. Solução: `cd ~/projeto && bash ...` na
>    linha do cron, ou `cd "$(dirname "$0")"` dentro do script.
> 3. **Permissões.** O arquivo pode ter `chmod 600` e o cron roda como outro usuário, ou o
>    destino não tem permissão de escrita. Cheque com `ls -ld` da pasta de destino.
> 4. **Disco cheio.** `df -h`. Backup que enche o disco para e o próximo erro é "no space
>    left on device" — leia o log, não o script.
> 5. **Código de saída.** Se o script devolve `!= 0`, o cron **não avisa ninguém** (a menos
>    que você redirecione `2>&1` para um log, como no exemplo). O log é o seu alarme.
> **Em resumo:** primeiro o *ambiente*, depois o *caminho*, depois as *permissões*, e
> sempre o *log* como fonte da verdade.

---

## 🧩 Exercícios extras (do repositório e do sistema)

| Onde | Sobre |
|---|---|
| `manual-qa-completo/Makefile` | Automação com alvos nomeados (`make scripts`, `make test-api`, `make all`) — o `Makefile` é um script de shell com nome |
| `manual-qa-completo/run_all.py` | Executa uma lista de scripts, conta falhas e **devolve código de saída** — o mesmo contrato do `set -e` |
| `Central-de-noticias/.github/workflows/update-news.yml` | **Cron real** em YAML, guarda "já atualizou hoje?", `|| true` para não abortar o pipeline e `git diff --cached --quiet` para não commitar sem mudança |
| `qa-automation-framework/` | Estrutura de pastas profissional (`config/`, `core/`, `tests/`, `utils/`) para organizar os scripts do projeto |
| `laboratorio-tech-social/site/exercicios/simulador-api.html` | Praticar requisição e status HTTP antes do módulo de Python |
| `QA_RUN` — jogo *Terminal Typer* | Treinar a ordem correta dos comandos de terminal (jogo 23 do hub) |
| `QA_RUN` — jogo *Log Watch* | Separar linha de log suspeita de linha legítima (jogo 63) |

**Exercícios de terminal para treinar fora da aula:**

1. **Descoberta do sistema:** `uname -a`, `cat /etc/os-release`, `df -h`, `free -h`,
   `nproc`, `whoami`.
2. **Caça ao arquivo perdido:** `find ~ -name "*.csv" -mtime -30` e
   `du -sh ~/Downloads/* | sort -h | tail -5` (descubra o que ocupa mais espaço).
3. **Contador de linhas de código:** `find . -name "*.py" -exec wc -l {} + | tail -1`.
4. **Servidor de arquivos na rede local:** `python3 -m http.server 8000` — sirva a pasta
   do projeto e acesse de outro dispositivo na mesma rede.
5. **Portas e processos:** `ps aux | head -20`, `ss -tlnp` (ou `netstat -an` no Windows).

---

## 🏠 Para casa

1. Escolha **1 tarefa repetitiva da sua rotina** (backup de arquivos, renomear planilhas,
   gerar um relatório, limpar uma pasta de downloads) e escreva um script de shell para
   ela, com **log** e **código de saída**.
2. Agende o script no `cron` (ou no Agendador de Tarefas) e **teste** a execução real.
3. Versione no Git com **3 commits**: `chore: estrutura inicial`, `feat: script de
   <tarefa>` e `docs: README com o uso`.
4. Escreva no `README.md` uma seção **"Problemas conhecidos"** com 1 item. (Dica: quem
   lê um script de automação precisa saber onde ele **falha**.)
5. (Opcional) Leia o capítulo de *cron* da documentação do seu sistema
   (`man 5 crontab` no Linux) e anote os 3 campos que mais confundem gente.

---

## 🔗 Próximo módulo

[02 — Python para Automatizar a Rotina (18+)](02-python-para-automatizar.md)

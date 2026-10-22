# Módulo 7 — Projeto final: automatize um processo real (18+)

**Duração:** 90 min · **Aula 16 de 16**
**Pré-requisito:** Módulos 1 a 6.
**Entregável:** automação de um processo real, com documentação, log de execução, teste automatizado e apresentação de 5 minutos.

---

## 🎯 Objetivo

Ao final da aula, o aluno terá:

1. Entregado uma automação que resolve um problema **observado**, não imaginado.
2. Documentado o processo de forma que outra pessoa consiga rodar e manter.
3. Defendido as decisões do projeto em uma apresentação curta, com evidências.

**Objetivo secundário:** reconhecer o próprio limite — saber o que ficou de fora e por quê.

---

## 📚 Fontes no repositório

| Repositório | O que usar |
|---|---|
| `python-do-zero/` | Base de sintaxe e projetos |
| `lista-de-exercicios-python-brasil/` | Exercícios de lógica e automação |
| `manual-qa-completo/` | Modelo de plano de teste e bug report |
| `qa-automation-framework/` | Estrutura de testes automatizados |
| `laboratorio-tech-social/` | Modelo de documentação e README |
| `Central-de-noticias/` | Exemplo real de automação agendada com log |
| `git-github-iniciantes/15_projeto_pratico/` | Roteiro de projeto completo |

**Links:**
[Python em português](https://docs.python.org/pt-br/3/) ·
[GitHub Pages](https://pages.github.com/) ·
[Laboratório Tech Social](https://github.com/Marquezbertin/laboratorio-tech-social)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Processo observado** | "Antes de automatizar, assista ao trabalho acontecer." |
| **Medição** | "Quanto tempo custa hoje? Sem número, não há melhoria." |
| **Escopo mínimo** | "O menor pedaço que já entrega valor sozinho." |
| **Critério de pronto** | "A lista que diz 'acabou' sem discussão." |
| **Log** | "O diário de cada execução: quando, o que fez, o que falhou." |
| **Teste automatizado** | "Uma execução que prova que a regra continua valendo." |
| **Documentação** | "O que outra pessoa precisa para rodar sem você." |
| **Manutenção** | "O que quebra quando a fonte de dados muda." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"A melhor automação não é a mais sofisticada. É a que resolve um problema que alguém realmente tem — e que continua funcionando na segunda-feira."*

Conte um caso real de automação que **quebrou** porque ninguém previu a mudança de formato do arquivo. A turma aponta o que faltou: teste, log, validação ou documentação.

**Combinado da aula:** cada aluno sai com **uma** automação funcionando e **uma** lista do que ficou de fora.

### Fase 2 — Exploração (20 min)

**Parte 1 — As 6 etapas do projeto (8 min).**

| Etapa | Pergunta que responde | Evidência |
|---|---|---|
| 1. Observar | Quem faz, com que frequência, com que dor? | anotações de 1 semana |
| 2. Medir | Quanto tempo e quantos erros hoje? | tabela antes/depois |
| 3. Escolher | Qual é o menor pedaço com valor? | escopo escrito |
| 4. Prototipar | Funciona no caso mais comum? | script rodando |
| 5. Testar | E nos casos estranhos? | teste automatizado |
| 6. Entregar | Outra pessoa consegue usar? | README + log |

**Parte 2 — Escopo mínimo viável (6 min).**
Exemplo: "automatizar todo o financeiro" → escopo mínimo: "gerar o CSV mensal de despesas a partir da pasta de notas, com validação de data e valor". O resto vira próxima versão.

Escreva no quadro a frase: **"Vou automatizar ___ para ___ , medido por ___ ."**

**Parte 3 — Critérios de pronto (6 min).**

```text
[ ] Roda com um comando e sem edição manual
[ ] Valida a entrada e falha com mensagem clara
[ ] Registra log de cada execução
[ ] Tem pelo menos 1 teste automatizado
[ ] README explica instalar, rodar, testar e limitações
[ ] Nenhum dado sensível no repositório
[ ] Tempo medido antes e depois
```

### Fase 3 — Mão na massa (40 min)

**Atividade A — Fechar o escopo (10 min).**
Preencha o planner e peça revisão de um colega:

| Campo | Preenchimento |
|---|---|
| Processo | |
| Quem sofre a dor | |
| Frequência | |
| Tempo atual por execução | |
| Erros atuais por mês | |
| Escopo mínimo | |
| Fora de escopo | |
| Medida de sucesso | |
| Riscos | |

**Atividade B — Protótipo que roda (20 min).**
Implemente o caminho feliz: entrada → validação → processamento → saída → log.

```python
import logging, sys
from pathlib import Path
from datetime import datetime

logging.basicConfig(
    filename="execucao.log",
    level=logging.INFO,
    format="%(asctime)s %(levelname)s %(message)s",
)

def processar(entrada: Path, saida: Path) -> int:
    if not entrada.exists():
        logging.error("Entrada não encontrada: %s", entrada)
        raise SystemExit(1)
    linhas = [l for l in entrada.read_text(encoding="utf-8").splitlines() if l.strip()]
    if not linhas:
        logging.warning("Entrada vazia: %s", entrada)
        return 0
    saida.write_text("\n".join(linhas), encoding="utf-8")
    logging.info("Processadas %d linhas de %s", len(linhas), entrada)
    return len(linhas)

if __name__ == "__main__":
    total = processar(Path(sys.argv[1]), Path(sys.argv[2]))
    print(f"OK: {total} linhas em {datetime.now():%H:%M:%S}")
```

**Atividade C — Teste e caso estranho (10 min).**
Escreva um teste para o caminho feliz e outro para a entrada vazia. Depois teste **três casos estranhos**: arquivo com acento no nome, linha em branco no meio e valor inválido. Corrija o que quebrar.

### Fase 4 — Projeto (15 min)

**Desafio: "Entrega"**
Finalize README de 1 página e prepare a apresentação de 5 minutos:

```text
1. O problema e quem sente (1 min)
2. O que existia antes (1 min)
3. O que a automação faz (1 min)
4. Demonstração ao vivo (1 min)
5. O que ficou de fora e o que aprendi (1 min)
```

**Critério de pronto:** a lista do "Critérios de pronto" acima, com evidência para cada item.

### Fase 5 — Mostra (5 min)

Duas apresentações completas no projetor. A turma usa a rubrica:

| Critério | 0-3 |
|---|---|
| Problema real e bem delimitado | |
| Funciona na demonstração | |
| Qualidade da documentação | |
| Teste e log presentes | |
| Clareza da apresentação | |

---

## 📝 Avaliação

| Componente | Peso |
|---|---|
| Entregável funcionando | 40% |
| Documentação (README + log) | 20% |
| Teste automatizado e tratamento de erro | 20% |
| Apresentação e reflexão sobre limites | 20% |

**Pergunta de escrita:**
> "Sua automação economiza 3 horas por mês, mas exige 30 minutos de verificação a cada execução e quebrou duas vezes em três meses. Ela vale a pena? Como decidir?"
> **Resposta:** vale se o **saldo líquido** for positivo e o risco for aceitável: economia de 3 h menos 0,5 h de verificação × execuções, descontando o tempo de manutenção das quebras. A decisão deve considerar também o custo do erro (uma falha silenciosa pode custar mais que as 3 h). O correto é medir, registrar as quebras e melhorar a validação — ou reduzir o escopo.

---

## 🧩 Checklist de entrega

- [ ] Automação rodando com um comando
- [ ] Validação de entrada com mensagem clara
- [ ] Log de execução gerado
- [ ] Pelo menos 1 teste automatizado
- [ ] README de 1 página (instalar, rodar, testar, limitações)
- [ ] Tempo antes/depois medido
- [ ] Nenhum dado sensível no repositório
- [ ] Apresentação de 5 minutos ensaiada

---

## 🏠 Para casa / Onde continuar

1. Agende a automação (cron ou Agendador de Tarefas) e acompanhe o log por duas semanas.
2. Abra uma issue para cada melhoria que ficou fora do escopo.
3. Continue estudando:
   - [Pro Git](https://git-scm.com/book/pt-br) — capítulos 2 e 3
   - [Documentação do pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
   - [Python para automação](https://automatetheboringstuff.com/)
   - [ANPD](https://www.gov.br/anpd/) — guias para pequenos negócios
   - [Laboratório Tech Social](https://github.com/Marquezbertin/laboratorio-tech-social) — continue contribuindo

**Parabéns:** você concluiu a trilha de 24 horas. O próximo passo é ensinar: escolha um módulo e dê uma oficina para alguém. Ensinar é a forma mais rápida de consolidar.

---

## 🔗 Voltar ao início

[Plano da trilha 18+](00-plano-da-trilha.md) · [Guia do professor](../00-GUIA-DO-PROFESSOR/01-plano-de-ensino-geral.md) · [README do projeto](../README.md)

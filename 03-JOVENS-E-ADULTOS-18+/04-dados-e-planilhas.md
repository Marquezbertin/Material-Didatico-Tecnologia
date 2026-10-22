# Módulo 4 — Dados e Planilhas: limpar, cruzar, decidir (18+)

**Duração:** 90 min · **Aula 4 de 16**
**Pré-requisito:** Módulo 2 (Python) e noções de planilha.
**Entregável:** relatório automático com três indicadores e um registro das decisões de limpeza.

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Diagnosticar os quatro problemas clássicos de uma base de dados: formato inconsistente, duplicidade, valores ausentes e valores fora de faixa.
2. Limpar e cruzar dados com `pandas`, registrando cada decisão tomada.
3. Produzir um relatório com três indicadores confiáveis e um gráfico honesto.

**Objetivo secundário:** explicar por que "dado limpo" não é o mesmo que "dado que confirma o que eu queria".

---

## 📚 Fontes no repositório

| Repositório | O que usar |
|---|---|
| `Analise-de-Dados/` | Notebooks e exemplos de análise exploratória |
| `planilhaeletronicas/` | Exercícios de planilha (fórmulas, gráficos, tabelas dinâmicas) |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Gerar dados fictícios para praticar |
| `laboratorio-tech-social/site/exercicios/visualizador-dados.html` | Visualizar a base antes de analisar |
| `Central-de-noticias/` | Exemplo real de coleta e organização de dados com automação diária |

**Links:**
[Documentação do pandas](https://pandas.pydata.org/docs/) ·
[Python em português](https://docs.python.org/pt-br/3/) ·
[DB Browser for SQLite](https://sqlitebrowser.org/) ·
[Google Colab](https://colab.research.google.com/)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Qualidade de dados** | "Se entra lixo, sai decisão errada — com aparência de rigor." |
| **Duplicidade** | "A mesma linha contada duas vezes infla qualquer total." |
| **Valor ausente** | "Vazio não é zero; tratar como zero é inventar dado." |
| **Tabela de referência** | "A lista do que é aceito, para validar cada linha." |
| **Média vs mediana** | "A média sente o extremo; a mediana resiste a ele." |
| **Join (`merge`)** | "Cruzar duas tabelas por uma chave em comum." |
| **`groupby`** | "Agrupar para comparar: por mês, por categoria, por região." |
| **Registro de decisão** | "Quem limpou, o quê, por quê e quantas linhas mudaram." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Esta planilha diz que as vendas cresceram 40%. Só que a mesma nota fiscal foi importada três vezes. O número não está errado por má-fé — está errado porque ninguém limpou."*

Mostre uma planilha real (ou fictícia) com data em três formatos, linha duplicada e célula vazia. Pergunte: *"Quais desses problemas mudam a conclusão?"*

**Demonstração (4 min):** abra o mesmo CSV no Excel e no pandas; mostre que o pandas "enxerga" tipos (data, número, texto) e que isso muda a análise.

### Fase 2 — Exploração (20 min)

**Parte 1 — Diagnóstico antes de limpar (8 min).**

```python
import pandas as pd

df = pd.read_csv("vendas.csv")
print(df.shape)              # (linhas, colunas)
print(df.dtypes)             # tipos detectados
print(df.isna().sum())       # ausentes por coluna
print(df.duplicated().sum()) # linhas duplicadas
print(df["data"].head())     # formatos de data
```

Regra: **fotografe a base antes de mexer**. Guarde `df.shape` e a contagem de ausentes para comparar depois.

**Parte 2 — Limpeza com registro (7 min).**

```python
antes = len(df)

df["data"] = pd.to_datetime(df["data"], errors="coerce", dayfirst=True)
df["valor"] = pd.to_numeric(df["valor"], errors="coerce")

df = df.drop_duplicates(subset=["pedido", "cliente"])
df = df.dropna(subset=["data", "valor"])

print(f"Linhas: {antes} -> {len(df)} (removidas {antes - len(df)})")
print("Datas inválidas:", df["data"].isna().sum())
```

`errors="coerce"` transforma o inválido em vazio em vez de quebrar o programa — mas **vazio precisa ser decidido**, não ignorado.

**Parte 3 — Validação contra tabela de referência (5 min).**

```python
categorias_validas = {"eletrônico", "vestuário", "alimento", "serviço"}
invalidas = df[~df["categoria"].isin(categorias_validas)]
print("Categorias fora da referência:", len(invalidas))
```

Dados inválidos vão para uma **aba separada de rejeitados**, com o motivo. Nunca apague em silêncio.

### Fase 3 — Mão na massa (40 min)

**Atividade A — Limpeza guiada (15 min).**
Use o `gerador-dados.html` para produzir uma base com problemas plantados. Rode o diagnóstico, limpe e preencha a tabela de decisões:

| Decisão | Linhas afetadas | Justificativa |
|---|---|---|
| Converter data | 320 | formatos mistos |
| Remover duplicadas | 27 | mesma nota importada 2× |
| Descartar sem valor | 15 | impossível calcular total |

**Atividade B — Cruzar duas bases (15 min).**

```python
clientes = pd.read_csv("clientes.csv")   # id_cliente, nome, cidade
vendas = pd.read_csv("vendas.csv")       # id_cliente, valor, data

junto = vendas.merge(clientes, on="id_cliente", how="left")
print(junto.groupby("cidade")["valor"].sum().sort_values(ascending=False))
```

Verifique quantas linhas **não** encontraram correspondência (`how="left"` + `isna()`): é o teste de qualidade do cruzamento.

**Atividade C — Três indicadores (10 min).**
Produza: total do período, ticket médio e cidade com maior receita. Para cada um, escreva **uma frase** com o número, o recorte e a limitação ("com base em 1.240 notas após remover 27 duplicadas").

### Fase 4 — Projeto (15 min)

**Desafio: "Relatório de uma página"**
Monte um relatório com: base usada (linhas antes/depois), tabela de decisões, três indicadores e **um gráfico** com título, unidade e fonte.

**Critério de pronto:**
- [ ] Diagnóstico inicial registrado
- [ ] Cada limpeza justificada e quantificada
- [ ] Nenhum ausente tratado como zero sem justificativa
- [ ] Indicadores com recorte e limitação explícitos
- [ ] Gráfico com eixo começando em zero (ou aviso claro se não começar)
- [ ] Script reproduzível (roda de novo e dá o mesmo resultado)

### Fase 5 — Mostra (5 min)

Dois relatórios no projetor. A turma aponta **um número que pode enganar** e como corrigir.

**Pergunta de saída:** *"Quando a média engana mais que a mediana? Dê um exemplo."*

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Diagnóstico | Identifica os quatro problemas na base |
| Limpeza | Decisões justificadas e quantificadas |
| Cruzamento | Confere linhas sem correspondência |
| Indicadores | Recorte e limitação explícitos |
| Reprodutibilidade | O script roda de novo sem ajuste manual |

**Pergunta de escrita:**
> "Uma base tem 10% de valores ausentes na coluna `valor`. O analista preencheu todos com zero e calculou a média. O que está errado e o que fazer?"
> **Resposta:** preencher com zero **inventa** informação e puxa a média para baixo. O correto é investigar por que faltam (falha de coleta? campo opcional?), decidir com registro (excluir do cálculo, imputar com critério e sinalizar) e informar o número de linhas afetadas no relatório.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `planilhaeletronicas/` | Fórmulas, referências relativas/absolutas, gráficos |
| `Analise-de-Dados/` | Análise exploratória em notebooks |
| `laboratorio-tech-social/site/trilhas/adolescentes/04-dados.html` | Trilha de dados (linguagem acessível) |
| `laboratorio-tech-social/trilhas/adolescentes-13-20/modulo-04-ciencia-dados.md` | Módulo completo de ciência de dados |

---

## 🏠 Para casa

Automatize o relatório: um script que lê a base bruta, limpa, calcula os três indicadores e grava `relatorio.md` + `grafico.png`. Agende com `cron` (Linux) ou Agendador de Tarefas (Windows) e registre o log de cada execução.

---

## 🔗 Próximo módulo

[Módulo 5 — Segurança digital e LGPD](05-seguranca-digital-e-lgpd.md)

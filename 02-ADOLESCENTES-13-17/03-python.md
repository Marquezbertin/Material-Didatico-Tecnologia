# B3 — Python do Zero (13–17 anos)

**Duração:** 90 min · **Aula 3 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Escrever e executar um programa Python com **entrada, saída, variável, condicional, laço, lista e função** — sem colar Stack Overflow.
2. Ler e explicar um **trace** (execução passo a passo) de um programa de 15 linhas.
3. Ler a **"Resposta Esperada"** de um exercício do repo e autoavaliar sua solução.

**Objetivo secundário:** Ler mensagens de erro do Python em inglês e sacar o que elas dizem.

---

## 📚 Fontes no repositório

`python-do-zero/` — **15 módulos × 6 exercícios = 90 exercícios**, todos com **"Resposta Esperada"**:

| Módulo | Conteúdo | Exercícios (nomes de arquivo) |
|---|---|---|
| `01_introducao` | O que é Python, primeiro programa, IDE | `exercicio_01_*.txt` … |
| `02_entrada_saida` | `input()`, `print()`, tipos de saída | |
| `03_operadores` | Aritméticos, comparação, lógicos, **`+=`, `**`**, f-string | |
| `04_condicionais` | `if`, `elif`, `else`, operadores ternários | |
| `05_repeticoes` | `for`, `range`, `while`, `break`, `continue` | |
| `06_listas` | Criar, acessar, percorrer, `append`, `remove`, fatiamento | |
| `07_tuplas_dicionarios` | Tupla, dicionário, `.get()`, percorrer chave/valor | |
| `08_funcoes` | `def`, parâmetros, retorno, escopo, padrão | |
| `09_strings` | Fatiamento, métodos (`upper`, `split`, `replace`, `join`) | |
| `10_arquivos` | Abrir, ler, escrever, `with`, CSV | |
| `11_tratamento_erros` | `try/except/finally`, exceções | |
| `12_modulos` | `import`, `from`, módulos da biblioteca padrão | |
| `13_programacao_orientada_objetos` | Classes, `__init__`, métodos, herança | |
| `14_projetos_praticos` | 6 projetos completos | |
| `15_api_e_json` | Consumo de API, JSON, `requests` | |

**Complementos:**
- `laboratorio-tech-social/site/trilhas/adolescentes/01-python.html` — trilha web
- `laboratorio-tech-social/materiais/slides/aula-teens-01-python.html` — slide
- `laboratorio-tech-social/site/exercicios/desafios-python.html` — exercícios no navegador
- `laboratorio-tech-social/site/exercicios/flashcards.html` — fixação por cartões
- `lista-de-exercicios-python-brasil/` — 112 exercícios (6 seções), com **doctests**
- `Calculadora/`, `jogo_da_velha/`, `o_acolito/`, `anyms/` — projetos reais do autor

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Variável** | "Uma caixa com nome dentro. O nome é o rotulo, o conteúdo muda." |
| **Tipo** | "Python descobre o tipo sozinho. Você não declara." |
| **Indentação** | "Em Python, espaço no começo da linha **é sintaxe**. Erro de espaço = programa errado." |
| **`input()` sempre retorna texto** | "Sempre. Sempre. Sempre. Precisa converter." |
| **f-string** | `f"Ola {nome}"` — o jeito moderno de juntar texto |
| **Lista vs Dicionário** | "Lista = gavetas numeradas. Dicionário = gavetas com etiqueta." |
| **Função** | "Uma caixa que recebe, faz, devolve. Sem devolução, é procedimento." |
| **`with`** | "Abre, usa e fecha sozinho. Mesmo se der erro." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"O programa de vocês vai ler o nome, perguntar 3 coisas e imprimir um resultado.
Parece bobo. Mas é exatamente a estrutura de TODO programa do mundo."*

**Demonstração ao vivo (5 min):** no Colab, digite **com erros de propósito**:
```python
print("Ola" nome)
```
A turma vê o `SyntaxError`. Pergunte: *"O que ele está reclamando?"*
Explique: em Python, `(` precisa fechar. O erro de digitação **é** o erro de sintaxe.

**Outra demo (3 min):**
```python
idade = input("Idade: ")
print(idade + 1)
```
`TypeError: can only concatenate str (not "int") to str`.
Diga: *"Erro em Python não é um problema. É o Python te mostrando onde está o problema.
Traduzir a mensagem é 80% do trabalho de programmer."*

**Dica de ouro (o repo `ingles-para-programadores` é exatamente sobre isso):**
> "A documentação e os erros estão em inglês. Aprender a ler erro em inglês **é** aprender a programar."

### Fase 2 — Exploração (20 min)

**Parte 1 — A anatomia de um programa (8 min).**
Escreva na lousa e peça para a turma identificar as 7 partes:

```python
# 1. comentario
nome = input("Como voce se chama? ")          # 2. entrada
notas = []                                      # 3. lista
for i in range(3):                              # 4. laco
    notas.append(float(input(f"Nota {i+1}: ")))  # 5. entrada dentro do laco
media = sum(notas) / len(notas)                  # 6. calculo
if media >= 7:                                  # 7. condicional
    situacao = "aprovado"
else:
    situacao = "reprovado"
print(f"{nome}: media {media:.2f} - {situacao}")  # 8. saida com f-string
```

Perguntas: *"Qual linha precisa de indentação?"* / *"Onde está o `input`?"* /
*"O que o `:2f` faz?"* (2 casas decimais)

**Parte 2 — Lista vs Dicionário (7 min).**
```python
# LISTA: indice numerico
alunos = ["Ana", "Bruno", "Carla"]
print(alunos[0])        # Ana

# DICIONARIO: chave -> valor
notas = {"Ana": 8.5, "Bruno": 6.0, "Carla": 9.5}
print(notas["Ana"])      # 8.5
print(notas.get("Dani", 0))   # 0  <- .get() nao quebra se nao existe
```
Pergunta: *"Qual você usaria para uma lista depresence? E para o cadastro de cada aluno?"*

**Parte 3 — Lendo erro (5 min).**
Mostre 4 erros típicos e o que significam:

| Erro | Significado | O que fazer |
|---|---|---|
| `SyntaxError` | Falta `:` ou parêntese, ou indentação errada | Releia a linha do traceback |
| `NameError: name 'x' is not defined` | Você usou `x` antes de criar | Verifique a ordem das linhas |
| `TypeError` | Tipo errado (texto com número) | `int()`, `float()`, `str()` |
| `IndentationError` | Espaço faltando ou sobrando | Regra: 4 espaços |

> **Método do repo `ingles-para-programadores/08_comandos_ingles/`:** leia a mensagem como
> uma frase: "cannot convert str to float" = "não consegui converter texto em número".

### Fase 3 — Mão na massa (35 min)

**Atividade A — Do módulo 01 ao 05 (20 min).**
No Colab (ou Python local), faça **5 exercícios** de `python-do-zero`, **1 de cada módulo**:

| Módulo | Exercício sugerido | Como achar |
|---|---|---|
| `01_introducao` | Primeiro programa | `exercicio_01_*.txt` do módulo |
| `02_entrada_saida` | Formatar saída com f-string | `exercicio_02_*.txt` |
| `03_operadores` | Calculadora de média com 3 operadores | `exercicio_03_*.txt` |
| `04_condicionais` | Classificar por faixa de idade | `exercicio_04_*.txt` |
| `05_repeticoes` | Somar 1 a N com `for` e depois com `while` | `exercicio_05_*.txt` |

**Regra da turma:** para cada exercício, o aluno **cola a "Resposta Esperada" do repo** no
começo do arquivo e compara com a saída real.

**Atividade B — Funções (15 min).**
Do módulo `08_funcoes`, implemente:
```python
def media(notas):
    return sum(notas) / len(notas)

def classificacao(m):
    if m >= 9: return "A"
    elif m >= 7: return "B"
    elif m >= 5: return "C"
    else: return "D"

alunos = {"Ana": [8,9,10], "Bruno": [5,6,4], "Carla": [10,10,9]}
for nome, notas in alunos.items():
    print(f"{nome}: {media(notas):.1f} - {classificacao(media(notas))}")
```
Pergunta: *"Por que `classificacao` recebe um número e não a lista?"* (→ **função pura**, testável)

### Fase 4 — Projeto (20 min)

**Desafio: "Sua ficha de estudante"**
Escreva um programa que:
1. Peça nome, idade, 3 notas e 1 cidade.
2. Valida cada entrada (idade entre 0 e 120, nota entre 0 e 10) **usando uma função**
   que devolve `True`/`False`.
3. Calcula a média com **f-string formatado**.
4. Salve os dados em uma **lista de dicionários**.
5. No final, mostre todos os cadastros em **tabela** (com `f"{:<20}"` para alinhar).

**Critério de pronto:**
- [ ] Usa **função** para a validação (não repete o `if` 4 vezes)
- [ ] Usa **f-string** em toda saída
- [ ] Guarda em **lista de dicionários**
- [ ] **Nenhum** erro ao rodar com entradas inválidas
- [ ] Entrada inválida **não quebra** o programa (repete a pergunta)

### Fase 5 — Mostra (5 min)

2 alunos rodam seu programa ao vivo, um deles **digita uma entrada inválida de propósito**
para mostrar que o programa pede a entrada de novo. A turma ve a robustez.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| 5 exercícios do repo | "Resposta Esperada" coincide com a saída real |
| Funções | 2 funções implementadas e usadas |
| Ficha de estudante | 5 critérios do "pronto" |
| Leitura de erro | 3 erros explained corretamente (quiz rápido) |
| Pergunta de saída | "O que `input()` devolve e por que `idade + 1` quebra?" |

**Quiz rápido (5 min, oral):**
1. `input()` devolve que tipo? → `str` (sempre)
2. Como descubro o tipo de uma variável? → `type(x)`
3. O que faz `//`? → Divisão inteira
4. O que é indentação? → Bloco de código; em Python é sintaxe (4 espaços)
5. `notas[0]` se `notas` é vazio? → `IndexError`

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `python-do-zero/06_listas/` | Fatiamento, comprehensions |
| `python-do-zero/07_tuplas_dicionarios/` | Dicionários aninhados |
| `python-do-zero/09_strings/` | Limpeza de texto (útil para o projeto de dados) |
| `python-do-zero/10_arquivos/` | Ler/escrever CSV (base do projeto final) |
| `python-do-zero/11_tratamento_erros/` | `try/except` (obrigatório no projeto final) |
| `python-do-zero/14_projetos_praticos/` | 6 projetos prontos para adaptar |
| `python-do-zero/15_api_e_json/` | Consumo de API (base do bot de notícias) |
| `lista-de-exercicios-python-brasil/` | 112 exercícios com doctest — banco de exercícios |
| `laboratorio-tech-social/site/exercicios/desafios-python.html` | Exercícios rodando no navegador |

---

## 🏠 Para casa

Refazer a "Ficha de Estudante" em **VS Code** (não no Colab) e **subir para o GitHub**
(depois da aula 07). Traga a pasta.

---

## 🔗 Próximo módulo

[B4 — Python: projetos práticos](04-python-projetos.md)

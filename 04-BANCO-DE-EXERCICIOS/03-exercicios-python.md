# EX-P3 — Banco de Exercícios: Python (13–17 anos)

**Trilha:** Adolescentes [B3 — Python do Zero](../02-ADOLESCENTES-13-17/03-python.md) ·
[B4 — Python: Projetos](../02-ADOLESCENTES-13-17/04-python-projetos.md) ·
Adultos [02 — Python para Automatizar a Rotina](../03-JOVENS-E-ADULTOS-18+/02-python-para-automatizar.md)

| Item | Descrição |
|---|---|
| **Faixa etária** | 13 a 17 anos (revisão rápida para 18+) |
| **Nº de itens** | 20 — código em Python (preencher lacunas, corrigir, escrever do zero) |
| **Nível** | ⭐ Fácil (5 itens) · ⭐⭐ Médio (9 itens) · ⭐⭐⭐ Difícil (6 itens) |
| **Tempo estimado** | 70 a 90 min (2 a 4 min por item, mais 10 min de desafio final) |
| **Formato** | Enunciado com código e **gabarito com o código completo** de cada resposta |

> ⚠️ **Licença de uso:** material livre, sob a licença **CC BY 4.0** (Creative Commons
> Atribuição 4.0 Internacional). Você pode copiar, adaptar e redistribuir, desde que cite a
> autoria (Bruno Bertin Marquez) e indique as mudanças. Licença:
> https://creativecommons.org/licenses/by/4.0/

---

## 🎯 Objetivo

Ao final da atividade, o aluno será capaz de:

1. Usar **variáveis**, **tipos** (`int`, `float`, `str`, `bool`, `list`, `dict`) e `print()`.
2. Construir **listas** e **dicionários**, percorrê-los e transformá-los.
3. Controlar o fluxo com **`if`**, **`for`**, **`while`**, `break` e `continue`.
4. Criar **funções** com `return`, parâmetro e valor padrão.
5. Ler e gravar **arquivos** e tratar **exceções** com `try/except`.

**Objetivo secundário:** ler o enunciado como um contrato — quem entra, o que sai, o que
pode dar errado.

---

## 📚 Fontes no repositório

| Repositório | Pasta usada | O que foi aproveitado |
|---|---|---|
| `python-do-zero` | `01_introducao/` | Variáveis, tipos de dados, nomes de variáveis |
| `python-do-zero` | `02_entrada_saida/` e `03_operadores/` | `input()`, `print()`, f-strings, operadores |
| `python-do-zero` | `04_condicionais/` | `if`/`elif`/`else` e ternário |
| `python-do-zero` | `05_repeticoes/` | `for`, `while`, `break`, `continue` |
| `python-do-zero` | `06_listas/` | Criação, métodos básicos, slicing, list comprehension |
| `python-do-zero` | `07_tuplas_dicionarios/` | Dicionários, `keys`, `values`, aninhamento, agenda |
| `python-do-zero` | `08_funcoes/` | `def`, retorno, parâmetros, escopo |
| `python-do-zero` | `10_arquivos/` | Escrever, ler, `append`, bloco `with`, CSV |
| `python-do-zero` | `11_tratamento_erros/` | `try/except`, tipos de erro, `else`/`finally`, `raise` |
| `lista-de-exercicios-python-brasil` | `secao_01` a `secao_06` | 112 exercícios clássicos com doctest (bom para mostrar "teste como documentação") |

**Ambiente de execução:** [Google Colab](https://colab.research.google.com/) (não precisa
instalar nada) ou Python 3 local.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Variável** | "Uma **caixa com etiqueta** que guarda um valor." |
| **`input()`** | "Devolve **texto**. Sempre texto." |
| **Tipo** | "O **formato** do valor: `int`, `float`, `str`, `bool`, `list`, `dict`." |
| **Indicação de bloco** | "Python usa **recuo (indentação)**, não chaves." |
| **`for`** | "Para **cada** item de uma sequência." |
| **`while`** | "**Enquanto** a condição for verdadeira." |
| **Lista** | "Lista **numerada**, começa no 0." |
| **Dicionário** | "Lista com **chave e valor**." |
| **Função** | "Trecho **reutilizável** com nome." |
| **`with open(...)`** | "Abre, usa e **fecha** sozinho. Mesmo com erro." |
| **`try/except`** | "Tenta; se explodir, **não morre**." |

---

## 📝 Exercícios 1 a 5 — Variáveis, tipos e entrada (⭐ Fácil)

### Exercício 1 — Preencher as lacunas ⭐ · ⏱️ 2 min

Complete o código para que o programa exiba exatamente `Ana tem 14 anos.`

```python
nome = "Ana"
idade = 14

print(__________________________________________)
```

### Exercício 2 — Descobrir os tipos ⭐ · ⏱️ 2 min

Escreva, ao lado de cada valor, o **tipo** que o Python devolve para `type(valor)`:

```python
valores = [15, 15.5, "15", True, [15], {"nome": "Ana"}]
```

### Exercício 3 — Entrada de dados ⭐ · ⏱️ 2 min

Complete o código para que o programa salve o nome digitado e o apresente:

```python
nome = input("Qual é o seu nome? ")
print("Olá, __________________!")
```

### Exercício 4 — Concatenar com f-string ⭐ · ⏱️ 2 min

Reescreva os dois `print()` usando **f-string** (uma string com `{}` dentro):

```python
produto = "caderno"
preco = 12.50
quantidade = 3

print("Produto:", produto, "Preço:", preco, "Quantidade:", quantidade)
print("Total:", preco * quantidade)
```

### Exercício 5 — Lista de compras ⭐ · ⏱️ 3 min

Escreva um programa que **crie uma lista** com três itens de compra, **adicione** um quarto
item com `append()` e **exiba** a lista final e a quantidade de itens com `len()`.

---

## 📝 Exercícios 6 a 10 — Condicionais e laços (⭐⭐ Médio)

### Exercício 6 — Corrigir o erro de tipo ⭐⭐ · ⏱️ 3 min

O programa abaixo **não dá erro nenhum** — e é exatamente por isso que o defeito é pior: ao
digitar `4` e `7`, ele exibe `A soma é: 47` quando a soma correta seria `11`. Encontre o
problema e **corrija**:

```python
a = input("Primeiro número: ")
b = input("Segundo número: ")
soma = a + b
print("A soma é:", soma)
```

### Exercício 7 — Condicional de aprovação ⭐⭐ · ⏱️ 3 min

Escreva um programa que leia a **nota** e exiba `Aprovado` se for **maior ou igual a 6**, e
`Reprovado` caso contrário.

### Exercício 8 — `for` com `range` ⭐⭐ · ⏱️ 3 min

Escreva um programa que imprima os números de **1 a 10**, um por linha, usando `for` e `range`.

### Exercício 9 — `while` com contador decrescente ⭐⭐ · ⏱️ 3 min

Reescreva o exercício 8 com `while`, contando de **10 até 1** (inclusive).

### Exercício 10 — `break` e `continue` ⭐⭐ · ⏱️ 3 min

Escreva um programa que imprima os números de **1 a 20**, mas:

- **não** imprima os múltiplos de 3 (use `continue`);
- **pare** a execução ao chegar no 15 (use `break`).

---

## 📝 Exercícios 11 a 15 — Listas e dicionários (⭐⭐ Médio / ⭐⭐⭐ Difícil)

### Exercício 11 — Divisão da lista ⭐⭐ · ⏱️ 3 min

Dada a lista abaixo, escreva o código que exibe:

1. o **total** de notas (`len`);
2. a **maior** nota (`max`);
3. a **média** das notas (soma dividida pelo total);
4. as três **primeiras** notas (fatiamento/slicing).

```python
notas = [7.5, 9.0, 6.0, 8.5, 10.0]
```

### Exercício 12 — Índice negativo e fatiamento ⭐⭐ · ⏱️ 3 min

Dada a lista abaixo, escreva o código que exibe o **último** item, o **penúltimo** e a lista
**invertida**:

```python
filmes = ["Matrix", "De volta para o futuro", "Interestelar", "Blade Runner"]
```

### Exercício 13 — List comprehension ⭐⭐⭐ · ⏱️ 4 min

Reescreva o laço abaixo usando **list comprehension** e exiba a nova lista:

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
dobros = []

for numero in numeros:
    dobros.append(numero * 2)

print(dobros)
```

### Exercício 14 — Maior e menor sem `max()` e `min()` ⭐⭐⭐ · ⏱️ 4 min

Escreva uma função que receba uma lista de números e devolva **o maior e o menor**, sem usar
as funções prontas `max()` e `min()`. Dica: comece assumindo que o maior e o menor são o
primeiro item da lista.

### Exercício 15 — Dicionário de alunos ⭐⭐ · ⏱️ 4 min

Crie o dicionário abaixo e depois exiba, **linha por linha**, o nome e a nota de cada aluno
percorrendo o dicionário:

```python
alunos = {
    "Ana": 8.5,
    "Bruno": 7.0,
    "Carla": 9.5
}
```

Escreva também uma frase que **falte** no dicionário: a média da turma.

---

## 📝 Exercícios 16 a 20 — Funções, arquivos e exceções (⭐⭐⭐ Difícil)

### Exercício 16 — Função com valor padrão ⭐⭐⭐ · ⏱️ 4 min

Escreva a função `saudacao(nome, turno="dia")` que devolve:

- `Bom dia, Ana!` quando `turno` é `"dia"`;
- `Boa tarde, Ana!` quando `turno` é `"tarde"`.

Depois chame a função **sem** o segundo argumento e **com** o segundo argumento.

### Exercício 17 — Função que devolve vários valores ⭐⭐⭐ · ⏱️ 4 min

Escreva a função `analisar_notas(notas)` que devolve **três valores**: a média, a maior nota e
a menor nota. Use `return media, maior, menor` e desempacote na chamada:

```python
media, maior, menor = analisar_notas([7.0, 9.5, 6.5])
```

### Exercício 18 — Ler e gravar arquivos ⭐⭐ · ⏱️ 6 min

**Parte A — ler.** O arquivo `notas.txt` tem uma nota por linha. Escreva o código que **lê** o
arquivo com `with open(...)`, ignora as linhas em branco e imprime cada nota:

```python
# conteúdo de notas.txt
8.5
7.0

9.5
```

**Parte B — gravar.** Escreva o código que grava o arquivo `notas.csv` com um cabeçalho e os
dados da lista:

```python
dados = [("Ana", 8.5), ("Bruno", 7.0), ("Carla", 9.5)]
```

O arquivo deve ficar assim:

```
nome,nota
Ana,8.5
Bruno,7.0
Carla,9.5
```

### Exercício 19 — Tratamento de erros ⭐⭐⭐ · ⏱️ 4 min

Escreva um programa que peça um número ao usuário e exiba o **dobro** dele. Se o usuário
digitar algo que não é número, o programa deve avisar **"Digite um número inteiro!"** em vez
de quebrar.

### Exercício 20 — Desafio final: do zero ⭐⭐⭐ · ⏱️ 10 min

Escreva, **do zero**, um programa de **agenda de alunos** que:

1. use um **dicionário** com nome do aluno como chave e nota como valor;
2. preencha a agenda a partir de uma lista de pares (aceite nota com **vírgula**, como `"8,5"`);
3. **cadastre** os alunos com uma **função**;
4. **mostre** a nota de um aluno procurado pelo nome e avise quando ele não existir;
5. calcule e exiba a **média** da turma;
6. **grave** a agenda em `agenda.csv`;
7. **trate** o erro de nota inválida sem parar o programa.

---

## ✅ Gabarito com o código completo

### 1 — Preencher as lacunas

```python
nome = "Ana"
idade = 14

print(f"{nome} tem {idade} anos.")
```

> A f-string (`f"..."`) é o jeito mais curto de juntar texto e variável. As alternativas
> `print(nome, "tem", idade, "anos.")` e `print(nome + " tem " + str(idade) + " anos.")`
> também funcionam.

### 2 — Tipos dos valores

| Valor | Tipo | Por quê |
|---|---|---|
| `15` | `int` | Número inteiro, sem casa decimal |
| `15.5` | `float` | Número com parte decimal |
| `"15"` | `str` | Texto entre aspas, mesmo parecendo número |
| `True` | `bool` | Verdadeiro ou falso |
| `[15]` | `list` | Lista de valores |
| `{"nome": "Ana"}` | `dict` | Dicionário de chave e valor |

> Detalhe que costuma cair em prova: `15` e `"15"` **não são a mesma coisa**. `15 + 1` dá 16;
> `"15" + 1` dá erro.

### 3 — Entrada de dados

```python
nome = input("Qual é o seu nome? ")
print(f"Olá, {nome}!")
```

> `input()` **sempre devolve texto**. Se a variável for usada em conta, precisa converter.

### 4 — Concatenar com f-string

```python
produto = "caderno"
preco = 12.50
quantidade = 3

print(f"Produto: {produto} Preço: {preco} Quantidade: {quantidade}")
print(f"Total: {preco * quantidade}")
```

> A expressão dentro das chaves é avaliada antes de virar texto: `{preco * quantidade}` calcula
> 37.5 e mostra `37.5`.

### 5 — Lista de compras

```python
compras = ["arroz", "feijão", "leite"]
compras.append("café")

print(compras)
print("Total de itens:", len(compras))
```

### 6 — Corrigir o erro de tipo

```python
a = int(input("Primeiro número: "))
b = int(input("Segundo número: "))
soma = a + b
print("A soma é:", soma)
```

> **Por que o programa original não "quebra":** o `input()` devolve **texto**, e o `+` entre
> dois textos **concatena** (junta), não soma — por isso o resultado é `47`, e não `11`.
> O `TypeError` (`can only concatenate str (not "int") to str`) só apareceria ao tentar somar
> **texto com número**, por exemplo `input("Número: ") + 1`.
>
> Esse item é o melhor exemplo de **erro silencioso**: o programa roda, não avisa nada e
> entrega o **número errado**. Por isso a conversão precisa acontecer **antes** da conta.

### 7 — Condicional de aprovação

```python
nota = float(input("Digite a nota: "))

if nota >= 6:
    print("Aprovado")
else:
    print("Reprovado")
```

### 8 — `for` com `range`

```python
for numero in range(1, 11):
    print(numero)
```

> `range(1, 11)` vai de 1 até 10: o **último valor é excluído**.

### 9 — `while` com contador decrescente

```python
contador = 10

while contador >= 1:
    print(contador)
    contador = contador - 1
```

> `contador -= 1` é a forma curta. Cuidado: se esquecer de atualizar o contador, o laço
> nunca termina (laço infinito).

### 10 — `break` e `continue`

```python
for numero in range(1, 21):
    if numero == 15:
        break
    if numero % 3 == 0:
        continue
    print(numero)
```

> Saída: 1, 2, 4, 5, 7, 8, 10, 11, 13, 14. O `continue` pula a impressão; o `break` sai do
> laço.
>
> **A ordem dos testes importa.** O 15 é **múltiplo de 3**: se o `continue` vier antes do
> `break`, ele dispara primeiro, o laço **nunca para** e a saída vai até 20. Por isso o
> `break` (que encerra) fica **antes** do `continue` (que só pula um item). Este é um dos
> erros mais comuns em laço — e só aparece quando você **roda** o código.

### 11 — Divisão da lista

```python
notas = [7.5, 9.0, 6.0, 8.5, 10.0]

print("Total:", len(notas))
print("Maior:", max(notas))
print("Média:", sum(notas) / len(notas))
print("Três primeiras:", notas[:3])
```

### 12 — Índice negativo e fatiamento

```python
filmes = ["Matrix", "De volta para o futuro", "Interestelar", "Blade Runner"]

print("Último:", filmes[-1])
print("Penúltimo:", filmes[-2])
print("Invertida:", filmes[::-1])
```

> Índice negativo conta a partir do fim: `-1` é o último, `-2` é o penúltimo. O fatiamento
> `filmes[::-1]` com passo `-1` devolve a lista ao contrário.

### 13 — List comprehension

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
dobros = [numero * 2 for numero in numeros]

print(dobros)
```

> Equivale a `[numero * 2 for numero in numeros if numero % 2 == 0]` se quermos apenas os
> pares. Saída: `[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]`.

### 14 — Maior e menor sem `max()` e `min()`

```python
def maior_e_menor(numeros):
    maior = numeros[0]
    menor = numeros[0]

    for numero in numeros:
        if numero > maior:
            maior = numero
        if numero < menor:
            menor = numero

    return maior, menor


valores = [7.5, 9.0, 6.0, 8.5, 10.0]
maior, menor = maior_e_menor(valores)
print("Maior:", maior, "Menor:", menor)
```

### 15 — Dicionário de alunos

```python
alunos = {
    "Ana": 8.5,
    "Bruno": 7.0,
    "Carla": 9.5
}

for nome, nota in alunos.items():
    print(f"{nome}: {nota}")

media = sum(alunos.values()) / len(alunos)
print(f"Média da turma: {media:.2f}")
```

> `.items()` devolve pares (chave, valor) na ordem de inserção. `alunos.values()` devolve só os
> valores — é o que permite calcular a média.

### 16 — Função com valor padrão

```python
def saudacao(nome, turno="dia"):
    if turno == "tarde":
        return f"Boa tarde, {nome}!"
    return f"Bom dia, {nome}!"


print(saudacao("Ana"))
print(saudacao("Bruno", "tarde"))
```

> O valor padrão entra **no final** da lista de parâmetros. Assim `saudacao("Ana")` funciona e
> `saudacao("Ana", "tarde")` também.

### 17 — Função que devolve vários valores

```python
def analisar_notas(notas):
    media = sum(notas) / len(notas)
    maior = max(notas)
    menor = min(notas)
    return media, maior, menor


media, maior, menor = analisar_notas([7.0, 9.5, 6.5])
print(f"Média: {media:.2f} | Maior: {maior} | Menor: {menor}")
```

> O `return` com três valores cria uma **tupla**. Ao desempacotar com
> `media, maior, menor = ...`, cada nome recebe um valor na mesma ordem.

### 18 — Ler e gravar arquivos

**Parte A — ler:**

```python
with open("notas.txt", "r", encoding="utf-8") as arquivo:
    for linha in arquivo:
        linha = linha.strip()
        if linha:
            print(linha)
```

> `with` garante que o arquivo seja **fechado**, mesmo se houver erro no meio da leitura.
> `strip()` remove espaços e quebras de linha.

**Parte B — gravar:**

```python
dados = [("Ana", 8.5), ("Bruno", 7.0), ("Carla", 9.5)]

with open("notas.csv", "w", encoding="utf-8") as arquivo:
    arquivo.write("nome,nota\n")
    for nome, nota in dados:
        arquivo.write(f"{nome},{nota}\n")
```

> O modo `"w"` **cria** o arquivo (ou apaga o conteúdo anterior). O `\n` é a quebra de linha
> do CSV — sem ele, tudo sairia numa linha só.

### 19 — Tratamento de erros

```python
try:
    numero = int(input("Digite um número inteiro: "))
except ValueError:
    print("Digite um número inteiro!")
else:
    print("O dobro é", numero * 2)
```

> `ValueError` é o erro levantado pelo `int()` quando o texto não é número. O bloco `else` só
> roda quando **não** houve erro.

### 20 — Desafio final: agenda de alunos

```python
def cadastrar_aluno(agenda, nome, nota):
    """Cadastra o aluno na agenda, aceitando nota com vírgula."""
    agenda[nome] = float(str(nota).replace(",", "."))


def mostrar_aluno(agenda, nome):
    """Mostra a nota do aluno ou avisa que ele não está na agenda."""
    if nome in agenda:
        print(f"{nome}: {agenda[nome]}")
    else:
        print(f"Aluno {nome} não encontrado.")


def media_da_turma(agenda):
    """Devolve a média das notas (0 se a agenda estiver vazia)."""
    if not agenda:
        return 0.0
    return sum(agenda.values()) / len(agenda)


def salvar_agenda(agenda, caminho="agenda.csv"):
    """Grava a agenda em um arquivo CSV."""
    with open(caminho, "w", encoding="utf-8") as arquivo:
        arquivo.write("nome,nota\n")
        for nome, nota in agenda.items():
            arquivo.write(f"{nome},{nota}\n")


agenda = {}
dados = [("Ana", "8,5"), ("Bruno", "7"), ("Carla", "9,5"), ("Diego", "dez")]

for nome, nota in dados:
    try:
        cadastrar_aluno(agenda, nome, nota)
    except ValueError:
        print(f"Nota inválida para {nome}: {nota}")

mostrar_aluno(agenda, "Ana")
mostrar_aluno(agenda, "Diego")
print(f"Média da turma: {media_da_turma(agenda):.2f}")

salvar_agenda(agenda)
```

> Saída esperada:
> ```
> Nota inválida para Diego: dez
> Ana: 8.5
> Aluno Diego não encontrado.
> Média da turma: 8.33
> ```
> O item `Diego` é o teste do tratamento de erro: a nota inválida **não** derruba o programa.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Prova de Python | 14 ou mais acertos em 20 |
| Itens 6, 10 e 14 | O aluno **explica** a causa do erro, não só corrige |
| Item 20 | Programa roda sem erro e trata a nota inválida |
| Leitura de código | O aluno consegue dizer o que cada linha faz |

**Pergunta de escrita:**
> "Por que `input()` sempre devolve texto, mesmo quando a pessoa digita um número?"
> **Resposta:** porque o `input()` só captura os **caracteres digitados**; para o Python, "8"
> e "8.5" são sequências de caracteres. Converter com `int()` ou `float()` é o que transforma o
> texto em número — e é por isso que esquecer essa conversão causa `TypeError` ou `ValueError`.

---

## 🏠 Para casa

Escolha um item do Bloco E do [EX-A2](02-exercicios-algoritmos.md) e reescreva a **versão
corrigida em Python**. O código deve ter comentários curtos explicando cada bloco — comentários
também são código.

---

## 🔗 Próximo módulo

[EX-W4 — Banco de Exercícios: HTML, CSS e JavaScript (13–17 anos)](04-exercicios-web.md)

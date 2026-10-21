# B4 — Python: projetos práticos (13–17 anos)

**Duração:** 90 min · **Aula 4 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Escolher, **adaptar e executar** 3 exercícios do banco `lista-de-exercicios-python-brasil` (112 exercícios, com **doctest**).
2. **Transformar um exercício** em uma solução completa: entrada validada + função + saída formatada + `try/except`.
3. **Publicar 1 Pull Request** em um repositório open source resolvendo um exercício vazio.

**Objetivo secundário:** Ler um `doctest` e saber reescrever o teste quando a resposta esperada mudar.

---

## 📚 Fontes no repositório

### `lista-de-exercicios-python-brasil/` — 112 exercícios, 6 seções

| Seção | Nº | Exemplos |
|---|---|---|
| `secao_01_estrutura_sequencial` | 18 | Alo Mundo, soma de 2 números, notas bimestrais, m→cm, área do círculo, Fahrenheit→Celsius, peso ideal, CLT, loja de tintas, tempo de download |
| `secao_02_estrutura_de_decisao` | 28 | Maior número, positivo/negativo, F ou M, vogal/consoante, 3 números, números decrescentes, turno, salário tabajara, triângulo, equação do 2º grau, ano bissexto, **validador de data**, decomposição de número, troco, Sherlock, posto de gasolina, hortifruti |
| `secao_03_estrutura_de_repeticao` | 48 | Número válido, **validador de senha**, validador de cadastro, crescimento populacional, números 1 a 20, tabuada, Fibonacci, fatorial, número primo, primos menores que N, média aritmética, classificador de turma, **urna eletrônica**, alunos por turma, coleção de CDs, loja/padaria/conveniência, **estatísticas de temperaturas**, tabuada com intervalo, sensor de academia, aumento salarial, sala de aula, trânsito, financiamento, lanchonete, eleição presidencial, corretor de provas, salto em distância, inteiro invertido, imprimir série |
| `secao_04_exercicios_lista` | 13 | Vetor 5 números, vetores inverso, média 4 notas, vetor par e ímpar, calculadora de média, soma de quadrados, intercalação de vetores, filtro de baixinhos, média de temperaturas anual, investigação, melhor jogador, lançamento de dados |
| `secao_05_exercicios_funcoes` | 2 | Pirâmide, quantidade de dígitos |
| `secao_06_exercicios_strings` | 5 | Comparador de strings, inversor maiúsculo, nome vertical em escada, **validador de CPF (strings)** |

> **Achado importante (verificado na auditoria):** das 112 questões, **107 são stubs
> vazios** — só 5 têm solução pronta. Isso é uma **oportunidade**, não um problema:
> a turma pode resolver e contribuir de verdade.

### Projetos reais do autor (para estudar estilo e estrutura)

| Repositório | O que estudar |
|---|---|
| `Calculadora/` | Flask + Jinja2, 2 rotas, formulários |
| `jogo_da_velha/` | Jogo da velha em console, 5 funções |
| `o_acolito/` | Jogo narrativo de aventura, 5 classes |
| `Roteiro-de-Estudos/` | App Tkinter de rotina de estudos |
| `hubias-estudos/` | SQLite (WASM) no navegador + flashcards + Pomodoro + sync |
| `anyms/` | Gestão com IndexedDB, 17 tabelas, custo médio ponderado |
| `meu-treino/` | PWA com Wake Lock, GPS, Web Share, localStorage |
| `tdm-app/` | Geração e mascaramento de dados de teste com Faker |
| `consulta_CNPJ/` | Consumo de 2 APIs, unificando JSON/TXT/Excel |
| `o_acolito/` | ⚠️ o README aponta um nome de script inexistente e PIL/matplotlib não estão declarados — **use como aula de documentação × código** |

### Complementos
- `python-do-zero/14_projetos_praticos/` — 6 projetos prontos
- `python-do-zero/11_tratamento_erros/` — `try/except`
- `python-do-zero/10_arquivos/` — CSV
- `laboratorio-tech-social/site/exercicios/desafios-python.html`

---

## 🧠 Conceitos-chave

| Conceito | Onde aparece |
|---|---|
| **Doctest** | Teste escrito dentro do próprio código, como saída esperada de `>>>` |
| **Stubs** | Função vazia com o enunciado — é o "esqueleto" do exercício |
| **`try/except`** | O programa não pode quebrar por causa do usuário |
| **Separação entrada/lógica/saída** | A mesma estrutura do Visualg, agora em Python |
| **Contribuição open source** | Fork → branch → commit → Pull Request |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Esse repositório tem 112 exercícios. **107 estão vazios.** Espera. 107
exercícios prontos pra você resolver e deixar o mundo melhor — e o primeiro passo é
descobrir como funciona um Pull Request."*

**Quiz de recuperação (B3):** *"O que `input()` devolve e por que `idade + 1` quebra?"*

### Fase 2 — Exploração (15 min)

**Parte 1 — Anatomia de um exercício do repo (7 min).**
Abra `secao_02_estrutura_de_decisao/ex_17_ano_bissexto.py` e mostre a estrutura real:

```python
def eh_ano_bissexto(ano: int) -> bool:
    """Retorna True se o ano for bissexto."""
    return ano % 4 == 0 and (ano % 100 != 0 or ano % 400 == 0)


def main() -> None:
    ano = int(input("Digite um ano: "))
    if eh_ano_bissexto(ano):
        print(f"{ano} e um ano bissexto")
    else:
        print(f"{ano} nao e um ano bissexto")


if __name__ == "__main__":
    main()
```

Destaque 4 coisas que a turma ainda não viu:
1. **Anotação de tipo** (`ano: int) -> bool`) — o Python anota, mas não obriga.
2. **Docstring** (`"""..."""`) — a documentação da função.
3. **`main()`** — o ponto de entrada do programa.
4. **`if __name__ == "__main__":`** — "rode isto só se eu executar o arquivo direto".

**Parte 2 — Como o repo valida (8 min).**
O repo usa **doctest**: o teste fica dentro do próprio arquivo.

```python
def dobro(n: int) -> int:
    """Retorna o dobro de n.

    >>> dobro(2)
    4
    """
    return n * 2
```

Rode no terminal:
```bash
python -m doctest arquivo.py -v
```
Explicação: *"O doctest é um teste que mora dentro da documentação. Se a documentação
mentir, o teste falha. Por isso ele é chamado de **documentação executável**."*

### Fase 3 — Mão na massa (35 min)

**Atividade A — 3 exercícios resolvidos (20 min).**
Cada aluno escolhe **3** exercícios de seções **diferentes**:

| Seção | Escolha obrigatória (1) | Escolha livre (2) |
|---|---|---|
| Sequencial | `ex_04_notas_bimestrais` ou `ex_09_fahrenheit_para_celsius` | qualquer um dos 18 |
| Decisão | `ex_17_ano_bissexto` ou `ex_18_validador_de_data` | qualquer um dos 28 |
| Repetição | `ex_14_qtde_pares_e_impares` ou `ex_21_numero_primo` | qualquer um dos 48 |
| Lista | `ex_01_vetor_5_numeros` ou `ex_05_vetore_par_e_impar` | qualquer um dos 13 |
| Funções | `ex_01_piramide` | — |
| Strings | `ex_09_validador_de_cpf_strings` ou `ex_02_inversor_maisculo` | qualquer um dos 5 |

**Processo obrigatório de cada exercício (5 min de papel + 15 min de código):**
1. **Leia o enunciado** e escreva em 1 frase o que o programa deve fazer.
2. **Desenhe o fluxograma** (o da trilha 8–12, agora com laços e condições).
3. **Implemente**.
4. **Rode o doctest** (se houver) e ajuste.
5. **Teste com 3 casos:** 1 normal, 1 limite, 1 inválido.

**Atividade B — Blindagem com `try/except` (15 min).**
Todos os programas da turma recebem esta camada:

```python
try:
    entrada = int(input("Digite um número: "))
except ValueError:
    print("Erro: isso não é um número inteiro. Tente de novo.")
    entrada = None
```

E o **`while True`** para repetir até o usuário acertar:
```python
while True:
    try:
        n = int(input("Digite um número: "))
        break
    except ValueError:
        print("Não é número. Tente de novo.")
```

> **Por que isso importa:** a turma vai ver na aula 08 (QA) que **"o programa não pode
> quebrar"** é o primeiro requisito de qualidade. Faça a ligação: *"O `try/except` que
> vocês acabaram de escrever é QA dentro do código."*

### Fase 4 — Projeto (25 min)

**Desafio: "3 exercícios, 1 programa"**
Crie **um único programa** que reúna 3 exercícios do banco em um fluxo com menu:

```
===== MENU =====
[1] Calculadora de IMC
[2] Verificador de ano bissexto
[3] Tabuada do 7
[4] Sair
Escolha: __
```

**Requisitos:**
- [ ] Menu em `while True` com `break` no "Sair"
- [ ] Cada opção é uma **função** separada (com docstring)
- [ ] **Validação de entrada** em todas as opções (`try/except`)
- [ ] Cada função tem **pelo menos 1 teste** (assert ou doctest)
- [ ] Um arquivo só, ≤ 150 linhas, com cabeçalho comentado:
      `# Nome do aluno | Data | Descrição`

**Critério bônus (opcional):** transformar o menu em **funcionário** (você escolhe os
exercícios, não o aluno) e escrever o README do programa.

### Fase 5 — Mostra (5 min)

2 alunos rodam o programa. Um deles **digita letra onde o programa pede número**, para
provar que a blindagem funciona.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| 3 exercícios do banco | Resolvidos e testados com 3 casos cada |
| Programa do menu | 4 requisitos do "pronto" |
| Testes | ≥ 1 teste por função |
| Participação | 1 teste ao vivo por aluno |
| Pergunta de saída | "Para que serve o `try/except` e quando usá-lo?" |

**Pergunta de escrita:**
> "Qual a diferença entre corrigir um erro (`if/else`) e capturar um erro (`try/except`)?"

**Resposta esperada:** `if/else` trata um valor **conhecido e previsível** (a entrada é
inválida); `try/except` trata **falhas inesperadas** (o input não é número, o arquivo não
existe, a rede caiu).

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `lista-de-exercicios-python-brasil/secao_03_estrutura_de_repeticao/ex_25_classificador_de_turma.py` | Classificador de turma (CSV + `if/elif`) — ótimo pro projeto social |
| `.../ex_33_estatisticas_de_temperaturas.py` | Estatísticas com listas — base do projeto de dados |
| `.../ex_43_lanchonete.py` | Lanchonete (caixa, troco) — dá para virar app do projeto final |
| `.../ex_44_eleicao_presidencial.py` | Eleicao (contagem de votos) - serve para o projeto social |
| `.../ex_26_urna_eletronica.py` | Urna eletrônica — debate ético perfeito |
| `lista-de-exercicios-python-brasil/secao_06_exercicios_strings/ex_09_validador_de_cpf_strings.py` | Validador de CPF (algoritmo clássico) |
| `python-do-zero/15_api_e_json/` | API + JSON (base do bot de notícias) |
| `python-do-zero/12_modulos/` | `import`, pacotes |
| `python-do-zero/13_programacao_orientada_objetos/` | Classes (base do `o_acolito`) |
| `tdm-app/` | Geração de dados de teste com Faker (dados falsos para o projeto final) |

---

## 🏠 Para casa

Escolher **3 exercícios novos** do banco (de seções que você ainda não fez) e resolver.
Comentar os exercícios resolvidos no `lista-de-exercicios-python-brasil` (se a escola
aceitar) — ou publicar no seu próprio repositório.

---

## 🔗 Próximo módulo

[B5 — Web: HTML, CSS e JavaScript](05-web.md)

# EX-S5 — Banco de Exercícios: SQL e Modelagem (14–17 anos)

**Trilha:** Adolescentes [B6 — Banco de Dados e SQL](../02-ADOLESCENTES-13-17/06-banco-de-dados-sql.md) ·
Adultos [04 — Dados e Planilhas](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md)

| Item | Descrição |
|---|---|
| **Faixa etária** | 14 a 17 anos (aproveitado como revisão para 18+) |
| **Nº de itens** | 18 — consulta (5), agrupamento e junção (5), subconsulta e alteração (5), constraints e normalização (3) |
| **Nível** | ⭐ Fácil (2 itens) · ⭐⭐ Médio (10 itens) · ⭐⭐⭐ Difícil (6 itens) |
| **Tempo estimado** | 80 a 100 min (4 a 6 min por item, mais 15 min de instalação do SQLite) |
| **Formato** | Enunciado com SQL e **gabarito com o SQL completo** de cada resposta |

> ⚠️ **Licença de uso:** material livre, sob a licença **CC BY 4.0** (Creative Commons
> Atribuição 4.0 Internacional). Você pode copiar, adaptar e redistribuir, desde que cite a
> autoria (Bruno Bertin Marquez) e indique as mudanças. Licença:
> https://creativecommons.org/licenses/by/4.0/

---

## 🎯 Objetivo

Ao final da atividade, o aluno será capaz de:

1. **Consultar** dados com `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` e `DISTINCT`.
2. **Agregar** com `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, `GROUP BY` e `HAVING`.
3. **Juntar** tabelas com `INNER JOIN` e `LEFT JOIN`, usando `ON` e `alias`.
4. **Alterar** dados com `INSERT`, `UPDATE` e `DELETE` — e entender o risco de cada um.
5. **Modelar**: escrever `CONSTRAINT`s, respeitar a **integridade referencial** e
   **normalizar** uma tabela até a 3ª Forma Normal.

**Objetivo secundário:** ler o resultado de uma consulta e dizer, em português, o que cada
linha retornada significa.

---

## 📚 Fontes no repositório

| Repositório | Pasta usada | O que foi aproveitado |
|---|---|---|
| `banco-de-dados-sql` | `01_o_que_e_banco_dados/` e `02_instalando_sqlite/` | Conceito de banco e uso do SQLite |
| `banco-de-dados-sql` | `03_tabelas_e_tipos/` e `04_inserindo_dados/` | Tipos, chaves primárias, `INSERT` |
| `banco-de-dados-sql` | `05_consultando_dados/` | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` |
| `banco-de-dados-sql` | `06_operadores_logicos/` | `AND`, `OR`, `BETWEEN`, `IN`, `LIKE` |
| `banco-de-dados-sql` | `07_funcoes_agregacao/` | `COUNT`, `SUM`, `AVG`, `GROUP BY`, `HAVING` |
| `banco-de-dados-sql` | `08_joins/` | `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, aliases, 3 tabelas |
| `banco-de-dados-sql` | `09_subqueries/` | Subconsultas com `IN` e `NOT IN` |
| `banco-de-dados-sql` | `10_atualizando_deletando/` | `UPDATE`, `DELETE` e cuidados de segurança |
| `banco-de-dados-sql` | `11_indices_e_performance/` | `CREATE INDEX` e `EXPLAIN` |
| `banco-de-dados-sql` | `12_modelagem_er/` | Entidades, relacionamentos, chaves e normalização |
| `banco-de-dados-sql` | `14_projeto_sistema_escolar/` | **Esquema real** de aluno, turma, disciplina, nota e matrícula usado como base deste banco |

**Ferramenta:** [DB Browser for SQLite](https://sqlitebrowser.org/) (grava e lê o arquivo
`escola.db`) ou o comando `sqlite3 escola.db` no terminal.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Tabela** | "Uma **planilha** com nome, colunas e regras." |
| **Chave primária** | "A **identidade** da linha. Não se repete." |
| **`FOREIGN KEY`** | "O **link** entre duas tabelas." |
| **`SELECT`** | "O que você quer **ver**." |
| **`WHERE`** | "Só as linhas que **passam no filtro**." |
| **`GROUP BY`** | "Junta linhas que são do **mesmo grupo**." |
| **`HAVING`** | "Filtra **depois** de agrupar." |
| **`INNER JOIN`** | "Só o que **existe nos dois lados**." |
| **`LEFT JOIN`** | "Tudo da **esquerda**, mesmo sem par na direita." |
| **`UNIQUE`** | "Não deixa **repetir**." |
| **`NOT NULL`** | "Não deixa **vazio**." |
| **`CHECK`** | "Não deixa **fora do intervalo**." |
| **1ª Forma Normal** | "Um valor por célula. Nada de lista escondida." |
| **3ª Forma Normal** | "Nada depende de nada, **só** da chave." |

---

## 🧩 Base de dados usada em todos os itens

Crie o arquivo `escola.db` e execute o script abaixo. Ele é uma **adaptação** do projeto
escolar do repositório (`banco-de-dados-sql/14_projeto_sistema_escolar/`, arquivos
`exercicio_01_criar_banco.txt` e `exercicio_02_povoar.txt`), com três mudanças em relação ao
original, feitas para este banco:

| Mudança | Original no repositório | Aqui |
|---|---|---|
| Tabela de matrícula | `aluno_turma` | `matricula`, com `id` próprio e `data_matricula` |
| Tabela `professor` | existe, ligada à `turma` | removida (não é usada por nenhum item) |
| Constraints | apenas chave primária e `NOT NULL` | `CHECK` na nota e `UNIQUE` em e-mail e matrícula |

Os **dados** (Ana, Bruno, Carla, David, as turmas 9A e 9B, as disciplinas e as notas) são os
mesmos do original, com **duas adições** que criam os casos de teste dos itens 9 e 10: a
aluna **Elisa Nunes** (sem matrícula) e a turma **10A** (com a Ana matriculada duas vezes).

```sql
-- Ativa a verificação das chaves estrangeiras (no SQLite ela é DESLIGADA por padrão)
PRAGMA foreign_keys = ON;

-- ===== Tabelas =====
CREATE TABLE aluno (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    data_nascimento TEXT,
    email TEXT UNIQUE
);

CREATE TABLE turma (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    ano INTEGER
);

CREATE TABLE matricula (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER NOT NULL REFERENCES aluno(id),
    turma_id INTEGER NOT NULL REFERENCES turma(id),
    data_matricula TEXT NOT NULL,
    UNIQUE (aluno_id, turma_id)
);

CREATE TABLE disciplina (
    id INTEGER PRIMARY KEY,
    nome TEXT UNIQUE NOT NULL
);

CREATE TABLE nota (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER NOT NULL REFERENCES aluno(id),
    disciplina_id INTEGER NOT NULL REFERENCES disciplina(id),
    valor REAL NOT NULL CHECK (valor >= 0 AND valor <= 10),
    UNIQUE (aluno_id, disciplina_id)
);

-- ===== Dados =====
INSERT INTO aluno (id, nome, data_nascimento, email) VALUES
    (1, 'Ana Souza',   '2008-05-14', 'ana@escola.com'),
    (2, 'Bruno Lima',  '2009-02-20', 'bruno@escola.com'),
    (3, 'Carla Melo',  '2008-11-03', 'carla@escola.com'),
    (4, 'David Reis',  '2009-07-30', 'david@escola.com'),
    (5, 'Elisa Nunes', '2008-02-11', 'elisa@escola.com');

INSERT INTO turma (id, nome, ano) VALUES
    (1, '9A', 2026),
    (2, '9B', 2026),
    (3, '10A', 2026);

INSERT INTO matricula (id, aluno_id, turma_id, data_matricula) VALUES
    (1, 1, 1, '2026-02-01'),
    (2, 2, 1, '2026-02-01'),
    (3, 3, 2, '2026-02-02'),
    (4, 4, 2, '2026-02-02'),
    (5, 1, 3, '2026-02-05');

INSERT INTO disciplina (id, nome) VALUES
    (1, 'Matemática'),
    (2, 'Português'),
    (3, 'História');

INSERT INTO nota (id, aluno_id, disciplina_id, valor) VALUES
    (1, 1, 1, 8.5),
    (2, 1, 2, 7.0),
    (3, 1, 3, 9.0),
    (4, 2, 1, 9.0),
    (5, 2, 2, 6.5),
    (6, 3, 1, 5.5),
    (7, 3, 2, 9.5),
    (8, 4, 1, 6.0),
    (9, 4, 2, 8.0);
```

**Resumo dos dados (guia de conferência):**

| Aluno | E-mail | Matrícula | Notas |
|---|---|---|---|
| Ana Souza (1) | ana@escola.com | 9A **e** 10A | Mat 8,5 · Port 7,0 · Hist 9,0 |
| Bruno Lima (2) | bruno@escola.com | 9A | Mat 9,0 · Port 6,5 |
| Carla Melo (3) | carla@escola.com | 9B | Mat 5,5 · Port 9,5 |
| David Reis (4) | david@escola.com | 9B | Mat 6,0 · Port 8,0 |
| Elisa Nunes (5) | elisa@escola.com | **sem matrícula** | **sem nota** |

> Dois detalhes que os itens exploram: a **Ana está em duas turmas** (por isso some duplicado
> em joins) e a **Elisa não tem matrícula** (por isso é o caso do `LEFT JOIN`).

---

## 📝 Bloco A — Consulta (1 a 5)

### Exercício 1 — Listar todos os alunos ⭐ · ⏱️ 3 min

Escreva a consulta que mostra **id, nome e e-mail** de todos os alunos, em **ordem alfabética
por nome**.

### Exercício 2 — Filtro, ordem e limite ⭐ · ⏱️ 3 min

Escreva a consulta que mostra o **nome e a data de nascimento** dos alunos **nascidos em
2008**, ordenados do **mais velho para o mais novo**, mostrando **no máximo 3 linhas**.

### Exercício 3 — `COUNT` e `DISTINCT` ⭐⭐ · ⏱️ 4 min

Escreva **duas** consultas:

1. quantos alunos existem na tabela `aluno`;
2. quantos **e-mails distintos** existem na tabela `aluno`.

### Exercício 4 — Funções de agregação ⭐⭐ · ⏱️ 4 min

Escreva uma consulta que mostre, sobre a tabela `nota`: a **quantidade** de notas, a **soma**,
a **média**, a **maior** e a **menor** nota.

### Exercício 5 — `GROUP BY` com contagem ⭐⭐ · ⏱️ 4 min

Escreva a consulta que mostra o **nome da turma** e **quantos alunos** ela tem, uma linha por
turma.

---

## 📝 Bloco B — Agrupamento e junções (6 a 10)

### Exercício 6 — `GROUP BY` com `HAVING` ⭐⭐ · ⏱️ 5 min

Escreva a consulta que mostra o **nome do aluno** e a **média** de suas notas, apenas para os
alunos cuja média for **maior ou igual a 7,5**, ordenados da maior média para a menor.

### Exercício 7 — `INNER JOIN` com duas tabelas ⭐⭐ · ⏱️ 5 min

Escreva a consulta que mostra o **nome do aluno** e o **nome da turma** em que ele está
matriculado.

### Exercício 8 — `INNER JOIN` com três tabelas ⭐⭐ · ⏱️ 5 min

Agora mostre também o **nome da disciplina** e o **valor da nota**, juntando quatro tabelas
(`aluno`, `matricula`, `nota` e `disciplina`). Ordene por nome do aluno e por nome da
disciplina.

### Exercício 9 — `LEFT JOIN` ⭐⭐⭐ · ⏱️ 6 min

Escreva a consulta que mostra **todos** os alunos, **inclusive** os que não têm matrícula, com
o nome da turma (ou um traço quando não houver).

### Exercício 10 — Junção com agregação ⭐⭐⭐ · ⏱️ 6 min

Escreva a consulta que mostra o **nome do aluno** e a **média de todas as suas notas**,
usando junção com `matricula` e `nota`.

> Atenção: a Ana está em **duas** turmas. Com essa junção, cada nota dela entra **duas
> vezes** no cálculo (uma por turma). O `AVG` sai certo por acaso — o `COUNT` não.

---

## 📝 Bloco C — Alias, subconsulta e alteração (11 a 15)

### Exercício 11 — Aliases ⭐⭐ · ⏱️ 4 min

Reescreva a consulta do exercício 7 usando **alias de tabela** (`aluno` como `a`, `matricula`
como `m`, `turma` como `t`) e **alias de coluna**, de modo que o resultado tenha os cabeçalhos
`aluno` e `turma`.

### Exercício 12 — Subconsulta com `NOT IN` ⭐⭐⭐ · ⏱️ 6 min

Escreva a consulta que lista os **alunos que não têm nota em História**, usando uma
**subconsulta** (e não um `JOIN`).

### Exercício 13 — `INSERT` ⭐⭐ · ⏱️ 4 min

Escreva o `INSERT` que **matricula a Elisa (id 5) na turma 9B (id 2)** com a data de matrícula
`2026-03-10`.

### Exercício 14 — `UPDATE` ⭐⭐ · ⏱️ 4 min

Escreva o `UPDATE` que **corrige o e-mail** da Ana para `ana.souza@escola.com`.

### Exercício 15 — `DELETE` ⭐⭐ · ⏱️ 4 min

Escreva o `DELETE` que **remove a matrícula do David (id 4) na turma 9B**. Escreva também o
comando que consulta **quantas** matrículas restaram na tabela.

---

## 📝 Bloco D — Constraints, integridade e normalização (16 a 18)

### Exercício 16 — Constraints do banco ⭐⭐⭐ · ⏱️ 6 min

Para cada situação abaixo, diga **qual constraint** deve ser usada e **o que acontece** se ela
faltar:

1. dois alunos com o **mesmo e-mail**;
2. uma nota com valor **12** (a escala vai de 0 a 10);
3. um aluno sem **nome**.

Escreva as **duas versões** do `CREATE TABLE nota`: uma sem constraints e uma com
`NOT NULL`, `CHECK` e `UNIQUE`.

### Exercício 17 — Integridade referencial ⭐⭐⭐ · ⏱️ 6 min

Tente inserir esta nota:

```sql
INSERT INTO nota (id, aluno_id, disciplina_id, valor)
VALUES (50, 99, 1, 7.5);
```

O `aluno_id` 99 **não existe** na tabela `aluno`. Explique o que o banco faz e o que
aconteceria se a tabela `nota` **não tivesse** a `FOREIGN KEY`.

> Antes de responder, confira se o `PRAGMA foreign_keys = ON;` está ativo no seu banco: no
> SQLite a verificação de chave estrangeira é **desligada por padrão**. Se ela estiver
> desligada, o `INSERT` vai passar — e esse é exatamente o defeito que o item quer mostrar.

### Exercício 18 — Normalização até a 3ª Forma Normal ⭐⭐⭐ · ⏱️ 10 min

A escola criou esta tabela "atalho", que parece resolver tudo de uma vez:

```sql
CREATE TABLE ficha (
    id INTEGER PRIMARY KEY,
    aluno_nome TEXT,
    aluno_email TEXT,
    turma_nome TEXT,
    turma_ano INTEGER,
    disciplina_nome TEXT,
    nota_valor REAL
);
```

Problemas: o mesmo aluno aparece **repetido** em várias linhas, o nome da turma se repete a
cada nota e qualquer correção de nome precisa ser feita em **todas** as linhas.

1. Identifique **duas** violações da 1ª Forma Normal ou da 2ª Forma Normal.
2. Proponha a **divisão** dessa tabela em tabelas menores (com as chaves estrangeiras).
3. Diga qual das **Formas Normais** (1FN, 2FN, 3FN) a tabela desnormalizada **viola** e por quê.

---

## ✅ Gabarito com o SQL completo

### 1 — Listar todos os alunos

```sql
SELECT id, nome, email
FROM aluno
ORDER BY nome;
```

### 2 — Filtro, ordem e limite

```sql
SELECT nome, data_nascimento
FROM aluno
WHERE data_nascimento LIKE '2008%'
ORDER BY data_nascimento ASC
LIMIT 3;
```

> `LIKE '2008%'` casa com tudo que **começa** com `2008`. Como a data está no formato
> `AAAA-MM-DD`, a comparação por texto já ordena do mais antigo para o mais novo — por isso
> `ASC` é explícito aqui.

### 3 — `COUNT` e `DISTINCT`

```sql
-- 1) total de alunos
SELECT COUNT(*) AS total_alunos FROM aluno;

-- 2) e-mails distintos
SELECT COUNT(DISTINCT email) AS e-mails_distintos FROM aluno;
```

> Resposta 1: **5**. Resposta 2: **5**. Hoje não há e-mail repetido, mas a coluna tem
> `UNIQUE`, então o número nunca pode passar de 5. `DISTINCT` é o filtro que remove
> repetição.

### 4 — Funções de agregação

```sql
SELECT
    COUNT(*) AS quantidade_notas,
    SUM(valor)  AS soma_notas,
    AVG(valor)  AS media_notas,
    MAX(valor)  AS maior_nota,
    MIN(valor)  AS menor_nota
FROM nota;
```

> Resposta esperada: quantidade **9**, soma **69**, média **7,67**, maior **9,5**, menor **5,5**.

### 5 — `GROUP BY` com contagem

```sql
SELECT t.nome AS turma, COUNT(m.id) AS alunos
FROM turma AS t
JOIN matricula AS m ON m.turma_id = t.id
GROUP BY t.id, t.nome
ORDER BY alunos DESC, t.nome;
```

> Resposta: 9A = 2, 9B = 2, 10A = 1. Usar `COUNT(m.id)` (e não `COUNT(*)`) conta só as
> matrículas que existem; a turma sem nenhuma matrícula apareceria com 0.

### 6 — `GROUP BY` com `HAVING`

```sql
SELECT a.nome AS aluno, AVG(n.valor) AS media
FROM aluno AS a
JOIN nota AS n ON n.aluno_id = a.id
GROUP BY a.id, a.nome
HAVING AVG(n.valor) >= 7.5
ORDER BY media DESC;
```

> Resposta: Ana 8,17 · Bruno 7,75 · Carla 7,50. David fica de fora (média 7,00).
> **Atenção:** `HAVING` filtra **depois** do agrupamento; `WHERE` filtraria as linhas antes de
> agrupar e não resolveria este caso.

### 7 — `INNER JOIN` com duas tabelas

```sql
SELECT a.nome AS aluno, t.nome AS turma
FROM aluno AS a
JOIN matricula AS m ON m.aluno_id = a.id
JOIN turma AS t ON t.id = m.turma_id
ORDER BY a.nome, t.nome;
```

> Resposta: Ana — 10A; Ana — 9A; Bruno — 9A; Carla — 9B; David — 9B.
> A Ana aparece **duas vezes** porque está matriculada em duas turmas: o `JOIN` devolve uma
> linha por **par** aluno-turma.

### 8 — `INNER JOIN` com quatro tabelas

```sql
SELECT a.nome AS aluno, d.nome AS disciplina, n.valor AS nota
FROM aluno AS a
JOIN nota AS n ON n.aluno_id = a.id
JOIN disciplina AS d ON d.id = n.disciplina_id
ORDER BY a.nome, d.nome;
```

> Resposta: 9 linhas (Ana 3, Bruno 2, Carla 2, David 2). Repare que `matricula` **não é
> necessária** aqui: o elo entre `aluno` e `nota` já existe. Junção a mais é consulta mais
> lenta.

### 9 — `LEFT JOIN`

```sql
SELECT a.nome AS aluno, COALESCE(t.nome, '—') AS turma
FROM aluno AS a
LEFT JOIN matricula AS m ON m.aluno_id = a.id
LEFT JOIN turma AS t ON t.id = m.turma_id
ORDER BY a.nome, t.nome;
```

> Resposta: Ana — 10A; Ana — 9A; Bruno — 9A; Carla — 9B; David — 9B; **Elisa — —**.
> A Elisa entra porque o `LEFT JOIN` **preserva** a tabela da esquerda. É o oposto do
> `INNER JOIN`, que só devolve o que tem par nos dois lados.

### 10 — Junção com agregação

```sql
SELECT a.nome AS aluno, AVG(n.valor) AS media
FROM aluno AS a
JOIN matricula AS m ON m.aluno_id = a.id
JOIN nota AS n ON n.aluno_id = a.id
GROUP BY a.id, a.nome
ORDER BY media DESC;
```

> Resposta: Ana 8,17 · Bruno 7,75 · Carla 7,50 · David 7,00.
>
> **O que acontece por baixo:** a Ana está em **duas** turmas, então cada uma das 3 notas
> dela entra **duas vezes** na conta — a consulta devolve 6 linhas para ela em vez de 3.
>
> **Atenção ao teste:** neste conjunto de dados a média da Ana **ainda sai certa** (8,17),
> porque cada nota foi repetida o mesmo número de vezes. Isso é **sorte**, não regra: se a
> Ana tivesse notas **diferentes** em cada turma, a média sairia distorcida, e um
> `COUNT` já contaria 6 notas em vez de 3. A forma **robusta** para este caso — a que
> junta **só** as tabelas que contam — é:

```sql
SELECT a.nome AS aluno, AVG(n.valor) AS media
FROM aluno AS a
JOIN nota AS n ON n.aluno_id = a.id
GROUP BY a.id, a.nome
ORDER BY media DESC;
```

> → Ana 8,17 · Bruno 7,75 · Carla 7,50 · David 7,00. A regra é: **agrupe pelas tabelas que
> você realmente quer contar** — uma junção desnecessária sempre multiplica as linhas.
>
> **Para o professor:** este item é a melhor oportunidade da aula para mostrar que o
> resultado "parece certo" e mesmo assim está errado. Peça que o aluno rode as **duas**
> consultas com `COUNT(*)` ao lado do `AVG`: a primeira devolve **6** notas para a Ana e a
> segunda devolve **3**. O `AVG` só não errou por acaso.

### 11 — Aliases

```sql
SELECT a.nome AS aluno, t.nome AS turma
FROM aluno AS a
JOIN matricula AS m ON m.aluno_id = a.id
JOIN turma AS t ON t.id = m.turma_id
ORDER BY aluno, turma;
```

> O alias de coluna (`AS aluno`) muda o **cabeçalho** da resultado; o alias de tabela
> (`FROM aluno AS a`) encurta o código e evita repetir o nome da tabela em cada coluna.

### 12 — Subconsulta com `NOT IN`

```sql
SELECT nome
FROM aluno
WHERE id NOT IN (
    SELECT n.aluno_id
    FROM nota AS n
    JOIN disciplina AS d ON d.id = n.disciplina_id
    WHERE d.nome = 'História'
)
ORDER BY nome;
```

> Resposta: Bruno Lima, Carla Melo, David Reis, Elisa Nunes.
> **Armadilha clássica:** `NOT IN` devolve **nada** se a subconsulta tiver algum `NULL`.
> Com `NOT EXISTS` ou com `LEFT JOIN ... WHERE ... IS NULL` esse risco desaparece.

### 13 — `INSERT`

```sql
INSERT INTO matricula (id, aluno_id, turma_id, data_matricula)
VALUES (6, 5, 2, '2026-03-10');
```

> Como `matricula.id` é `INTEGER PRIMARY KEY`, o SQLite preenche o valor automaticamente se
> você **omitir** a coluna `id`:
> `INSERT INTO matricula (aluno_id, turma_id, data_matricula) VALUES (5, 2, '2026-03-10');`
> A constraint `UNIQUE (aluno_id, turma_id)` impede matricular a mesma pessoa duas vezes
> **na mesma turma**.

### 14 — `UPDATE`

```sql
UPDATE aluno
SET email = 'ana.souza@escola.com'
WHERE id = 1;
```

> **Sempre** use `WHERE`. Sem ele, o `UPDATE` muda **todas** as linhas da tabela — é o erro
> mais caro do SQL.

### 15 — `DELETE`

```sql
DELETE FROM matricula
WHERE aluno_id = 4 AND turma_id = 2;

SELECT COUNT(*) AS matriculas_restantes FROM matricula;
```

> Resposta: restam **4** matrículas. Pelo mesmo motivo do `UPDATE`, `DELETE` sem `WHERE`
> apaga a tabela inteira. Para "desfazer" uma tabela apagada, é preciso o **backup**.

### 16 — Constraints do banco

**1) E-mail repetido → `UNIQUE`.** Sem essa constraint, dois alunos poderiam ter o mesmo
e-mail e o login ficaria ambíguo.

**2) Nota 12 → `CHECK (valor >= 0 AND valor <= 10)`.** Sem essa constraint, o banco aceitaria
qualquer número.

**3) Aluno sem nome → `NOT NULL`.** Sem essa constraint, o banco aceitaria `NULL` no lugar do
nome.

```sql
-- Versão SEM constraints
CREATE TABLE nota (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER,
    disciplina_id INTEGER,
    valor REAL
);

-- Versão COM constraints
CREATE TABLE nota (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER NOT NULL REFERENCES aluno(id),
    disciplina_id INTEGER NOT NULL REFERENCES disciplina(id),
    valor REAL NOT NULL CHECK (valor >= 0 AND valor <= 10),
    UNIQUE (aluno_id, disciplina_id)
);
```

> Ao tentar gravar um valor que viola uma constraint, o banco **rejeita a operação** e
> mostra o erro — os dados válidos continuam intactos.

### 17 — Integridade referencial

```sql
INSERT INTO nota (id, aluno_id, disciplina_id, valor)
VALUES (50, 99, 1, 7.5);
```

> **O que o banco faz:** rejeita o `INSERT` com a mensagem
> `FOREIGN KEY constraint failed` (SQLite) ou `violates foreign key constraint` (PostgreSQL,
> MySQL). Nada é gravado: a tabela `nota` continua com 9 linhas.
>
> **Atenção, professor — este é o detalhe que o aluno vai errar:** o SQLite **não verifica
> chave estrangeira por padrão**. Antes de rodar o item, garanta que o `PRAGMA
> foreign_keys = ON;` está ativo (o comando já está no script do topo deste arquivo). Sem
> ele, o `INSERT` é **aceito** e a nota fica órfã, apontando para o aluno 99 que não existe —
> o próprio defeito que o item 17 quer ensinar. Se o aluno estiver usando o
> [DB Browser for SQLite](https://sqlitebrowser.org/), a opção **"Aplicar restrições de
> chaves estrangeiras"** fica nas preferências do banco.
>
> **Se a `FOREIGN KEY` não existisse:** o `INSERT` seria aceito e a nota ficaria "órfã",
> apontando para o aluno 99 que não existe. O erro apareceria **depois**, no relatório — ou
> nunca apareceria. É exatamente o tipo de sujeira que a constraint impede.

### 18 — Normalização até a 3ª Forma Normal

**1) As violações:**

- **1ª Forma Normal:** a tabela **está** em 1FN — cada célula guarda um único valor e não há
  lista escondida. O problema real é a **redundância**: o mesmo aluno, a mesma turma e a mesma
  disciplina aparecem repetidos em várias linhas.
- **2ª Forma Normal:** a chave primária é `id`, mas os dados do aluno (`aluno_nome`,
  `aluno_email`) e da turma (`turma_nome`, `turma_ano`) **dependem da chave** por meio de um
  atributo não-chave. Como o resultado é o mesmo para todas as linhas do mesmo aluno, isso é
  **dependência parcial** — **violação da 2FN**.
- **3ª Forma Normal:** por cima disso, `aluno_email` depende de `aluno_nome`, e não da chave:
  `id → aluno_nome → aluno_email`. É uma **dependência transitiva** — **violação da 3FN**.

> Nota do professor: o enunciado convida a apontar 1FN e 2FN; a resposta tecnicamente correta
> é: a tabela **está** em 1FN, **viola a 2FN** (dependência parcial) e **viola a 3FN**
> (dependência transitiva). Respostas que dizem "viola a 1FN porque repete dados" são aceitas
> quando o aluno justifica a **redundância** e a necessidade de **atualizar o mesmo dado em
> vários lugares** (anomalia de atualização).

**2) A divisão proposta:**

```sql
CREATE TABLE aluno (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    email TEXT UNIQUE
);

CREATE TABLE turma (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    ano INTEGER
);

CREATE TABLE disciplina (
    id INTEGER PRIMARY KEY,
    nome TEXT UNIQUE NOT NULL
);

CREATE TABLE matricula (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER NOT NULL REFERENCES aluno(id),
    turma_id INTEGER NOT NULL REFERENCES turma(id),
    UNIQUE (aluno_id, turma_id)
);

CREATE TABLE nota (
    id INTEGER PRIMARY KEY,
    aluno_id INTEGER NOT NULL REFERENCES aluno(id),
    disciplina_id INTEGER NOT NULL REFERENCES disciplina(id),
    valor REAL NOT NULL CHECK (valor >= 0 AND valor <= 10),
    UNIQUE (aluno_id, disciplina_id)
);
```

**3) Conclusão:** o modelo final está na **3ª Forma Normal** — cada fato mora em **uma**
tabela e cada tabela depende **só** da sua chave primária:

| Dado | Tabela | Depende de |
|---|---|---|
| Nome e e-mail do aluno | `aluno` | `aluno.id` |
| Nome e ano da turma | `turma` | `turma.id` |
| Nome da disciplina | `disciplina` | `disciplina.id` |
| Quem está em qual turma | `matricula` | `aluno_id`, `turma_id` |
| Valor da nota | `nota` | `aluno_id`, `disciplina_id` |

> **Ganho concreto:** corrigir o nome de um aluno passa a ser **um** `UPDATE`, e não um por
> linha repetida — e a anomalia de atualização simplesmente deixa de existir.

---

## 🏆 Desafio bônus (não conta nos 18 itens)

```sql
-- Índice que acelera a busca por nome
CREATE INDEX idx_aluno_nome ON aluno(nome);

-- Veja o plano de execução antes e depois
EXPLAIN QUERY PLAN
SELECT id, nome FROM aluno WHERE nome = 'Ana Souza';
```

> O plano mostra `SEARCH` (busca pelo índice) em vez de `SCAN` (varrer a tabela inteira).
> Regra prática: indexe colunas muito usadas em `WHERE` e `ORDER BY`.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Prova de SQL | 12 ou mais acertos em 18 |
| Itens 9 e 10 | O aluno **explica** a diferença entre `INNER` e `LEFT JOIN` e a armadilha da duplicação |
| Itens 16 a 18 | O aluno justifica a **integridade** em linguagem simples |
| Consultas executadas | Toda consulta do gabarito roda no SQLite sem erro |

**Pergunta de escrita:**
> "Por que o `DELETE` sem `WHERE` é considerado perigoso?"
> **Resposta:** porque ele apaga **todas** as linhas da tabela de uma vez, sem chance de
> desfazer. Por isso o `WHERE` é obrigatório na prática e o comando precisa de **backup** e de
> **permissão** controlada (em produção, os comandos de `DELETE` e `UPDATE` costumam ser
> bloqueados para o usuário comum).

---

## 🏠 Para casa

Refaça o item 10 **de três formas** diferentes e compare os resultados: (a) com `JOIN`
nas três tabelas; (b) só com `aluno` e `nota`; (c) com uma **subconsulta** que calcula a
média. Escreva em uma frase qual forma é a **mais correta** e **por quê**.

---

## 🔗 Próximo módulo

[EX-Q6 — Banco de Exercícios: QA e Testes (13–17 anos)](06-exercicios-qa.md)

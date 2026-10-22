# B6 — Banco de Dados e SQL (13–17 anos)

**Duração:** 90 min · **Aula 6 de 16**

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. **Modelar** um banco relacional: criar tabelas com `CREATE TABLE`, tipos de dados, `PRIMARY KEY`, `NOT NULL`, `UNIQUE` e `FOREIGN KEY`.
2. **Popular** o banco com `INSERT` e alterar com `UPDATE` e `DELETE` de forma segura (sempre com `WHERE`).
3. **Escrever 10 consultas** que respondem perguntas reais de negócio usando `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY` e `JOIN`.
4. **Executar e ler** as consultas em uma ferramenta visual: [DB Browser for SQLite](https://sqlitebrowser.org/) (grátis, Windows/Linux/Mac) ou [Visualg](https://visualg3.com.br/).
5. **Explicar** a diferença entre **dado** e **informação** — e por que isso muda o valor do que você construiu.

**Objetivo secundário:** Dizer, em uma frase cada, o que é chave primária, chave estrangeira, índice e integridade referencial.

---

## 📚 Fontes no repositório

`banco-de-dados-sql/` — **15 módulos × 6 exercícios = 90 arquivos `.txt`**, todos com bloco **"RESPOSTAS ESPERADAS"** e **"DICA"** (conferido nos arquivos do repositório):

| Módulo | Conteúdo | Exercícios |
|---|---|---|
| `01_o_que_e_banco_dados` | Conceitos, tipos de dado, SGBDs, relacional × NoSQL | 6 |
| `02_instalando_sqlite` | Instalação, terminal, primeiro script, ponto e vírgula | 6 |
| `03_tabelas_e_tipos` | `CREATE TABLE`, tipos, constraints (`NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `DEFAULT`, `CHECK`), `ALTER TABLE`, `DROP TABLE` | 6 |
| `04_inserindo_dados` | `INSERT`, `VALUES`, múltiplas linhas, `DEFAULT`, omissão de colunas | 6 |
| `05_consultando_dados` | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, apelidos (`alias`) | 6 |
| `06_operadores_logicos` | `AND`, `OR`, `NOT`, `BETWEEN`, `IN`, `LIKE` | 6 |
| `07_funcoes_agregacao` | `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`, `GROUP BY`, `HAVING` | 6 |
| `08_joins` | `INNER`, `LEFT`, `RIGHT`, junção de 3 tabelas | 6 |
| `09_subqueries` | Subconsulta escalar, `IN`, `EXISTS`, `ANY`, `ALL` | 6 |
| `10_atualizando_deletando` | `UPDATE`, `DELETE`, segurança, transações | 6 |
| `11_indices_e_performance` | `CREATE INDEX`, quando indexar, `EXPLAIN QUERY PLAN` | 6 |
| `12_modelagem_er` | Entidades, relacionamentos, chaves, normalização | 6 |
| `13_sqlite_com_python` | `sqlite3`: o mesmo banco lido pelo Python | 6 |
| `14_projeto_sistema_escolar` | Schema de escola + 4 relatórios prontos | 6 |
| `15_projeto_ecommerce` | Schema de loja + 3 relatórios prontos | 6 |

**Dois schemas completos já prontos no repo (copie e adapte):**
- `banco-de-dados-sql/14_projeto_sistema_escolar/README.md` — tabelas `aluno`, `professor`, `disciplina`, `turma`, `aluno_turma` (N:N) e `nota`, com 4 consultas de relatório prontas.
- `banco-de-dados-sql/15_projeto_ecommerce/README.md` — tabelas `cliente`, `categoria`, `produto`, `pedido` e `item_pedido`, com 3 relatórios prontos.

**Trilha web e slides:**
`laboratorio-tech-social/site/trilhas/adolescentes/04-dados.html` ·
`laboratorio-tech-social/materiais/slides/aula-teens-04-dados.html` ·
`laboratorio-tech-social/site/exercicios/gerador-dados.html` ·
`laboratorio-tech-social/site/exercicios/visualizador-dados.html` ·
`laboratorio-tech-social/trilhas/adolescentes-13-20/modulo-04-ciencia-dados.md`

**Ferramentas da aula:**
[DB Browser for SQLite](https://sqlitebrowser.org/) — editor visual, abre e salva o arquivo `.db` sem terminal ·
[Visualg](https://visualg3.com.br/) — o fluxograma em português da aula 02, para quem quiser desenhar o algoritmo antes de digitar o SQL ·
`sqlite3` no terminal — o caminho do repo no módulo `02_instalando_sqlite`.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Dado** | "O fato cru, sozinho: **14**." |
| **Informação** | "O dado com contexto e propósito: **Ana, 14 anos, 9ª série, média 8,5**." |
| **SGBD** | "O programa que guarda os dados e responde perguntas sobre eles (SQLite, MySQL, PostgreSQL)." |
| **Tabela** | "Uma planilha **com regras**: linhas = registros, colunas = campos." |
| **Chave primária** | "A coluna que dá identidade única à linha. Sem ela, o banco não sabe o que é 'o mesmo registro'." |
| **Chave estrangeira** | "O ponteiro que liga uma tabela a outra." |
| **Integridade referencial** | "O banco **recusa** apontar para um registro que não existe." |
| **`NOT NULL` / `UNIQUE` / `CHECK`** | "As regras que o banco impõe para os dados não saírem do controle." |
| **`SELECT` + `WHERE`** | "Puxar só o que interessa." |
| **`GROUP BY` + agregação** | "Juntar linhas parecidas e **resumir**." |
| **`JOIN`** | "Trazer a informação de **duas** tabelas ao mesmo tempo." |
| **Índice** | "O sumário do livro: acha a linha sem ler o livro inteiro." |
| **Normalização** | "Separar para não repetir: **um dado, um lugar só**." |
| **`UPDATE`/`DELETE` sem `WHERE`** | "O botão de formatar tudo sem querer." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Todo mundo aqui já comprou alguma coisa online. O que o site fez por baixo? Não foi 'achar na internet'. Foi **perguntar ao banco de dados**. 'Meus pedidos', 'o que está disponível', 'quanto eu gastei' — cada uma dessas telas é uma frase em SQL escrita por alguém."*

**Demonstração ao vivo (5 min):** abra o [DB Browser for SQLite](https://sqlitebrowser.org/), crie o arquivo `loja.db` e rode:

```sql
SELECT nome, preco, estoque FROM produto ORDER BY preco DESC;
```

Depois troque `DESC` por `ASC` e adicione `WHERE estoque > 0`. Diga: *"Isso não é programação. É uma pergunta feita em português quase literal."*

**Dado × informação (3 min):** escreva `14` no quadro. Pergunte: *"Isso é dado ou informação?"* (Dado.) Agora escreva *"Ana, 14 anos, 9ª série, 3 faltas em março"* — (Informação.) Feche: *"Informação é dado com contexto e propósito para uma decisão. Você vai passar a aula construindo a máquina que faz essa transformação."*

### Fase 2 — Exploração (25 min)

**Parte 1 — O schema (10 min).** Projete no editor de SQL do DB Browser:

```sql
-- O SQLite vem com a chave estrangeira DESLIGADA: ligue em toda conexão
PRAGMA foreign_keys = ON;

-- Quem compra
CREATE TABLE cliente (
    id     INTEGER PRIMARY KEY AUTOINCREMENT,
    nome   TEXT    NOT NULL,
    email  TEXT    NOT NULL UNIQUE,
    cidade TEXT,
    criado_em TEXT NOT NULL DEFAULT (datetime('now'))
);

-- Classificação dos produtos
CREATE TABLE categoria (
    id   INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT    NOT NULL UNIQUE
);

-- O que é vendido
CREATE TABLE produto (
    id           INTEGER PRIMARY KEY AUTOINCREMENT,
    nome         TEXT    NOT NULL,
    preco        REAL    NOT NULL CHECK (preco >= 0),
    estoque      INTEGER NOT NULL DEFAULT 0 CHECK (estoque >= 0),
    categoria_id INTEGER REFERENCES categoria(id)
);

-- Cada compra
CREATE TABLE pedido (
    id         INTEGER PRIMARY KEY AUTOINCREMENT,
    cliente_id INTEGER NOT NULL REFERENCES cliente(id),
    data       TEXT    NOT NULL,
    status     TEXT    NOT NULL DEFAULT 'pendente'
);

-- Junção N:N: um pedido tem vários produtos, um produto está em vários pedidos
CREATE TABLE item_pedido (
    pedido_id      INTEGER NOT NULL REFERENCES pedido(id),
    produto_id     INTEGER NOT NULL REFERENCES produto(id),
    quantidade     INTEGER NOT NULL CHECK (quantidade > 0),
    preco_unitario REAL    NOT NULL CHECK (preco_unitario >= 0),
    PRIMARY KEY (pedido_id, produto_id)
);
```

Explique um por um:
- `PRIMARY KEY` — identifica a linha. No SQLite, `INTEGER PRIMARY KEY` **já** numera sozinho (é apelido do `rowid`); `AUTOINCREMENT` adiciona a garantia extra de que **o número nunca é reutilizado**, nem depois de um `DELETE`.
- `NOT NULL` — a coluna é obrigatória.
- `UNIQUE` — dois registros não podem ter o mesmo valor nessa coluna (o `email` do cliente).
- `DEFAULT` — valor automático quando o campo é omitido (`status = 'pendente'`, `estoque = 0`).
- `CHECK` — regra de negócio escrita dentro do banco (`preco >= 0`, `quantidade > 0`).
- `REFERENCES` — a chave estrangeira: o ponteiro para a outra tabela.

**Parte 2 — Povoamento (5 min).**

```sql
INSERT INTO cliente (nome, email, cidade) VALUES
    ('Ana Souza',  'ana@email.com',  'São Paulo'),
    ('Bruno Lima', 'bruno@email.com', 'Rio de Janeiro'),
    ('Carla Melo', 'carla@email.com', 'Belo Horizonte');

INSERT INTO categoria (nome) VALUES
    ('Eletrônicos'), ('Livros'), ('Vestuário');

INSERT INTO produto (nome, preco, estoque, categoria_id) VALUES
    ('Fone de ouvido', 149.90, 25, 1),
    ('Mouse',          49.90, 40, 1),
    ('Livro de SQL',   69.00, 30, 2),
    ('Camiseta',       39.90, 25, 3),
    ('Caderno',        19.90, 20, 2);

INSERT INTO pedido (cliente_id, data, status) VALUES
    (1, '2026-03-02', 'entregue'),
    (2, '2026-03-05', 'pendente'),
    (1, '2026-03-11', 'entregue'),
    (3, '2026-03-14', 'pendente');

INSERT INTO item_pedido (pedido_id, produto_id, quantidade, preco_unitario) VALUES
    (1, 1, 1, 149.90),
    (1, 2, 2,  49.90),
    (2, 3, 1,  69.00),
    (3, 4, 3,  39.90),
    (4, 1, 1, 149.90);
```

**Parte 3 — As quatro famílias de consulta (6 min).**

```sql
-- 1) Ler: SELECT + WHERE + ORDER BY
SELECT nome, preco FROM produto WHERE estoque > 0 ORDER BY preco DESC;

-- 2) Contar: COUNT + GROUP BY
SELECT status, COUNT(*) AS total_pedidos
FROM pedido
GROUP BY status;

-- 3) Somar: SUM + GROUP BY + HAVING
SELECT c.nome, SUM(ip.quantidade * ip.preco_unitario) AS total
FROM cliente c
JOIN pedido p       ON p.cliente_id = c.id
JOIN item_pedido ip ON ip.pedido_id = p.id
GROUP BY c.nome
HAVING total >= 100;

-- 4) Juntar: JOIN e LEFT JOIN
SELECT c.nome, COUNT(p.id) AS pedidos
FROM cliente c
LEFT JOIN pedido p ON p.cliente_id = c.id
GROUP BY c.nome;
```

Explique a diferença que mais trava: **`WHERE` filtra linhas antes de agrupar; `HAVING` filtra os grupos depois de agrupar.**

**Parte 4 — Integridade referencial, índice e normalização (4 min).**

```sql
-- Isto FALHA: o cliente 99 não existe
INSERT INTO pedido (cliente_id, data) VALUES (99, '2026-04-01');
-- Erro: FOREIGN KEY constraint failed
```

```sql
-- Índice para as colunas que mais aparecem em WHERE e JOIN
CREATE INDEX idx_pedido_cliente ON pedido(cliente_id);
CREATE INDEX idx_item_pedido_produto ON item_pedido(produto_id);

-- Compare o plano de execução antes e depois do índice
EXPLAIN QUERY PLAN SELECT * FROM pedido WHERE cliente_id = 1;
-- Sem índice: SCAN pedido          (lê tudo)
-- Com índice: SEARCH pedido USING INDEX idx_pedido_cliente
```

Normalização em duas linhas (o repo tem o estudo completo em `banco-de-dados-sql/12_modelagem_er/exercicio_04_normalizacao.txt`):

```sql
-- RUIM: o estado se repete em toda linha e pode ficar inconsistente
CREATE TABLE cliente (id INTEGER PRIMARY KEY, nome TEXT, cidade TEXT, estado TEXT);

-- BOM (3FN): cada dado mora em um lugar só
CREATE TABLE cidade (id INTEGER PRIMARY KEY, nome TEXT NOT NULL, estado TEXT NOT NULL);
CREATE TABLE cliente (id INTEGER PRIMARY KEY, nome TEXT NOT NULL, cidade_id INTEGER REFERENCES cidade(id));
```

### Fase 3 — Mão na massa (35 min)

**Atividade A — Montar o schema (12 min).**
No [DB Browser for SQLite](https://sqlitebrowser.org/), crie `loja.db` e:
1. Execute o `PRAGMA foreign_keys = ON;` **e o schema da Parte 1**.
2. Execute o povoamento da Parte 2.
3. Confira com `SELECT * FROM produto;` e com o botão **"Verificar estrutura do banco"**.

**Atividade B — As 10 consultas do projeto (18 min).**
Cada dupla escreve **10 consultas numeradas**, cada uma com a **pergunta de negócio escrita por cima**. Modelos prontos:

```sql
-- Consulta 1 — Quais produtos existem e de que categoria são?
SELECT p.nome, c.nome AS categoria, p.preco
FROM produto p
JOIN categoria c ON c.id = p.categoria_id
ORDER BY p.nome;

-- Consulta 2 — Quanto cada cliente gastou no total?
SELECT c.nome, SUM(ip.quantidade * ip.preco_unitario) AS total
FROM cliente c
JOIN pedido p       ON p.cliente_id = c.id
JOIN item_pedido ip ON ip.pedido_id = p.id
GROUP BY c.nome
ORDER BY total DESC;
```

As outras 8 (com a dica de qual comando usar):

| # | Pergunta | Dica |
|---|---|---|
| 3 | Quais produtos estão quase esgotando? | `WHERE` + `ORDER BY` |
| 4 | Quais clientes já compraram alguma vez? | `JOIN` + `DISTINCT` |
| 5 | Quais clientes **nunca** compraram? | `LEFT JOIN` + `IS NULL` |
| 6 | Quais são os 3 produtos mais vendidos? | `GROUP BY` + `ORDER BY` + `LIMIT` |
| 7 | Qual é o preço médio de cada categoria? | `AVG` + `GROUP BY` |
| 8 | Quantos pedidos existem em cada status? | `COUNT` + `GROUP BY` |
| 9 | Quais pedidos o cliente Ana fez, com o valor de cada item? | `WHERE` + `JOIN` de 3 tabelas |
| 10 | Quais produtos começam com a letra "C"? | `LIKE` |

**Atividade C — 3 exercícios do repo (5 min).**
Escolha 3 entre:
- `banco-de-dados-sql/03_tabelas_e_tipos/exercicio_03_constraints.txt` — constraints
- `banco-de-dados-sql/08_joins/exercicio_05_join_3_tabelas.txt` — JOIN de 3 tabelas
- `banco-de-dados-sql/12_modelagem_er/exercicio_04_normalizacao.txt` — normalização
- `banco-de-dados-sql/11_indices_e_performance/exercicio_04_explain.txt` — `EXPLAIN`

Cada arquivo `.txt` traz **"RESPOSTAS ESPERADAS"** e **"DICA"**. Cole a resposta esperada como comentário no seu arquivo `.sql` e confirme que a consulta devolve o mesmo resultado.

### Fase 4 — Projeto (15 min)

**Desafio: "O banco de dados do projeto da turma"**

Entregáveis (2 arquivos na pasta `data/` do repositório da turma):
- `schema.sql` — o `CREATE TABLE` completo com constraints + o `INSERT` de povoamento
- `consultas.sql` — as 10 consultas numeradas e comentadas

Use o domínio real do projeto final (aula 13): biblioteca comunitária, loja solidária, agenda de oficinas, rede de apoio… O schema da aula serve de **modelo**, não de resposta final.

**Critério de pronto:**
- [ ] `schema.sql` roda do zero (no DB Browser ou com `sqlite3 loja.db < schema.sql`) **sem erro**
- [ ] Pelo menos **4 tabelas**, com **1 chave primária composta** e **1 ou mais chaves estrangeiras**
- [ ] As **10 consultas** numeradas, cada uma com a pergunta escrita por cima
- [ ] Pelo menos **1 `JOIN` de 3 tabelas** e **1 `GROUP BY` com `HAVING`**
- [ ] **1 índice** criado e o `EXPLAIN QUERY PLAN` mostrando `SEARCH` (não `SCAN`)
- [ ] **Nenhum `UPDATE`/`DELETE` sem `WHERE`**
- [ ] Nenhum dado pessoal real de aluno (ver `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §9)

### Fase 5 — Mostra (5 min)

Abra 2 bancos no projetor. Cada dupla mostra **1 consulta** e responde: *"Que decisão de negócio essa consulta toma?"*

**Pergunta de saída:** "Por que `DELETE FROM pedido;` é perigoso e `DELETE FROM pedido WHERE status = 'cancelado';` não é?"

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| `schema.sql` | Roda do zero; 4+ tabelas; chave primária composta e chave estrangeira presentes |
| `consultas.sql` (10) | Cada consulta responde a pergunta escrita; 1 JOIN de 3 tabelas; 1 GROUP BY + HAVING |
| 3 exercícios do repo | Bloco "RESPOSTAS ESPERADAS" conferido arquivo a arquivo |
| Índice | `EXPLAIN QUERY PLAN` mostra `SEARCH` em vez de `SCAN` |
| Compreensão oral | Aluno explica dado × informação e o papel da chave estrangeira |
| Higiene do SQL | Nenhum `UPDATE`/`DELETE` sem `WHERE`; nenhum dado pessoal real |

**Pergunta de escrita:**
> "Na tabela `pedido` existe a coluna `cliente_id` com `REFERENCES cliente(id)`. O que acontece
> se alguém tentar inserir um pedido com `cliente_id = 99`, sabendo que o cliente 99 não existe?
> E por que isso é melhor do que o banco aceitar o valor?"
> **Resposta:** Com `PRAGMA foreign_keys = ON;` ativo, o banco **recusa** a inserção e devolve
> o erro `FOREIGN KEY constraint failed`. Isso é a **integridade referencial**: o banco garante
> que todo pedido aponta para um cliente que realmente existe. Sem essa trava, o banco aceitaria
> "pedidos órfãos" e o erro só apareceria semanas depois, no relatório — o `JOIN` devolveria
> linhas sem cliente e o total do cliente sumiria do resultado. O banco não é só um lugar
> que guarda dados: é um lugar que **recusa dados errados**.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `banco-de-dados-sql/05_consultando_dados/` | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, apelidos |
| `banco-de-dados-sql/07_funcoes_agregacao/` | `COUNT`, `SUM`, `AVG`, `GROUP BY`, `HAVING` |
| `banco-de-dados-sql/09_subqueries/` | Subconsultas e `EXISTS` (nível avançado) |
| `banco-de-dados-sql/11_indices_e_performance/` | `CREATE INDEX` e `EXPLAIN QUERY PLAN` |
| `banco-de-dados-sql/12_modelagem_er/` | Normalização (1FN, 2FN, 3FN) e diagrama ER |
| `banco-de-dados-sql/13_sqlite_com_python/` | `sqlite3`: ler e escrever no mesmo banco pelo Python |
| `banco-de-dados-sql/14_projeto_sistema_escolar/` | Schema de escola com 4 relatórios prontos |
| `banco-de-dados-sql/15_projeto_ecommerce/` | Schema de loja com 3 relatórios prontos |
| `laboratorio-tech-social/site/exercicios/gerador-dados.html` | Gerar dados fictícios para povoar o banco |
| `laboratorio-tech-social/site/exercicios/visualizador-dados.html` | Visualizar e filtrar dados no navegador |

---

## 🏠 Para casa

1. Instale o [DB Browser for SQLite](https://sqlitebrowser.org/) em casa e abra o `loja.db` que você exportou da aula.
2. Reescreva **3 das 10 consultas** como perguntas do **projeto final** (aula 13) e deixe as SQL prontas no arquivo `consultas.sql`.
3. (Opcional) Desenhe o fluxo de uma consulta no estilo [Visualg](https://visualg3.com.br/) — da aula 02 — usando a sequência *ler → filtrar → agrupar → ordenar → apresentar*, e depois traducione para SQL.

---

## 🔗 Próximo módulo

[B7 — Git e GitHub](07-git-github.md)

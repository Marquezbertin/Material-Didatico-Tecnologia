# Módulo 2 — Python para Automatizar a Rotina (18+)

**Duração:** 90 min · **Aula 3 de 16** (módulo em 2 aulas: 03 e 04)

**Entregável do módulo:** **1 script real rodando + teste automatizado**.

---

## 🎯 Objetivo

Ao final do módulo, o aluno será capaz de:

1. Explicar **por que Python** e não outra linguagem para automatizar a rotina
   (curva de aprendizado, biblioteca padrão enorme, é a língua da automação de dados).
2. Preparar um **ambiente isolado**: interpretador, `venv`, `requirements.txt` — ou
   [Google Colab](https://colab.research.google.com/) quando não se pode instalar nada.
3. Escrever um **script confiável**, com as 5 regras: uma tarefa por execução, log,
   falha explícita, backup antes de operação destrutiva e `--dry-run`.
4. Manipular **arquivos e pastas** com `pathlib`, sem concatenar caminho na mão.
5. Ler e gravar **CSV** (`csv.DictReader`, `csv.writer`), **planilhas** (`openpyxl`) e
   **JSON** (`json`).
6. Fazer **requisições HTTP** com `requests`, `timeout` obrigatório e tratamento de erro.
7. Dar **interface de linha de comando** ao script com `argparse`.
8. Escrever **testes automatizados** com `unittest` (padrão da biblioteca, sem instalar nada).
9. **Agendar** o script (`cron` no Linux/macOS, `schtasks` no Windows) e configurar
   `logging` para arquivo e tela.

**Objetivo secundário:** Reconhecer, num código alheio, as 5 marcas de um script que vai
quebrar de madrugada.

---

## 📚 Fontes no repositório

| Fonte real | O que usar nesta aula |
|---|---|
| `python-do-zero/` | **15 módulos × 6 exercícios = 90 exercícios** em `.txt`, com bloco **"Resposta Esperada"**. Módulos-chave para a aula: `10_arquivos/` (escrever, ler, `append`, `with`, **CSV**), `15_api_e_json/` (`json.dump`, JSON em arquivo, `requests` básico, consumo de API), `11_tratamento_erros/`, `12_modulos/` |
| `manual-qa-completo/docs/03/scripts/estimate.py` | Script real de referência: `from __future__ import annotations`, funções com `docstring`, tipagem, e um bloco `if __name__ == "__main__":` — **o padrão profissional** |
| `manual-qa-completo/run_all.py` | O padrão de **código de saída**: `return 1 if failures else 0`, execução por `subprocess.run(..., check=True)` e contagem de falhas |
| `manual-qa-completo/docs/11/scripts/secret_scan.py` | Varredura de segredos em repositório (módulo 05 vai reaproveitar) |
| `qa-automation-framework/` | Estrutura de projeto profissional: `requirements.txt` fixado (`pytest==8.3.3`, `requests==2.32.3`, `PyYAML==6.0.2`), `pyproject.toml`, `config/config.yaml`, `utils/data_generator.py` com `Faker` (dados falsos) |
| `Central-de-noticias/requirements.txt` | Exemplo real de dependências mínimas (`requests`, `feedparser`, `trafilatura`, `edge-tts`) |
| `Analise-de-Dados/` | 7 datasets reais para treinar CSV e XLSX: `datasets/Gapminder.csv`, `AdventureWorks.xlsx`, `Aracaju.xlsx`, `Fortaleza.xlsx`, `Natal.xlsx`, `Recife.xlsx`, `Salvador.xlsx` |
| `agente_qaIA/scripts/create_sample_db.py` | Script real que **cria um banco de dados de demonstração** — o modelo de "gerar dados fictícios antes de testar" |

> **Plano B (sem internet e sem instalação):** todos os exercícios do `python-do-zero` são
> `.txt` com "Resposta Esperada" — funcionam **offline**, com o aluno testando no
> [Google Colab](https://colab.research.google.com/) depois.

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Por que Python** | "É a língua que **fala com arquivo, planilha e API** sem pedir licença." |
| **Interpretador** | "`python` é o **programa** que lê o seu `.py`. Sem ele, o arquivo é só texto." |
| **`venv`** | "Uma caixinha isolada com as dependências **só daquele projeto**. Sem `venv`, você quebra o computador de outra pessoa." |
| **`requirements.txt`** | "A lista **versionada** do que o projeto precisa. É o que permite outra máquina rodar igual." |
| **Script confiável** | "1 tarefa · log · falha explícita · backup · dry-run." |
| **`pathlib`** | "Caminho é **objeto**, não texto. Você não concatena `/` na mão." |
| **`csv.DictReader`** | "Lê CSV linha a linha como **dicionário**: `linha['produto']`." |
| **`csv.writer`** | "Escreve CSV **com vírgula e aspas certas** — não é `print` com vírgula." |
| **`openpyxl`** | "Lê e escreve `.xlsx` de verdade: células, colunas, formatos." |
| **`json`** | "Texto que vira estrutura Python e volta. Formato padrão de API." |
| **`timeout`** | "Requisição HTTP **sem** timeout pode travar o script para sempre." |
| **`argparse`** | "O script que aceita opções é um **programa**. O que não aceita, é uma gambiarra." |
| **`unittest`** | "Teste automatizado = **código que verifica código**. Sai do da biblioteca padrão." |
| **`logging`** | "`print` é conversa; `logging` é **diário com nível, data e arquivo**." |
| **`--dry-run`** | "Mostra o que faria **sem fazer**. Salva a sua sexta-feira." |
| **Código de saída** | "`0` deu certo, `!= 0` deu errado. É assim que o agendador descobre." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (8 min)

**Gancho:** *"Quantas vezes por semana você repete a mesma tarefa manual —formatar
planilha, juntar arquivos, conferir se o relatório bate? Toda vez que alguém faz isso de
novo, a empresa paga de novo. Automatizar não é programar: é **devolver a sua hora**."*

**Demonstração ao vivo (5 min):** rode o script do módulo **antes** de explicá-lo:

```bash
# 1. Mostra o que existe
python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --dry-run

# 2. Executa de verdade
python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --formato todos

# 3. Mostra o log
cat logs/consolidar_vendas.log
```

Diga: *"Três comandos. O primeiro **não escreveu nada** — foi o ensaio. O terceiro deixou
um registro do que aconteceu. Já é mais confiável que 90% dos scripts que estão rodando
na sua empresa agora."*

### Fase 2 — Exploração (25 min)

**Parte 1 — Por que Python, e o ambiente (7 min).**

| Alternativa | Quando escolher | Custo de aprender |
|---|---|---|
| **Python** | dados, planilha, arquivo, API, automação, QA | baixo |
| Bash | uma linha de comando que vira script | médio (sintaxe estranha) |
| JavaScript | navegador, Node, front-end | médio |
| PowerShell | quem só tem Windows e nunca usou terminal | médio |

**O ambiente (o que o aluno precisa ter na máquina):**

```bash
# 1. Conferir a versão do interpretador
python --version          # Windows: python3 --version ou py --version
python3 --version

# 2. Criar o ambiente virtual (uma caixinha só do projeto)
python3 -m venv .venv

# 3. Ativar o ambiente virtual
source .venv/bin/activate          # Linux e macOS
# .venv\Scripts\activate           # Windows (PowerShell/CMD)

# 4. Instalar as dependências do projeto
pip install openpyxl requests

# 5. Gravar as dependências com versão (isso é que vai para o Git)
pip freeze > requirements.txt
```

> **Regra da sala:** o `.venv` **nunca** entra no Git. Ele está no `.gitignore`:
> ```gitignore
> .venv/
> __pycache__/
> *.pyc
> logs/
> .env
> ```

**Alternativa sem instalar nada — [Google Colab](https://colab.research.google.com/):**
o aluno abre, cola o script numa célula e roda. Serve para **aprender e testar**, mas
não serve para **agendar** — agendamento exige uma máquina rodando. Combine:
*Colab para aprender, sua máquina para produzir.*

**Parte 2 — As 5 regras do script confiável (6 min).**

| # | Regra | O que impede |
|---|---|---|
| 1 | **Uma tarefa por execução** | script que faz 7 coisas e quebra em 1 delas |
| 2 | **Log** (tela + arquivo) | "não sei o que aconteceu" às 3h da manhã |
| 3 | **Falha explícita** (mensagem clara + `exit 1`) | erro silencioso que continua e corrompe |
| 4 | **Backup antes de operação destrutiva** | sobrescrever o relatório bom sem cópia |
| 5 | **`--dry-run`** | rodar em produção para "ver como fica" |

> **A frase que fixa:** *"O `--dry-run` é o botão de **ensaio** do script. Ninguém ensaia
> uma apresentação no palco."*

**Parte 3 — Biblioteca padrão antes da biblioteca externa (4 min).**

O que o Python **já tem** (não precisa instalar nada):

| Precisa de | Use | Não instale |
|---|---|---|
| Ler/escrever arquivo | `pathlib`, `open()` | nada |
| CSV | `csv` | `pandas` (para o Módulo 04) |
| JSON | `json` | nada |
| Data e hora | `datetime` | nada |
| Log | `logging` | nada |
| Teste | `unittest` | `pytest` (opcional, depois) |
| Argumentos | `argparse` | nada |
| HTTP | `urllib` (sozinho) ou `requests` (melhor) | — |
| Excel | — | `openpyxl` (esse é externo mesmo) |

**Parte 4 — `pathlib`, `csv`, `json` na prática (8 min).**

```python
"""Exemplo: ler um CSV com pathlib + csv e gravar um JSON."""

import csv
import json
from pathlib import Path

# 1. pathlib: o caminho é um objeto, não texto
pasta = Path("dados")
pasta.mkdir(parents=True, exist_ok=True)      # cria sem falhar se já existir
arquivo = pasta / "vendas.csv"

# 2. Gravar um CSV de exemplo (o "dado fictício" entra por aqui)
with arquivo.open("w", encoding="utf-8", newline="") as saida:
    escritor = csv.writer(saida)
    escritor.writerow(["data", "produto", "quantidade", "valor_unitario"])
    escritor.writerow(["2026-03-01", "Caneta", "10", "1.50"])
    escritor.writerow(["2026-03-02", "Papel", "2", "25.00"])

# 3. Ler o CSV com DictReader: cada linha vira um dicionário
with arquivo.open("r", encoding="utf-8-sig", newline="") as entrada:
    for linha in csv.DictReader(entrada):
        print(linha["produto"], linha["quantidade"], linha["valor_unitario"])

# 4. Gravar um JSON com acentos preservados
relatorio = Path("relatorios")
relatorio.mkdir(parents=True, exist_ok=True)
dados = {"gerado_em": "2026-03-05", "vendas": [{"produto": "Caneta", "total": 15.0}]}
(relatorio / "vendas.json").write_text(
    json.dumps(dados, ensure_ascii=False, indent=2), encoding="utf-8"
)
```

> **Detalhe que separa profissional de amador:** `encoding="utf-8-sig"` ao **ler** CSV
> (remove o BOM que o Excel brasileiro deixa) e `ensure_ascii=False` ao gravar JSON (para
> "Operação" continuar sendo "Operação" e não "Opera\u00e7\u00e3o").

### Fase 3 — Mão na massa (30 min)

**Atividade A — Montar o script completo (20 min).**
Crie `consolidar_vendas.py` na raiz do projeto:

```python
#!/usr/bin/env python3
"""consolidar_vendas.py — consolida um CSV de vendas em um relatório por produto.

Ferramenta didática do Módulo 2 (Python para Automatizar a Rotina).

Uso:
    python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios
    python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --formato todos
    python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --dry-run

As 5 regras do script confiável, aplicadas aqui:
    1. UMA tarefa por execução: consolidar vendas.
    2. Log em tela e em arquivo.
    3. Falha explícita: mensagem clara e código de saída diferente de zero.
    4. Backup do relatório anterior antes de sobrescrever.
    5. --dry-run mostra o que faria sem escrever nada.
"""

from __future__ import annotations

import argparse
import csv
import json
import logging
import shutil
import sys
from collections import defaultdict
from collections.abc import Callable
from datetime import datetime
from pathlib import Path

import openpyxl  # biblioteca externa: pip install openpyxl

# --------------------------------------------------------------------- configuração
ARQUIVO_LOG = "logs/consolidar_vendas.log"
FORMATO_LOG = "%(asctime)s [%(levelname)s] %(message)s"
COLUNAS_OBRIGATORIAS = {"data", "produto", "quantidade", "valor_unitario"}

# Tipo de uma função que grava o relatório: recebe os totais e o caminho de destino
Gravador = Callable[[dict[str, float], Path], None]


def configurar_log(nivel: str = "INFO") -> logging.Logger:
    """Configura o log para aparecer na tela e ficar gravado em arquivo."""
    # Garante que a pasta de logs exista antes de criar o arquivo de log
    Path(ARQUIVO_LOG).parent.mkdir(parents=True, exist_ok=True)

    logger = logging.getLogger("consolidar_vendas")
    logger.setLevel(nivel)

    # Fecha e remove os handlers antigos (evita log duplicado e arquivo aberto)
    for handler in logger.handlers[:]:
        handler.close()
        logger.removeHandler(handler)

    formato = logging.Formatter(FORMATO_LOG, datefmt="%Y-%m-%d %H:%M:%S")

    # Saída 1: na tela (stdout)
    tela = logging.StreamHandler(sys.stdout)
    tela.setFormatter(formato)
    logger.addHandler(tela)

    # Saída 2: no arquivo (utf-8 para não quebrar acento)
    arquivo = logging.FileHandler(ARQUIVO_LOG, encoding="utf-8")
    arquivo.setFormatter(formato)
    logger.addHandler(arquivo)

    return logger


def ler_vendas(caminho: Path) -> list[dict[str, str]]:
    """Lê o CSV de vendas e devolve uma lista de dicionários (uma por linha).

    Lança FileNotFoundError se o arquivo não existir e ValueError se faltarem
    colunas obrigatórias ou se algum número for inválido.
    """
    if not caminho.exists():
        raise FileNotFoundError(f"Arquivo de entrada não encontrado: {caminho}")

    with caminho.open("r", encoding="utf-8-sig", newline="") as arquivo:
        leitor = csv.DictReader(arquivo)
        cabecalho = set(leitor.fieldnames or [])
        faltando = COLUNAS_OBRIGATORIAS - cabecalho
        if faltando:
            raise ValueError(
                "Colunas obrigatórias ausentes no CSV: " + ", ".join(sorted(faltando))
            )
        vendas = [
            {chave: (valor or "").strip() for chave, valor in linha.items() if chave}
            for linha in leitor
        ]

    return vendas


def total_por_produto(vendas: list[dict[str, str]]) -> dict[str, float]:
    """Soma (quantidade x valor unitário) de cada produto."""
    totais: dict[str, float] = defaultdict(float)

    for venda in vendas:
        try:
            quantidade = float(venda["quantidade"])
            valor_unitario = float(venda["valor_unitario"])
        except (KeyError, ValueError) as erro:
            raise ValueError(f"Valores inválidos na linha: {venda}") from erro
        if quantidade < 0 or valor_unitario < 0:
            raise ValueError(f"Quantidade ou valor negativo na linha: {venda}")
        totais[venda["produto"]] += quantidade * valor_unitario

    return dict(totais)


def fazer_backup(caminho: Path) -> Path | None:
    """Cria uma cópia '.bak' do arquivo antes de sobrescrevê-lo.

    Devolve o caminho da cópia ou None se o arquivo ainda não existia.
    """
    if not caminho.exists():
        return None

    backup = caminho.with_suffix(caminho.suffix + ".bak")
    shutil.copy2(caminho, backup)
    return backup


def gravar_csv(totais: dict[str, float], caminho: Path) -> None:
    """Grava o relatório por produto em CSV, do maior total para o menor."""
    caminho.parent.mkdir(parents=True, exist_ok=True)

    with caminho.open("w", encoding="utf-8", newline="") as arquivo:
        escritor = csv.writer(arquivo)
        escritor.writerow(["produto", "total"])
        for produto, total in sorted(totais.items(), key=lambda item: item[1], reverse=True):
            escritor.writerow([produto, f"{total:.2f}"])


def gravar_json(totais: dict[str, float], caminho: Path) -> None:
    """Grava o relatório por produto em JSON."""
    caminho.parent.mkdir(parents=True, exist_ok=True)

    dados = {
        "gerado_em": datetime.now().isoformat(timespec="seconds"),
        "total_geral": round(sum(totais.values()), 2),
        "por_produto": {
            produto: round(total, 2)
            for produto, total in sorted(totais.items())
        },
    }
    caminho.write_text(json.dumps(dados, ensure_ascii=False, indent=2), encoding="utf-8")


def gravar_xlsx(totais: dict[str, float], caminho: Path) -> None:
    """Grava o relatório por produto em uma planilha Excel (.xlsx)."""
    caminho.parent.mkdir(parents=True, exist_ok=True)

    livro = openpyxl.Workbook()
    folha = livro.active
    folha.title = "Por produto"
    folha.append(["Produto", "Total (R$)"])

    for produto, total in sorted(totais.items(), key=lambda item: item[1], reverse=True):
        folha.append([produto, round(total, 2)])

    # Formata a coluna de valores como moeda e ajusta a largura das colunas
    for celula in folha["B"][1:]:
        celula.number_format = 'R$ #,##0.00'
    folha.column_dimensions["A"].width = 32
    folha.column_dimensions["B"].width = 16

    livro.save(caminho)


def analisar_argumentos(argv: list[str] | None = None) -> argparse.Namespace:
    """Lê e valida os argumentos de linha de comando."""
    analisador = argparse.ArgumentParser(
        description="Consolida um CSV de vendas em um relatório por produto."
    )
    analisador.add_argument(
        "--entrada", type=Path, required=True,
        help="Caminho do CSV de vendas (obrigatório).",
    )
    analisador.add_argument(
        "--saida", type=Path, default=Path("relatorios"),
        help="Pasta onde o relatório será gravado. Padrão: relatorios",
    )
    analisador.add_argument(
        "--formato", choices=["csv", "json", "xlsx", "todos"], default="csv",
        help="Formato do relatório. Padrão: csv",
    )
    analisador.add_argument(
        "--dry-run", action="store_true",
        help="Mostra o que faria sem gravar nada.",
    )
    analisador.add_argument(
        "--nivel-log", choices=["DEBUG", "INFO", "WARNING", "ERROR"], default="INFO",
        help="Nível de detalhe do log. Padrão: INFO",
    )
    return analisador.parse_args(argv)


def main(argv: list[str] | None = None) -> int:
    """Ponto de entrada. Devolve o código de saída: 0 = sucesso, 1 = falha."""
    argumentos = analisar_argumentos(argv)
    logger = configurar_log(argumentos.nivel_log)
    logger.info("Iniciando consolidação (dry-run=%s).", argumentos.dry_run)

    # ---- Leitura e consolidação (tudo dentro do try: falha explícita)
    try:
        vendas = ler_vendas(argumentos.entrada)
        logger.info("%d venda(s) lida(s) de %s.", len(vendas), argumentos.entrada)

        totais = total_por_produto(vendas)
        logger.info(
            "%d produto(s) consolidado(s). Total geral: R$ %.2f",
            len(totais), sum(totais.values()),
        )
    except (FileNotFoundError, ValueError) as erro:
        logger.error("Falha: %s", erro)
        return 1

    # ---- Lista de arquivos de saída (o dry-run só mostra, não grava)
    alvos: list[tuple[Path, Gravador]] = []
    if argumentos.formato in ("csv", "todos"):
        alvos.append((argumentos.saida / "vendas_por_produto.csv", gravar_csv))
    if argumentos.formato in ("json", "todos"):
        alvos.append((argumentos.saida / "vendas_por_produto.json", gravar_json))
    if argumentos.formato in ("xlsx", "todos"):
        alvos.append((argumentos.saida / "vendas_por_produto.xlsx", gravar_xlsx))

    for caminho, gravador in alvos:
        if argumentos.dry_run:
            logger.info("[dry-run] Gravaria %s (nada foi gravado).", caminho)
            continue

        # Regra 4: backup antes de sobrescrever
        backup = fazer_backup(caminho)
        if backup is not None:
            logger.warning("Backup do relatório anterior em %s", backup)

        gravador(totais, caminho)
        logger.info("Relatório gravado em %s", caminho)

    logger.info("Concluído com sucesso.")
    return 0


if __name__ == "__main__":
    sys.exit(main())
```

**Crie o dado de entrada `dados/vendas.csv`:**

```csv
data,produto,quantidade,valor_unitario
2026-03-01,Caneta azul,10,1.50
2026-03-01,Papel A4,4,22.90
2026-03-02,Caneta azul,5,1.50
2026-03-02,Caderno,3,18.00
2026-03-03,Estojo,2,45.00
```

**Rode nesta ordem (é a ordem didática):**

```bash
# 1. Ensaio: mostra o que faria e NÃO grava nada
python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --formato todos --dry-run

# 2. Real
python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --formato todos

# 3. Erro proposital: apague o CSV e rode de novo
python consolidar_vendas.py --entrada dados/nao_existe.csv --saida relatorios
echo "código de saída: $?"     # deve ser 1 (e o log registra o motivo)
```

**Entregável da Atividade A:** `consolidar_vendas.py` rodando, com as 5 regras aplicadas,
log em `logs/consolidar_vendas.log` e **código de saída** correto nos dois cenários.

**Atividade B — Requisição HTTP com timeout (10 min).**
Crie `consultar_github.py`:

```python
#!/usr/bin/env python3
"""consultar_github.py — consulta a API pública do GitHub com timeout e tratamento de erro."""

import logging
import sys

import requests

LOG = logging.getLogger("consultar_github")


def buscar_repositorio(usuario: str, repositorio: str) -> dict:
    """Busca os metadados de um repositório público do GitHub.

    Levanta RuntimeError com mensagem clara em qualquer falha.
    """
    url = f"https://api.github.com/repos/{usuario}/{repositorio}"
    LOG.info("Consultando %s", url)

    try:
        # timeout = (tempo de conexão, tempo de leitura da resposta)
        resposta = requests.get(url, timeout=(3, 10))
    except requests.exceptions.Timeout:
        raise RuntimeError("Tempo esgotado ao falar com a API do GitHub.") from None
    except requests.exceptions.ConnectionError:
        raise RuntimeError("Sem conexão com a API do GitHub.") from None

    if resposta.status_code == 404:
        raise RuntimeError(f"Repositório não encontrado: {usuario}/{repositorio}")
    if resposta.status_code >= 500:
        raise RuntimeError(f"Erro do servidor do GitHub: HTTP {resposta.status_code}")

    resposta.raise_for_status()
    return resposta.json()


def main() -> int:
    logging.basicConfig(level=logging.INFO, format="%(asctime)s [%(levelname)s] %(message)s")

    try:
        dados = buscar_repositorio("Marquezbertin", "manual-qa-completo")
    except RuntimeError as erro:
        LOG.error("Falha: %s", erro)
        return 1

    LOG.info("Repositório: %s", dados.get("full_name"))
    LOG.info("Descrição: %s", dados.get("description"))
    LOG.info("Estrelas: %s | Linguagem: %s", dados.get("stargazers_count"), dados.get("language"))
    return 0


if __name__ == "__main__":
    sys.exit(main())
```

**Regras para toda chamada HTTP, sempre:**
- `timeout` **sempre** (sem ele, o script trava esperando).
- `raise_for_status()` ou verificação manual de `status_code`.
- `except` específico (`Timeout`, `ConnectionError`), nunca `except:` genérico.
- Chave de API em **variável de ambiente**, nunca no código.

**Entregável da Atividade B:** `consultar_github.py` rodando e **falhando de forma
clara** quando o repositório não existe (`python consultar_github.py` com um nome
inexistente → mensagem clara e código de saída 1).

### Fase 4 — Projeto (22 min)

**Desafio: "Seu script, testado e agendado"**

**Parte 1 — Teste automatizado (12 min).**
Crie `test_consolidar_vendas.py`:

```python
#!/usr/bin/env python3
"""test_consolidar_vendas.py — testes automatizados do script de consolidação.

Executar:  python -m unittest -v test_consolidar_vendas.py
"""

import csv
import json
import tempfile
import unittest
from pathlib import Path

import consolidar_vendas as cv


class TestConsolidarVendas(unittest.TestCase):
    """Cada método test_* é um caso de teste independente."""

    def setUp(self) -> None:
        """Roda antes de cada teste: cria uma pasta temporária e um CSV de exemplo."""
        self.pasta = tempfile.TemporaryDirectory()
        self.raiz = Path(self.pasta.name)
        self.csv = self.raiz / "vendas.csv"
        self.csv.write_text(
            "data,produto,quantidade,valor_unitario\n"
            "2026-03-01,Caneta,10,1.50\n"
            "2026-03-02,Caneta,5,1.50\n"
            "2026-03-02,Papel,2,25.00\n",
            encoding="utf-8",
        )

    def tearDown(self) -> None:
        """Roda depois de cada teste: apaga a pasta temporária."""
        self.pasta.cleanup()

    def test_le_todas_as_vendas(self) -> None:
        """O CSV de exemplo tem 3 linhas de venda."""
        vendas = cv.ler_vendas(self.csv)
        self.assertEqual(len(vendas), 3)

    def test_soma_por_produto(self) -> None:
        """Caneta: 10x1.50 + 5x1.50 = 22.50 | Papel: 2x25.00 = 50.00."""
        totais = cv.total_por_produto(cv.ler_vendas(self.csv))
        self.assertAlmostEqual(totais["Caneta"], 22.50)
        self.assertAlmostEqual(totais["Papel"], 50.00)

    def test_arquivo_inexistente_falha(self) -> None:
        """Arquivo ausente precisa levantar FileNotFoundError."""
        with self.assertRaises(FileNotFoundError):
            cv.ler_vendas(self.raiz / "nao_existe.csv")

    def test_coluna_ausente_falha(self) -> None:
        """CSV sem a coluna 'valor_unitario' precisa levantar ValueError."""
        ruim = self.raiz / "sem_coluna.csv"
        ruim.write_text("data,produto\n2026-03-01,Caneta\n", encoding="utf-8")
        with self.assertRaises(ValueError):
            cv.ler_vendas(ruim)

    def test_valor_invalido_falha(self) -> None:
        """Quantidade não numérica precisa levantar ValueError."""
        ruim = self.raiz / "valor_invalido.csv"
        ruim.write_text(
            "data,produto,quantidade,valor_unitario\n2026-03-01,Caneta,abc,1.50\n",
            encoding="utf-8",
        )
        with self.assertRaises(ValueError):
            cv.total_por_produto(cv.ler_vendas(ruim))

    def test_grava_csv_com_cabecalho(self) -> None:
        """O CSV gerado tem o cabeçalho e uma linha por produto."""
        saida = self.raiz / "relatorios" / "vendas.csv"
        cv.gravar_csv(cv.total_por_produto(cv.ler_vendas(self.csv)), saida)
        with saida.open(encoding="utf-8", newline="") as arquivo:
            linhas = list(csv.reader(arquivo))
        self.assertEqual(linhas[0], ["produto", "total"])
        self.assertEqual(len(linhas), 3)

    def test_grava_json_com_total_geral(self) -> None:
        """O JSON gerado tem 'gerado_em' e o total geral correto (22.50 + 50.00)."""
        saida = self.raiz / "relatorios" / "vendas.json"
        cv.gravar_json(cv.total_por_produto(cv.ler_vendas(self.csv)), saida)
        dados = json.loads(saida.read_text(encoding="utf-8"))
        self.assertIn("gerado_em", dados)
        self.assertAlmostEqual(dados["total_geral"], 72.50)

    def test_backup_copia_o_arquivo(self) -> None:
        """O backup guarda o conteúdo anterior do relatório."""
        alvo = self.raiz / "relatorio.csv"
        alvo.write_text("conteudo antigo", encoding="utf-8")
        backup = cv.fazer_backup(alvo)
        self.assertIsNotNone(backup)
        self.assertEqual(backup.read_text(encoding="utf-8"), "conteudo antigo")

    def test_dry_run_nao_grava_arquivo(self) -> None:
        """Com --dry-run nada é gravado, mas o código de saída é 0."""
        saida = self.raiz / "relatorios"
        codigo = cv.main([
            "--entrada", str(self.csv),
            "--saida", str(saida),
            "--formato", "todos",
            "--dry-run",
        ])
        self.assertEqual(codigo, 0)
        self.assertFalse((saida / "vendas_por_produto.csv").exists())

    def test_main_devolve_1_quando_falta_arquivo(self) -> None:
        """Entrada inexistente: o script falha com código de saída 1."""
        codigo = cv.main([
            "--entrada", str(self.raiz / "nao_existe.csv"),
            "--saida", str(self.raiz / "relatorios"),
        ])
        self.assertEqual(codigo, 1)


if __name__ == "__main__":
    unittest.main()
```

Rode:

```bash
python -m unittest -v test_consolidar_vendas.py
```

> ⚠️ O `main()` em modo teste **cria a pasta `logs/`** no diretório atual (por causa do
> `logging.FileHandler`). Isso é esperado — e é exatamente o tipo de detalhe que um
> profissional percebe e documenta.

**Parte 2 — Agendar (10 min).**

```bash
# Linux e macOS: cron
crontab -e
```

```cron
# Consolida as vendas todo dia às 7h (o log vai para arquivo, o erro também)
0 7 * * * cd ~/meu-projeto && /home/USUARIO/meu-projeto/.venv/bin/python consolidar_vendas.py --entrada dados/vendas.csv --saida relatorios --formato todos >> logs/cron.log 2>&1
```

> **Use o caminho absoluto do Python do `.venv`.** É o erro número 1 de cron: o `python`
> do sistema não é o seu.

```powershell
# Windows: schtasks (PowerShell)
schtasks /Create /TN "ConsolidarVendas" /TR "C:\Users\USUARIO\meu-projeto\.venv\Scripts\python.exe C:\Users\USUARIO\meu-projeto\consolidar_vendas.py --entrada C:\Users\USUARIO\meu-projeto\dados\vendas.csv --saida C:\Users\USUARIO\meu-projeto\relatorios --formato todos" /SC DAILY /ST 07:00

# Testar sem esperar o relógio
schtasks /Run /TN "ConsolidarVendas"

# Remover a tarefa
schtasks /Delete /TN "ConsolidarVendas" /F
```

**Critério de pronto:**
- [ ] `consolidar_vendas.py` roda e gera **os 3 formatos** (CSV, JSON, XLSX)
- [ ] O script tem **log** em arquivo e em tela
- [ ] O script **falha de forma explícita** (mensagem clara + código de saída 1)
- [ ] O script faz **backup** (`.bak`) antes de sobrescrever um relatório existente
- [ ] O script tem `--dry-run` e **não grava** nada com ele
- [ ] `consultar_github.py` usa `requests` com `timeout` e trata erro
- [ ] `test_consolidar_vendas.py` tem **pelo menos 8 testes** e todos passam
- [ ] `requirements.txt` existe com as dependências versionadas
- [ ] `.gitignore` cobre `.venv/`, `__pycache__/`, `logs/` e `.env`
- [ ] O script está **agendado** (cron ou `schtasks`) e você **testou** a execução
- [ ] `README.md` explica: o que o script faz, como instalar, como rodar, como agendar e onde fica o log

### Fase 5 — Mostra (5 min)

Cada aluno roda o script **ao vivo** na frente da turma (30 s) e mostra **1 teste** rodando
(`python -m unittest -v ...` filtrado por um caso). A turma pergunta:

1. "O que acontece se eu rodar com `--dry-run`?"
2. "Onde eu descubro que o script falhou às 3h da manhã?"

> **Pergunta de saída:** "Qual a diferença entre `print("erro")` e `logger.error("erro")`?
> E por que um script agendado precisa de código de saída?"

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Script principal | Roda sem erro; gera os 3 formatos; CLI com `argparse` e `--help` funcionando |
| Regras de script confiável | 1 tarefa · log · falha explícita · backup · dry-run — as 5 presentes |
| Log | Arquivo `logs/*.log` criado, com data/hora e nível |
| Código de saída | `0` no sucesso, `1` na falha (verificado) |
| HTTP | `requests` com `timeout`, `except` específico e mensagem clara |
| Testes | 8 ou mais casos em `unittest`, todos verdes, nomes descritivos em português |
| Agendamento | Tarefa criada **e testada** (cron ou `schtasks`) |
| Ambiente | `requirements.txt` versionado + `.gitignore` com `.venv/` e `__pycache__/` |
| README | Requer instalado, comando de uso, agendamento e caminho do log |

**Pergunta de escrita:**
> "Você agendou o script para rodar todo dia às 7h. Segunda-feira ele rodou bem.
> Terça-feira o relatório saiu **vazio**, sem erro no terminal e sem mensagem no log.
> Quarta-feira, o mesmo. Onde você olha primeiro, e o que isso revela sobre o seu script?"
> **Resposta:** O sintoma "saída vazia, sem erro, sem log" aponta para **uma das três**:
> 1. **O arquivo de entrada mudou de lugar ou foi renomeado.** O script lê
>    `dados/vendas.csv` com caminho **relativo**. Se o `cron` roda em outro diretório de
>    trabalho, o caminho relativo aponta para outro lugar — ou para nada. *Correção:* use
>    caminho absoluto e, no código, valide `caminho.exists()` antes de ler (o script do
>    módulo já faz isso e **registra o erro no log** — se o log está vazio, o script nem
>    chegou a ler o arquivo, e isso muda o diagnóstico).
> 2. **O código trata "arquivo vazio" como sucesso.** Se o CSV tiver só o cabeçalho, o
>    `DictReader` devolve **zero linhas** — e `total_por_produto({})` devolve `{}`, sem
>    exceção. O script "tem sucesso" e grava um relatório vazio. *Correção:* valide o
>    resultado antes de gravar e **falhe explicitamente** ("a entrada tem 0 linhas").
> 3. **O `logging` está configurado para um caminho que não existe** (ou o usuário do
>    agendamento não tem permissão), então o log vai para outro lugar — ou para lugar
>    nenhum. *Correção:* `logging.FileHandler` com pasta criada antes
>    (`Path(...).parent.mkdir(...)`), **caminho absoluto** do arquivo de log e um `echo`
>    do caminho no início da execução.
> **Lição de fundo:** um script que falha em silêncio é pior que um script que não
> existe, porque ele produz **resultado errado** com aparência de resultado certo.
> É por isso que a regra 3 (falha explícita) e a regra 5 (`--dry-run`) existem.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `python-do-zero/10_arquivos/exercicio_01_escrever.txt` | Escrever arquivo de texto |
| `python-do-zero/10_arquivos/exercicio_02_ler.txt` | Ler arquivo linha a linha |
| `python-do-zero/10_arquivos/exercicio_03_append.txt` | Acrescentar ao final (`append`) |
| `python-do-zero/10_arquivos/exercicio_04_with.txt` | Bloco `with` (fecha o arquivo sozinho) |
| `python-do-zero/10_arquivos/exercicio_05_csv.txt` | Ler e escrever CSV |
| `python-do-zero/15_api_e_json/exercicio_01_json_dump.txt` | `json.dump` |
| `python-do-zero/15_api_e_json/exercicio_02_json_arquivo.txt` | JSON em arquivo |
| `python-do-zero/15_api_e_json/exercicio_03_requests_basico.txt` | `requests` básico |
| `python-do-zero/15_api_e_json/exercicio_04_api_consumo.txt` | Consumir uma API |
| `python-do-zero/11_tratamento_erros/` | `try`, `except`, `finally` — base da "falha explícita" |
| `python-do-zero/12_modulos/` | Separar o script em módulos e `import` |
| `manual-qa-completo/docs/03/scripts/estimate.py` | Script real com `docstring`, tipagem e `if __name__ == "__main__"` |
| `manual-qa-completo/run_all.py` | Padrão de código de saída e execução por subprocess |
| `qa-automation-framework/utils/data_generator.py` | Gerar dados falsos com `Faker` (nunca use dado real de cliente) |
| `qa-automation-framework/requirements.txt` | Exemplo de `requirements.txt` **versionado** |
| `Analise-de-Dados/datasets/Gapminder.csv` | CSV real para treinar (mais de mil linhas) |
| `Analise-de-Dados/datasets/AdventureWorks.xlsx` | Planilha real para treinar `openpyxl` |
| `agente_qaIA/scripts/create_sample_db.py` | Gerar banco de demonstração antes de testar |
| `lista-de-exercicios-python-brasil/` | 112 exercícios em texto puro, com gabarito (funciona **offline**) |

---

## 🏠 Para casa

1. **Troque o problema do script pelo seu.** Pegue uma tarefa real do seu trabalho (juntar
   planilhas, conferir um arquivo, extrair um número) e reescreva o script para ela,
   mantendo as **5 regras**.
2. Escreva **pelo menos 3 testes novos** para o seu caso — e inclua **um teste de
   falha** (entrada inválida).
3. Agende o script e **teste** a execução real (no `cron`, use `* * * * *` por 1 minuto;
   no Windows, use `schtasks /Run`).
4. Versione tudo no Git com **3 commits**: `chore: estrutura e requirements`,
   `feat: script de <sua tarefa>` e `test: casos de teste`.
5. Escreva no `README.md` uma seção **"Decisões e limitações"**: 2 itens que o script
   **não** resolve.
6. (Opcional) Refaça o mesmo script com a **biblioteca padrão** (`csv` + `json` + `logging`),
   sem `openpyxl` e sem `requests`, e compare o tamanho do código.

---

## 🔗 Próximo módulo

**03 — Git e GitHub profissional** (aula 05 e 06 desta trilha). Ainda **não publicado**
nesta versão do material — o mapa completo da trilha, com o repositório-base e o
entregável de cada módulo, está em:

[Trilha JOVENS E ADULTOS (18+) — Profissionais](00-plano-da-trilha.md)

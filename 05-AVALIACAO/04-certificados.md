# Modelo de Certificado e Critérios de Emissão (8–12 · 13–17 · 18+)

**Pasta:** `05-AVALIACAO/` · **Público:** coordenação e professor · **Entrega:** no fim da trilha

> Este modelo é **inspirado em boas práticas de avaliação e registro de conclusão**:
> linguagem simples, código verificável e dados mínimos. Ele **não** segue uma norma
> técnica específica — adapte os campos ao que a sua instituição exige.

---

## 🎯 Objetivo

Ao final deste material, o professor ou o coordenador será capaz de:

1. **Emitir o certificado** de conclusão com os campos completos: nome do aluno, trilha,
   carga horária, data, professor e código de verificação.
2. Aplicar os **critérios de emissão** (frequência, entregáveis e projeto final
   apresentado) de forma igual para as três faixas.
3. Escolher **uma das três formas de emissão on-line** — modelo editável, GitHub
   Pages ou certificado digital assinado.
4. Converter **carga horária, minutos e frequência** sem erro aritmético.

**Objetivo secundário:** fazer do certificado uma **prova verificável** — quem
recebe consegue conferir o código em 30 segundos, sem ligar para ninguém.

---

## 📚 Onde cada coisa está

| Documento | O que resolve |
|---|---|
| `05-AVALIACAO/04-certificados.md` (este) | Modelo, critérios de emissão, emissão on-line e conversão de horas |
| `05-AVALIACAO/01-rubrica-avaliacao.md` | A rubrica que define o **conceito** do aluno antes da emissão |
| `05-AVALIACAO/02-rubricas-por-trilha.md` | Os **componentes e pesos** que sustentam os critérios de emissão |
| `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §8 e §9 | Inclusão, material obrigatório e **segurança de crianças** |
| `01-CRIANCAS-8-12/07-projeto-final.md` | A entrega do certificado na **Mostra de resultados** da trilha 8–12 |

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Certificado** | "Prova de que a pessoa **terminou** — não de que foi aprovada em prova." |
| **Frequência mínima** | "75% é o piso. O que falta, compensa com entrega." |
| **Entregável** | "O que existe no repositório do aluno, com link." |
| **Código de verificação** | "Um código curto que qualquer pessoa confere sozinha." |
| **Carga horária** | "Sempre em **horas**, com o número de aulas ao lado." |
| **Nome social / apelido** | "Para menor de idade, o nome publicado é o que ele escolheu." |
| **Mínimo de dado** | "No certificado público entra só o necessário." |

---

## Critérios de emissão

Os critérios são os **mesmos três** para as três faixas; o que muda é **quanto** de
cada um e **qual entregável** conta.

| Critério | 8–12 (Exploradores) | 13–17 (Makers/Devs) | 18+ (Profissionais) |
|---|---|---|---|
| **Frequência mínima** | 75% — 9 das 12 aulas | 75% — 12 das 16 aulas | 75% — 12 das 16 aulas |
| **Participação** | Nível **Adequado** (3) em pelo menos 3 dos 4 critérios da rubrica da trilha | Conceito **Adequado** ou **Excelente** no componente "Participação e exercícios" (20%) | Conceito **Adequado** ou **Excelente** no componente "Entregáveis e scripts rodando" (20%) |
| **Entregáveis mínimos** | Mapa do Projeto preenchido + projeto funcional + apresentação oral de 4 min | Repositório com `README`, `LICENSE`, testes e histórico de commits + site publicado | Script de automação rodando + testes automatizados + documentação + pipeline executando |
| **Projeto final apresentado** | Sim — 4 min na Mostra de resultados, para a turma e a família | Sim — 4 min no Showcase, com demonstração ao vivo | Sim — 5 min, com métrica e análise de risco |
| **Segurança e dados** | Nenhuma ocorrência grave de exposição de dado pessoal ou senha compartilhada | Repositório sem dado real de aluno e sem segredo no histórico | Repositório sem dado real de cliente e sem segredo versionado |
| **Autorização** | Do responsável e da escola; usar **nome social ou apelido**; sem foto, e-mail ou matrícula no documento público | Termo de uso de **imagem e voz** assinado quando houver publicação de foto ou vídeo | Consentimento expresso do titular para uso do nome no certificado |

### Regras de aplicação dos critérios

1. **Frequência abaixo de 75%** não impede a emissão: desde que os entregáveis
   estejam completos, o certificado é emitido com a carga horária **correspondente
   às aulas frequentadas** (veja a conversão de horas).
2. **Falta não justificada** conta como não entregue no componente do dia, e a
   entrega é recuperável até a data do projeto final.
3. **Aluno com plano de apoio** é avaliado pelo mesmo critério, com o apoio
   concedido: o plano muda a condição de prova, não a régua (ver
   `01-rubrica-avaliacao.md`).
4. **O certificado não é recompensa por perfeição.** É registro de conclusão. O
   conceito da trilha vai em **observação** ("conceito: Adequado"), nunca como
   nota reprovável.
5. **Trilha 8–12:** a emissão depende de autorização da escola — o item do
   checklist final do projeto final já traz "Certificado (se a escola autorizar)".

---

## Modelo de certificado (texto pronto para editar)

Copie o bloco abaixo para um documento editável (Word, Google Docs, LibreOffice) e
substitua os campos entre `{ }`.

```text
════════════════════════════════════════════════════════════════════════════
                     CERTIFICADO DE CONCLUSÃO
            Material Didático de Tecnologia — Trilha {TRILHA}
════════════════════════════════════════════════════════════════════════════

Certificamos que {NOME_DO_ALUNO} concluiu o curso "{NOME_DO_CURSO}", promovido
por {NOME_DA_INSTITUICAO}, com carga horária total de {CARGA_HORARIA},
realizado no período de {DATA_INICIO} a {DATA_CONCLUSAO}.

PROGRAMA REALIZADO
{RELACAO_DOS_MODULOS}

O programa compreendeu {NUMERO_AULAS} aulas de {DURACAO_AULA} minutos e
culminou com {NOME_DO_PROJETO_FINAL}, apresentado em {DATA_DA_MOSTRA}.

{CIDADE}, {DATA_CONCLUSAO}.

_______________________________        _______________________________
{PROFESSOR_RESPONSAVEL}                {COORDENACAO_PEDAGOGICA}
Professor(a) responsável pela trilha    Coordenação pedagógica
{NOME_DA_INSTITUICAO}                  {NOME_DA_INSTITUICAO}

Código de verificação: {CODIGO_VERIFICACAO}
Conferir em {URL_VERIFICACAO}
════════════════════════════════════════════════════════════════════════════
```

### Campos a preencher

| Campo | Exemplo | Obrigatório |
|---|---|---|
| `{NOME_DO_ALUNO}` | Ana Souza (ou o **apelido**, na faixa 8–12) | Sim |
| `{NOME_DO_CURSO}` | Material Didático de Tecnologia — Trilha Makers/Devs | Sim |
| `{TRILHA}` | Exploradores 8–12 · Makers/Devs 13–17 · Profissionais 18+ | Sim |
| `{NOME_DA_INSTITUICAO}` | Escola Municipal / Empresa / Grupo comunitário | Sim |
| `{CARGA_HORARIA}` | 24 horas (16 aulas de 90 minutos) | Sim |
| `{NUMERO_AULAS}` | 16 | Sim |
| `{DURACAO_AULA}` | 90 minutos | Sim |
| `{DATA_INICIO}` / `{DATA_CONCLUSAO}` | 05/02/2026 e 18/12/2026 | Sim |
| `{NOME_DO_PROJETO_FINAL}` | Site de avisos da escola | Sim |
| `{DATA_DA_MOSTRA}` | 18/12/2026 | Sim |
| `{PROFESSOR_RESPONSAVEL}` | Nome do professor(a) | Sim |
| `{COORDENACAO_PEDAGOGICA}` | Nome do(a) coordenador(a) | Recomendado |
| `{CODIGO_VERIFICACAO}` | `MTD-B13-2026-001` | Sim |
| `{URL_VERIFICACAO}` | `https://sua-escola.github.io/certificados/verificar.html` | Sim |
| `{CIDADE}` | Cidade do curso | Recomendado |

### Regras de diagramação do documento

| Item | Orientação |
|---|---|
| Papel | A4 **horizontal** ou retrato, com margem de 2 cm |
| Assinaturas | Duas: professor e coordenação. Se for digital, use assinatura eletrônica (ver opções abaixo) |
| QR Code | Opcional, mas recomendado: aponta para `{URL_VERIFICACAO}` já com o código preenchido |
| Nome do aluno | Em **destaque**, tamanho maior que o texto |
| Carga horária | Sempre com o número de aulas ao lado: `24 horas (16 aulas de 90 minutos)` |
| Observação do conceito | Opcional, no rodapé: `Conceito da trilha: Adequado` — **sem nota numérica** |
| Imagem de aluno | **Não** incluir na faixa 8–12 (ver a seção de privacidade) |

---

## Código de verificação

### Formato

```
MTD-{FAIXA}-{ANO}-{SEQUENCIAL}

MTD-A8-2026-001     → 8–12   (Exploradores)
MTD-B13-2026-001    → 13–17  (Makers/Devs)
MTD-C18-2026-001    → 18+    (Profissionais)
```

| Regra | Detalhe |
|---|---|
| Sequencial | 3 dígitos, por trilha e por ano, sem reutilizar número |
| Onde guardar | Uma planilha/arquivo único, **restrito**: `codigo`, `nome`, `trilha`, `data`, `situação` |
| Onde publicar | Somente a **lista pública** com nome (se autorizado) e os campos do certificado |
| O que **não** publicar | CPF, e-mail, telefone, matrícula, data de nascimento, endereço, nota |

---

## Emissão on-line — 3 opções

### Opção 1 — Modelo editável (a mais simples, custo zero)

| Item | Detalhe |
|---|---|
| Ferramentas | Word, Google Docs, LibreOffice Writer ou Google Slides |
| Passo a passo | (1) copie o texto do modelo para um documento; (2) preencha os campos; (3) exporte em **PDF**; (4) assine no documento ou no PDF; (5) guarde o PDF com o nome `{CODIGO_VERIFICACAO}.pdf` |
| Vantagem | Funciona em qualquer computador, sem servidor, sem internet na hora da emissão |
| Onde guardar | Pasta protegida por acesso, com backup em 2 lugares |
| Quando usar | Turmas pequenas, escola sem site, emissão pontual |

> Dica: crie **um** documento-mestre com os campos e use-o para todos — assim a
> diagramação fica igual e só muda o conteúdo.

### Opção 2 — GitHub Pages (site público com página de verificação)

| Item | Detalhe |
|---|---|
| Onde | Um repositório da escola (nunca a conta pessoal do aluno) com a pasta `certificados/` |
| Publicação | Settings → Pages → branch `main`, pasta `/ (root)` → URL pública |
| Estrutura sugerida | `certificados/indice.html` (lista) · `certificados/verificar.html` (busca pelo código) · `certificados/certificados.js` (dados) |
| Custo | R$ 0 |
| Quando usar | Turma grande, emissão contínua, material aberto |

**Página de verificação — dados em um arquivo só:**

```javascript
// certificados/certificados.js
const CERTIFICADOS = {
  "MTD-B13-2026-001": {
    nome: "Nome do Aluno",
    trilha: "Adolescentes 13–17 — Makers/Devs",
    carga: "24 horas (16 aulas de 90 minutos)",
    data: "18/12/2026",
    professor: "Nome do Professor",
    instituicao: "Nome da Escola"
  }
};

function buscar(codigo) {
  const chave = (codigo || "").trim().toUpperCase();
  const achado = CERTIFICADOS[chave];
  const saida = document.getElementById("resultado");

  if (!achado) {
    saida.textContent = "Código não encontrado. Confira os caracteres.";
    return;
  }

  saida.innerHTML =
    "<h2>Certificado válido</h2>" +
    "<p><strong>" + achado.nome + "</strong></p>" +
    "<p>Trilha: " + achado.trilha + "</p>" +
    "<p>Carga horária: " + achado.carga + "</p>" +
    "<p>Conclusão: " + achado.data + "</p>" +
    "<p>Professor: " + achado.professor + "</p>" +
    "<p>Instituição: " + achado.instituicao + "</p>";
}
```

```html
<!-- certificados/verificar.html -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Verificar certificado</title>
</head>
<body>
  <h1>Verificar certificado</h1>
  <label for="codigo">Código de verificação</label>
  <input id="codigo" type="text" placeholder="MTD-B13-2026-001">
  <button onclick="buscar(document.getElementById('codigo').value)">Verificar</button>
  <div id="resultado"></div>
  <script src="certificados.js"></script>
</body>
</html>
```

> O repositório `laboratorio-tech-social` já traz um modelo nessa linha — a pasta
> `site/certificado/` com `index.html` e `verificar.html` — citado no plano da
> trilha 8–12, no plano da trilha 18+ e no guia do professor §9. Copie o padrão e
> adapte para a sua instituição.

### Opção 3 — Certificado digital com assinatura (validade formal)

| Item | Detalhe |
|---|---|
| O que é | Um arquivo (PDF) **assinado digitalmente**, que prova quem emitiu e que o conteúdo **não mudou** depois |
| Assinatura com pessoa jurídica | Certificado digital no padrão **ICP-Brasil** (e-CPF ou e-CNPJ) — a assinatura tem validade jurídica no Brasil |
| Assinatura simples | Plataformas de assinatura eletrônica ou a própria assinatura do GitHub: valida **autoria**, com valor probatório menor |
| Carimbo do tempo | Selo que registra **quando** o arquivo foi assinado; um arquivo carimbado não muda depois |
| Alternativa sem custo | Assinatura autoassinada gerada com `openssl` + chave privada do professor, útil para registro **interno** da instituição |
| Quando usar | Instituição que precisa de registro formal, reconhecimento externo ou comprovação legal |

### Comparativo

| Opção | Custo | Precisa de internet | Confere em | Serve para |
|---|---|---|---|---|
| **1. Modelo editável** | R$ 0 | Não | O professor, pelo PDF | Registro interno simples |
| **2. GitHub Pages** | R$ 0 | Sim, para publicar | Qualquer pessoa, pelo código | Turmas grandes e material aberto |
| **3. Certificado digital** | Variável | Sim | Qualquer pessoa, pelo arquivo PDF assinado | Validade formal e reconhecimento externo |

> **Recomendação:** comece pela **Opção 1** e evolua para a **Opção 2** quando a
> escola tiver um repositório próprio. A **Opção 3** só faz sentido se houver
> exigência formal da instituição — e, nesse caso, o modelo de texto continua o
> mesmo; muda apenas a assinatura.

---

## Tabela de conversão de horas

### Carga horária de cada trilha

| Trilha | Aulas | Duração por aula | Carga horária total | Total em minutos | 75% de frequência (horas) | 75% de frequência (aulas) |
|---|---|---|---|---|---|---|
| **8–12 — Exploradores** | 12 | 60 min | **12 h** | 720 min | 9 h | 9 aulas |
| **13–17 — Makers/Devs** | 16 | 90 min | **24 h** | 1.440 min | 18 h | 12 aulas |
| **18+ — Profissionais** | 16 | 90 min | **24 h** | 1.440 min | 18 h | 12 aulas |

> ⚠️ O plano da trilha 8–12 declara **12 aulas × 60 min = 12 horas** e nomeia 10
> módulos com carga. **Confirme o número real de aulas com a coordenação** antes de
> emitir e ajuste esta linha — a carga horária do certificado não pode divergir do
> que consta no plano.

### Minutos → horas (referência rápida)

| Minutos | Horas | Minutos | Horas |
|---|---|---|---|
| 30 | 0,5 | 150 | 2,5 |
| 45 | 0,75 | 180 | 3 |
| 60 | 1 | 240 | 4 |
| 90 | 1,5 | 360 | 6 |
| 120 | 2 | 1.440 | 24 |

**Definição:** 1 **hora-aula** = 60 minutos. Uma aula de 90 minutos vale
**1,5 hora-aula**. A carga horária se declara em **horas-cronômetro**: 16 aulas de
90 minutos = 24 horas.

### Frequência → carga horária frequentada

**Aula de 90 min (trilhas 13–17 e 18+):**

| Presenças | Horas frequentadas | % da carga |
|---|---|---|
| 16 | 24,0 h | 100% |
| 15 | 22,5 h | 93,8% |
| 14 | 21,0 h | 87,5% |
| 13 | 19,5 h | 81,3% |
| 12 | 18,0 h | 75% |
| 11 | 16,5 h | 68,8% |
| 10 | 15,0 h | 62,5% |
| 8 | 12,0 h | 50% |

**Aula de 60 min (trilha 8–12):**

| Presenças | Horas frequentadas | % da carga |
|---|---|---|
| 12 | 12,0 h | 100% |
| 11 | 11,0 h | 91,7% |
| 10 | 10,0 h | 83,3% |
| 9 | 9,0 h | 75% |
| 8 | 8,0 h | 66,7% |
| 7 | 7,0 h | 58,3% |
| 6 | 6,0 h | 50% |

**Como declarar no certificado:** escreva a carga **real frequentada** quando o
aluno ficar abaixo de 75% de presença, com o total de aulas frequentadas entre
parênteses. Exemplo: `21 horas (14 de 16 aulas frequentadas)`.

---

## Privacidade e dados do certificado

| Faixa | Regra |
|---|---|
| **8–12** | Publicar **nome social ou apelido**. **Nunca** foto, e-mail, matrícula, endereço ou nome do responsável no documento público. Ter termo de autorização assinado e guardado |
| **13–17** | Nome completo é aceitável, com autorização do responsável para uso de imagem e voz. **Sem** CPF, e-mail, telefone ou matrícula no documento público |
| **18+** | Nome completo com **consentimento expresso** do titular. O certificado não substitui um certificado de curso técnico reconhecido pelo MEC |

| Princípio | Como aplicar |
|---|---|
| **Dado mínimo** | No certificado público entram só os 7 campos do modelo — nada mais |
| **Finalidade** | O registro existe para **comprovar a conclusão**. Não é lista de contato nem material de divulgação sem autorização |
| **Guarda** | A lista de códigos é mantida conforme a política da instituição; dados que não precisam ser guardados, são eliminados |
| **Dúvida jurídica** | [ANPD — Autoridade Nacional de Proteção de Dados](https://www.gov.br/anpd/pt-br) e a coordenação jurídica da instituição |

> Checklist de segurança de crianças completo em
> `00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md` §9.

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Certificado emitido | Todos os campos obrigatórios preenchidos, com **código de verificação** único |
| Critérios de emissão | Frequência, entregáveis e projeto final apresentado conferidos e registrados |
| Página de verificação | O código digitado devolve os dados do certificado (ou "não encontrado") |
| Conversão de horas | A carga horária do certificado bate com o plano da trilha e com a frequência real |
| Privacidade | Nenhum dado além dos campos do modelo no documento público |

**Pergunta de escrita:**
> "Um aluno de 13 anos faltou a 5 das 16 aulas, mas entregou o projeto final
> completo, com testes, commits e README, e apresentou no Showcase. Ele recebe
> certificado?"
> **Resposta:** Recebe, e o certificado declara a carga **correspondente ao que ele
> frequentou**: 11 aulas × 90 min = 990 min = **16,5 horas**. O motivo é simples — a
> carga horária do certificado é uma **declaração factual**, não um prêmio. Dizer
> "24 horas" para quem não fez 16 horas é declarar algo falso, e é exatamente esse
> tipo de incoerência que faz um certificado perder valor. Os critérios de
> emissão pedem 75% de frequência **para compensar**, não para reprovar: como os
> entregáveis e o projeto final estão completos, a compensação foi feita e o
> certificado é emitido com a carga correta. E o que ele ganhou foi o que
> importa: a experiência de ter construído e publicado um projeto de verdade.

---

## 🏠 Para casa

1. Copie o modelo do certificado para um documento editável e preencha **um**
   certificado fictício de teste, com o código `MTD-A8-2026-000` — confira se
   todos os campos cabem na página e se a diagramação fica boa impressa.
2. Monte a planilha de códigos com as colunas: código, nome (ou apelido), trilha,
   data, situação, observação do conceito.
3. Se for emitir online, publique a `verificar.html` com **dois** certificados de
   teste (um válido e um código inexistente) e confira os dois caminhos da página.

---

## 🔗 Links

- [Rubrica geral (conceito antes da emissão)](01-rubrica-avaliacao.md)
- [Rubricas por trilha (8–12, 13–17, 18+)](02-rubricas-por-trilha.md)
- [Quizzes formativos rápidos](03-quizzes-formativos.md)
- [Guia do professor — Metodologia, Avaliação e Rubricas](../00-GUIA-DO-PROFESSOR/03-metodologia-e-avaliacao.md)
- [Projeto final 8–12 (entrega do certificado na Mostra de resultados)](../01-CRIANCAS-8-12/07-projeto-final.md)
- [Plano da trilha 8–12 — Exploradores](../01-CRIANCAS-8-12/00-plano-da-trilha.md)
- [Plano da trilha 13–17 — Makers/Devs](../02-ADOLESCENTES-13-17/00-plano-da-trilha.md)
- [Plano da trilha 18+ — Profissionais](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md)
- [ANPD — Autoridade Nacional de Proteção de Dados](https://www.gov.br/anpd/pt-br)
- [GitHub Pages](https://pages.github.com/)

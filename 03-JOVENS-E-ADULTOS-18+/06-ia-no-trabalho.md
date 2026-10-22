# Módulo 6 — Inteligência artificial no trabalho (18+)

**Duração:** 90 min · **Aula 6 de 16**
**Pré-requisito:** Módulos 2 e 4.
**Entregável:** um fluxo de trabalho com IA documentado + checklist de verificação das respostas.

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Explicar, em linguagem simples, como um modelo generativo produz texto e por que ele **inventa com confiança**.
2. Escrever prompts com papel, contexto, tarefa, formato e restrições, e avaliar o resultado com critérios.
3. Definir o que **nunca** enviar a uma ferramenta de IA e quando a revisão humana é obrigatória.

**Objetivo secundário:** medir, de forma honesta, quanto tempo a IA economizou — e quanto tempo a verificação consumiu.

---

## 📚 Fontes no repositório

| Repositório | O que usar |
|---|---|
| `ia-para-iniciantes/` | Conceitos, aplicações e limites (verifique as pastas antes de citar) |
| `prompts-recipe-to-create-a-ebook/` | Exemplo de prompts encadeados para produzir material |
| `agente_qaIA/` | Ideia de agente que apoia testes |
| `laboratorio-tech-social/trilhas/adultos-18+/modulo-06-ia-no-trabalho.md` | Versão resumida da trilha |
| `Analise-de-Dados/` | Onde a IA apoia a análise — e onde atrapalha |

**Links:**
[Guia de prompts (OpenAI)](https://platform.openai.com/docs/guides/prompt-engineering) ·
[Google Colab](https://colab.research.google.com/) ·
[Documentação do Python](https://docs.python.org/pt-br/3/)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Token** | "Pedaço de palavra: o modelo trabalha com pedaços, não com letras." |
| **Previsão** | "O modelo escolhe o próximo token mais provável — não consulta um banco de fatos." |
| **Treino vs inferência** | "Treino é aprender; inferência é responder. Na inferência ele não aprende com você." |
| **Alucinação** | "Resposta falsa com tom de certeza." |
| **Viés** | "O modelo repete padrões dos dados com que foi treinado." |
| **Janela de contexto** | "O que cabe na conversa; o que ficou fora, ele não 'lembra'." |
| **Prompt** | "O pedido: quanto mais claro o pedido, menos adivinhação." |
| **Revisão humana** | "A responsabilidade final é sempre de uma pessoa." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Peça a uma IA para citar cinco artigos científicos sobre um tema obscuro. Ela vai citar cinco — com autores, revistas e anos. Alguns podem não existir. E o texto continua impecável."*

Faça a demonstração ao vivo e depois **verifique** uma das citações. A turma vê a alucinação acontecer.

**Pergunta inicial:** *"Em que tarefas você confiaria na IA sem conferir? Em quais não confiaria de jeito nenhum?"*

### Fase 2 — Exploração (20 min)

**Parte 1 — Como funciona, sem matemática (7 min).**
Mostre a frase: *"O gato subiu no ___"*. O modelo calcula probabilidades para o próximo pedaço. Repita com uma pergunta factual e mostre que a mesma mecânica se aplica: ele **gera** uma resposta provável, não **consulta** a verdade.

Consequências práticas:
- datas, números, leis e citações → **sempre verificar**;
- texto genérico e reescrita → risco menor;
- dados confidenciais → **nunca** colar em ferramenta pública.

**Parte 2 — Anatomia de um prompt (8 min).**

```text
PAPEL:      "Você é um revisor técnico exigente."
CONTEXTO:   "O público é iniciante; o texto será lido em voz alta."
TAREFA:     "Reescreva o parágrafo abaixo em até 80 palavras."
FORMATO:    "Uma lista de 3 itens, cada um com no máximo 20 palavras."
RESTRIÇÕES: "Não invente dados; se faltar informação, diga o que falta."
```

Compare um prompt vago (`"melhore este texto"`) com o estruturado. Peça que a turma aponte o que mudou no resultado.

**Parte 3 — Avaliação com critérios (5 min).**

| Critério | Pergunta |
|---|---|
| Correção | O que é fato foi verificado? |
| Adequação | Serve ao público e ao formato pedido? |
| Completude | Respondeu tudo o que foi pedido? |
| Risco | Há dado sensível, viés ou conselho perigoso? |

Nota de 0 a 3 em cada critério; abaixo de 2 em **correção** → descartar ou refazer.

### Fase 3 — Mão na massa (40 min)

**Atividade A — Prompt ruim vs. prompt bom (15 min).**
Em duplas, escolham uma tarefa real (escrever e-mail, resumir relatório, gerar caso de teste). Escrevam duas versões do prompt, executem e comparem com a tabela de critérios. Registrem a diferença.

**Atividade B — Verificação de fatos (15 min).**
Peça à IA um parágrafo com **três afirmações verificáveis** sobre um tema do curso. Verifiquem cada uma em fonte primária. Registrem:

| Afirmação | Fonte | Confere? |
|---|---|---|

Discutam: quantas passaram? O texto "parecia" confiável?

**Atividade C — Fluxo seguro (10 min).**
Desenhem o fluxo do uso de IA no trabalho:

```text
tarefa -> posso enviar estes dados? -> prompt -> resposta
       -> verificação humana -> uso -> registro do que foi feito
```

Listem o que **nunca** entra no prompt: dados pessoais de clientes, senhas e chaves, dados de menores, informações sob sigilo, conteúdo de terceiros sem autorização.

### Fase 4 — Projeto (15 min)

**Desafio: "Meu fluxo com IA"**
Documente **um** fluxo de trabalho com IA no seu projeto do Módulo 4 ou 5: tarefa, prompt reutilizável, critérios de avaliação, verificação e tempo medido.

**Critério de pronto:**
- [ ] Tarefa delimitada (não "usar IA para tudo")
- [ ] Prompt com papel, contexto, tarefa, formato e restrições
- [ ] Tabela de avaliação preenchida para 3 respostas
- [ ] Verificação de fatos registrada
- [ ] Lista do que nunca é enviado
- [ ] Tempo economizado **e** tempo de verificação medidos

### Fase 5 — Mostra (5 min)

Cada dupla mostra um caso em que a IA **falhou** e como percebeu. O objetivo é treinar o ceticismo, não a admiração.

**Pergunta de saída:** *"Por que 'a IA disse' não é fonte?"*

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Comparação de prompts | Diferença explicada com critérios |
| Verificação | Confere afirmações em fonte primária |
| Fluxo | Identifica o que pode e o que não pode ser enviado |
| Documentação | Prompt, avaliação e medição registrados |

**Pergunta de escrita:**
> "Um colega usa IA para resumir contratos de clientes e cola o texto inteiro na ferramenta gratuita. Quais são os dois problemas?"
> **Resposta:** (1) **Confidencialidade/LGPD** — dados de terceiros e informações sob sigilo foram enviados a um serviço externo, possivelmente usados para treino; (2) **Confiabilidade** — o resumo pode omitir cláusulas ou inventar obrigações, e a responsabilidade continua sendo de quem assina. O correto é usar ferramenta aprovada, anonimizar, limitar o trecho e revisar com especialista.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `ia-para-iniciantes/` | Conceitos e aplicações |
| `prompts-recipe-to-create-a-ebook/` | Prompts encadeados |
| `agente_qaIA/` | Automação de testes com apoio de IA |
| `laboratorio-tech-social/trilhas/adultos-18+/modulo-06-ia-no-trabalho.md` | Versão da trilha |

---

## 🏠 Para casa

Crie uma **biblioteca pessoal de 5 prompts** reutilizáveis, cada um com: objetivo, prompt, exemplo de boa resposta, critérios de verificação. Compartilhe com a equipe e registre o que funcionou.

---

## 🔗 Próximo módulo

[Módulo 7 — Projeto final: automatize um processo real](07-projeto-final.md)

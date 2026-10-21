# 🧭 Metodologia, Avaliação e Rubricas

Baseado em `laboratorio-tech-social/docs/plano-pedagogico.md` e nas evidências
científicas citadas nos seus próprios materiais (as "ciências" dos blocos verdes nas
trilhas HTML do repositório).

---

## 1. Os 5 princípios (verbatim do seu plano pedagógico)

1. **Gratuidade total** — nenhuma aula, material ou ferramenta pode ter custo para o aluno.
2. **Acesso aberto** — todo conteúdo é público e reutilizável (licença MIT).
3. **Aprender fazendo** — aulas baseadas em projetos, não em teoria pura.
4. **Inclusão** — acolher iniciantes, meninas e grupos subrepresentados na tecnologia.
5. **Segurança** — proteção de menores em primeiro lugar.

---

## 2. O ciclo de aula (verbatim do plano pedagógico)

```
Apresentação do problema  →  Exploração  →  Mão na massa  →  Projeto  →  Mostra de resultados
```

- Aulas de **60 a 90 minutos**.
- Ritmo **semanal** (presencial ou online).
- Ferramentas gratuitas: **Scratch, Python, Google Colab, GitHub Pages, Figma**.
- Avaliação é **formativa**: projetos e participação, **nunca prova eliminatória**.

> ⚠️ Isso é importante e vai contra a maioria dos métodos escolares: **não tire prova
> eliminatória**. O `05-AVALIACAO/` deste material traz quizzes formativos e simulados
> **para autoavaliação e para o professor entender o nível da turma**, não para reprovar.

---

## 3. As 4 evidências científicas que o seu material já usa

As trilhas HTML do `laboratorio-tech-social` citam essas bases — use-as para justificar
suas escolhas ao coordenar pedagogical:

| Princípio | Fonte citada no repo | Aplicação na aula |
|---|---|---|
| **Aprendizagem ativa** supera aula passiva | Freeman et al., 2014 | Nunca passar 20 min só explicando. A regra é 1/3 teoria, 2/3 prática. |
| **Recuperação prática** fixa mais que reler | Karpicke, 2012 | Quiz no início da aula (perguntar o que ficou da aula passada), não no fim. |
| **Prática espaçada** > treino único | Karpicke, 2012 | 10 min por dia de digitação > 2 h só na véspera. Use o histórico do `meu-treino`. |
| **Construcionismo** (aprender construindo) | Seymour Papert | Toda aula termina com algo que a turma **construiu**. |
| **Alfabetização midiática e informacional (MIL)** | UNESCO | Verificar antes de repostar; pensar antes de acreditar e antes de postar. |

**Leitura lateral** (Stanford History Education Group): em vez de ler só a página,
abrir outra aba e conferir **quem escreveu** e se outros sites confirmam.
**Teste CRAAP**: **C**orrente, **R**elevante, de **A**utoridade, **A**corrível, com **P**ropósito claro.

---

## 4. Rubrica de avaliação formativa

### 4.1 Crianças (8–12) — 4 níveis

| Nível | Descrição | Pontos |
|---|---|---|
| 🌱 **Semente** | Participou e tentou. Ainda precisa de apoio passo a passo. | 1 |
| 🌿 **Broto** | Concluiu a tarefa com alguma ajuda. Explica uma parte do que fez. | 2 |
| 🌳 **Árvore** | Concluiu sozinho e **explica** o raciocínio. | 3 |
| 🌟 **Floresta** | Concluiu, explicou e **ajudou um colega**. | 4 |

**Instrumentos:** quiz rápido de 4 perguntas (modelo em `site/trilhas/*/07-informatica.html`),
observação do professor, arquivo entregue, apresentação oral de 1 min.

### 4.2 Adolescentes (13–17) — 4 níveis

| Nível | Descrição | Pontos |
|---|---|---|
| 1 | Entregou parcial ou não entregou. | 1 |
| 2 | Entregou o mínimo pedido, com erros conceituais. | 2 |
| 3 | Entregou completo, código/diagrama correto e **documentado**. | 3 |
| 4 | Entregou completo, **refatorou**, documentou e **publicou** (no GitHub). | 4 |

**Instrumentos:** código no repositório do aluno (link), README, quiz, apresentação.

### 4.3 Adultos (18+) — 4 níveis (comunyão de mercado)

| Nível | Descrição |
|---|---|
| 1 | Não entregue. |
| 2 | Entregue com falha funcional ou sem documentação. |
| 3 | Entregue, testado, documentado. |
| 4 | Entregue, testado, documentado, com **métricas** (cobertura, KPI, tempo) e análise de risco. |

Use os scripts do `manual-qa-completo` como referência de "o que se espera de um
profissional": `docs/09/scripts/kpi.py` (KPIs), `docs/08/scripts/quality_gate.py`
(gate de qualidade), `docs/03/scripts/estimate.py` (estimativa PERT).

---

## 5. Como usar os quizzes sem virar prova

| Instrumento | Quando usar | Como aplicar |
|---|---|---|
| Quiz no início da aula | Toda aula | Pergunta de recuperação da aula anterior. Sem nota, só para o professor ver se precisa retomar. |
| Quiz no fim da aula | Toda aula | O aluno corrige sozinho (gabarito visível depois). Guarde para o próximo planejamento. |
| `QA_RUN` → Quiz Duel | B7 (QA) | 5 categorias × 5 perguntas, 30 s cada. É **brincadeira**, não prova. |
| `questionario_despertardaqualidade` | B7 | 10 perguntas V/F de qualidade de software. Use como autoavaliação. |
| `qa-exercicios-praticos/simulados/` | C3 (adultos) | 20 questões com gabarito comentado. **Situação**, não eliminação. |
| `ia-para-iniciantes` | B8 | 90 exercícios com "CRITÉRIOS DE AVALIAÇÃO" e "DICAS" — já é autoavaliativo. |
| `laboratorio-tech-social/site/quiz-*.html` | Crianças, B7, B10 | 3 quizzes prontos: `quiz-criancas.html`, `quiz-teens.html`, `quiz-ciberseguranca.html`. |

---

## 6. Feedback

O plano pedagógico define: **"Feedback semanal dos alunos (formato lúdico)"**
e **"Reunião mensal de voluntários para melhorar o conteúdo"**.

### Formato de feedback semanal (5 min, no fim da aula)

1. **Uma palavra:** o que mais te marcou hoje?
2. **De 0 a 10:** quão travado você se sentiu?
3. **Uma coisa** que você quer que eu explique de novo.

Registre em uma planilha. Depois de 4 semanas, olhe a coluna das palavras repetidas —
é o seu próximo ajuste de aula.

---

## 7. Metas do aluno por trilha

### Exploradores (8–12) — do plano pedagógico
- Compreender o que é um computador e como ele pensa (lógica).
- Criar animações e jogos simples.
- Montar circuitos básicos e entender sensores.
- Publicar uma página web própria.

### Makers/Devs (13–20) — do plano pedagógico
- Programar em Python com confiança.
- Construir sites e pequenas aplicações web.
- Aplicar noções de testes de software (QA) e qualidade.
- Analisar dados e contar histórias com números.
- Conceber e entregar um projeto de impacto social em open source.

---

## 8. Inclusão — práticas concretas

Do princípio "Inclusão — acolher iniciantes, meninas e grupos subrepresentados na tecnologia":

| Prática | Como aplicar |
|---|---|
| **Nunca expor aluno tímido** | A "mostra de resultados" é voluntária. Quem quiser, mostra. |
| **Nunca assumir que "já sabe" | Pergunte o nível antes do curso (`docs/guia-do-voluntario.md`). |
| **Duplas estratégicas** | Alunos mais avan[cç]ados pareados com iniciantes — o nível 4 da rubrica exige "ajudou um colega". |
| **Ferramentas gratuitas sempre** | Nenhuma aula pode depender de plano pago. GitHub, Python, Colab, Scratch, SQLite, VS Code — tudo gratuito. |
| **Material não é opcional** | O `laboratorio-tech-social` tem `modelo-certificado.md`, `guia-do-voluntario.md` e `site/certificado/verificar.html`. Todo aluno sai com certificado. |
| **Língua** | Todo o material é PT-BR; o `ingles-para-programadores` existe exatamente para não excluir quem ainda não lê inglês técnico. |

---

## 9. Segurança de crianças — checklist antes de cada aula

Baseado em `laboratorio-tech-social/docs/seguranca-criancas.md`:

- [ ] Não expor nome completo, endereço, telefone, RG, foto ou dados de saúde de aluno.
- [ ] Não usar e-mail real do aluno para cadastro em serviço externo sem autorização.
- [ ] Senhas: gerar descartáveis por aula e apagar ao final.
- [ ] Chaves de API (OpenAI, Gemini, Supabase, NewsAPI): conta do professor ou variável de ambiente — **nunca no navegador do aluno com dados reais**.
- [ ] Links externos: verificar antes de usar com crianças.
- [ ] Atividades física/presenciais: manter a turma no campo de visão.
- [ ] Registros de progresso: identificar por apelido/código, não por nome completo.
- [ ] Em caso de dúvida: consultar `docs/seguranca-criancas.md` antes da aula, não depois.

---

## 10. Checklist semanal do professor

| # | Tarefa | Onde |
|---|---|---|
| 1 | Ler o módulo do repositório correspondente **antes** da aula | ver `02-mapa-repositorio-para-aula.md` |
| 2 | Testar o código/exercício localmente | os `.txt` de exercício e os scripts do `manual-qa-completo` |
| 3 | Preparar o slide | `laboratorio-tech-social/materiais/slides/template-slides.html` |
| 4 | Conferir o material offline (plano B) | `01-plano-de-ensino-geral.md` seção 6 |
| 5 | Testar login/chave de API com a conta do professor | — |
| 6 | Aplicar o quiz de recuperação | quiz do início da aula |
| 7 | Aplicar o feedback semanal (5 min) | seção 6 |
| 8 | Registrar ponto de atenção de cada aluno | planilha |
| 9 | Publicar o resultado da aula no repositório da turma | `git-github-iniciantes/09_github_pages/` |

---

## 11. Onde está o material de avaliação pronto nos repositórios

| Item | Caminho |
|---|---|
| Quiz de crianças (4 perguntas) | `laboratorio-tech-social/site/trilhas/criancas/07-informatica.html` (bloco `<script>`) |
| Quiz de teens (6 perguntas) | `laboratorio-tech-social/site/trilhas/adolescentes/08-informatica.html` |
| Quiz de cibersegurança | `laboratorio-tech-social/site/exercicios/quiz-ciberseguranca.html` |
| Quiz de QA (10 V/F) | `questionario_despertardaqualidade/index.html` + `script.js` |
| Simulado 1 (fundamentos QA) | `qa-exercicios-praticos/simulados/simulado-01-fundamentos.md` |
| Simulado 2 (API, SQL, segurança) | `qa-exercicios-praticos/simulados/simulado-02-api-sql-seguranca.md` |
| Quiz Duel em formato jogo | `QA_RUN/js/games/quizduel.js` |
| Checklist de aceite | `manual-qa-completo/docs/10/PT/checklist_aceite.md` |
| Matriz de rastreabilidade | `manual-qa-completo/docs/10/PT/matriz_rastreabilidade.md` |
| Glossário QA PT/EN | `manual-qa-completo/docs/10/PT/glossario.md` |
| Rubrica de carreira e certificações | `manual-qa-completo/docs/01/PT/indice.md` §1.10 |
| Lista de livros de QA | `QualityHub/Indicação de livros/Indicações.md` |

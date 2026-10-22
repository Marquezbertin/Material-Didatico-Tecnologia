# Módulo 5 — Segurança digital e LGPD (18+)

**Duração:** 90 min · **Aula 5 de 16**
**Pré-requisito:** Módulos 1 a 4.
**Entregável:** auditoria de 30 minutos + política de proteção de dados de uma página para o projeto.

---

## 🎯 Objetivo

Ao final da aula, o aluno será capaz de:

1. Aplicar as medidas de segurança com maior impacto: senha única, 2FA, atualização e backup 3-2-1.
2. Distinguir controlador, operador e titular, e reconhecer as bases legais da LGPD no próprio trabalho.
3. Escrever a política de proteção de dados do seu projeto, com finalidade, minimização e prazo de guarda.

**Objetivo secundário:** reconhecer um golpe de engenharia social antes de clicar.

---

## 📚 Fontes no repositório

| Repositório | O que usar |
|---|---|
| `pensamento_computacional/13_ciberseguranca/` | Exercícios de segurança da informação |
| `pensamento_computacional/15_etica_sociedade/` | Ética, sociedade e tecnologia |
| `laboratorio-tech-social/docs/seguranca-criancas.md` | Regras de proteção de menores (leia antes de publicar qualquer projeto) |
| `questionario/` | Exemplo de aplicação que coleta dados — analise o que ela pede |
| `o-despertar-qa/` | Projeto real com boas práticas de repositório |

**Links:**
[ANPD — Autoridade Nacional de Proteção de Dados](https://www.gov.br/anpd/) ·
[Lei 13.709/2018 (LGPD)](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm) ·
[CS Unplugged](https://classic.csunplugged.org/) ·
[Cartilha de segurança para internet (CERT.br)](https://cartilha.cert.br/)

---

## 🧠 Conceitos-chave

| Conceito | Frase que fixa |
|---|---|
| **Confidencialidade** | "Só quem deve ver, vê." |
| **Integridade** | "O dado não foi alterado no caminho." |
| **Disponibilidade** | "Quando eu preciso, está lá." |
| **Não repúdio** | "Não dá para negar que a ação aconteceu." |
| **2FA** | "Senha + um segundo fator: uma senha vazada não basta." |
| **Backup 3-2-1** | "Três cópias, dois tipos de mídia, uma fora do local." |
| **Controlador** | "Quem decide por que e como os dados são tratados." |
| **Operador** | "Quem trata os dados em nome do controlador." |
| **Titular** | "A pessoa a quem os dados pertencem." |
| **Minimização** | "Colete só o que é necessário para a finalidade." |
| **Engenharia social** | "O golpe explora a pessoa, não o computador." |

---

## ⏱️ Roteiro (90 min)

### Fase 1 — Apresentação (10 min)

**Gancho:** *"Nenhum dos maiores vazamentos recentes começou com um gênio do mal quebrando a criptografia. Começou com uma senha reutilizada, um servidor sem atualização ou alguém que clicou em um link."*

Mostre duas mensagens lado a lado (uma legítima e uma de phishing) e peça que a turma aponte as diferenças: remetente, urgência, link, pedido de código.

**Demonstração (4 min):** verifique no [Have I Been Pwned](https://haveibeenpwned.com/) um e-mail de teste (nunca o pessoal de outra pessoa) e mostre o que um vazamento significa na prática.

### Fase 2 — Exploração (20 min)

**Parte 1 — As quatro medidas que resolvem a maior parte (8 min).**

| Medida | O que fazer | Por que resolve |
|---|---|---|
| Senha única | Gerenciador de senhas + frase longa | impede o "efeito dominó" entre sites |
| 2FA | Aplicativo autenticador ou chave física | senha sozinha não basta |
| Atualização | Ativar atualização automática | fecha falhas já exploradas |
| Backup 3-2-1 | Rotina automática + teste de restauração | ransomware não vence quem tem cópia |

**Parte 2 — LGPD em 10 minutos (7 min).**
Pergunte: *"Quando você preenche um cadastro, quem é o titular? Quem decide o que será feito com os dados?"*

```text
Titular      -> você
Controlador  -> quem decide a finalidade e os meios (a empresa)
Operador     -> quem executa o tratamento em nome do controlador
```

Bases legais mais comuns: consentimento, execução de contrato, obrigação legal, legítimo interesse. **Consentimento não é a única base — e não é carta branca.**

**Parte 3 — Segurança no código (5 min).**

```python
import os
chave = os.environ.get("CHAVE_API")   # variável de ambiente, nunca no código
if not chave:
    raise SystemExit("Defina CHAVE_API antes de rodar")
```

```gitignore
.env
*.pem
*.key
```

Regra: se um segredo apareceu no commit, **revogue**. Apagar o arquivo não apaga o histórico.

### Fase 3 — Mão na massa (40 min)

**Atividade A — Auditoria de 30 minutos (15 min).**
Liste suas contas em uma tabela e marque:

| Conta | Senha única? | 2FA? | Atualizada há menos de 1 ano? | Backup? |
|---|---|---|---|---|
| e-mail principal | | | | |
| banco | | | | |
| GitHub | | | | |

Feche as três lacunas mais graves **na aula** (ativar 2FA, trocar senha repetida, criar backup).

**Atividade B — Caça ao phishing (10 min).**
Em duplas, analisem 4 mensagens fictícias. Para cada uma, registrem: sinal de alerta, ação segura e o que fazer se o clique já aconteceu (trocar senha, revogar sessão, avisar o suporte).

**Atividade C — Política do projeto (15 min).**
Preencha o modelo:

```text
POLÍTICA DE PROTEÇÃO DE DADOS — <projeto>
1. Quais dados coletamos:
2. Para que finalidade:
3. Base legal:
4. Por quanto tempo guardamos:
5. Com quem compartilhamos:
6. Onde ficam armazenados:
7. Como o titular pede acesso/correção/exclusão:
8. Quem é o responsável:
9. Data da última revisão:
```

Se o projeto envolve menores: **sem dados reais de alunos**, sem contato direto, consentimento do responsável quando houver publicação.

### Fase 4 — Projeto (15 min)

**Desafio: "Meu projeto em conformidade"**
Aplique a política ao projeto do Módulo 4: remova os dados que não são necessários, defina prazo de guarda, crie o aviso de privacidade e proteja os arquivos com dados pessoais.

**Critério de pronto:**
- [ ] Política de 1 página preenchida
- [ ] Nenhum dado pessoal real em repositório público
- [ ] Segredos fora do código e do histórico
- [ ] Backup testado (restaurou pelo menos um arquivo)
- [ ] 2FA ativo nas três contas principais
- [ ] Prazo de guarda definido e justificado

### Fase 5 — Mostra (5 min)

Cada dupla apresenta **um risco** e **a medida** que adotou. A turma vota na medida mais eficaz por esforço.

**Pergunta de saída:** *"Por que apagar um arquivo com senha do repositório não resolve o vazamento?"*

---

## 📝 Avaliação

| Instrumento | Critério |
|---|---|
| Auditoria | Três lacunas fechadas na aula |
| Phishing | Identifica sinais e ação correta |
| Política | Nove campos preenchidos com coerência |
| Código | Nenhum segredo no repositório |
| Backup | Restauração testada |

**Pergunta de escrita:**
> "Um cliente pede a exclusão dos dados dele. A empresa diz que 'não pode apagar por causa do backup'. Está correto?"
> **Resposta:** A LGPD prevê a eliminação, com exceções legais (obrigação legal, exercício de direitos, etc.). O backup pode ser mantido pelo ciclo técnico, mas deve ser tratado com segurança e não pode servir de desculpa para uso contínuo; o pedido precisa de resposta formal e registro. Quando há obrigação de guarda, o titular deve ser informado do fundamento.

---

## 🧩 Exercícios extras (do repositório)

| Arquivo | Sobre |
|---|---|
| `CyberSec-_Crosswords/` | Palavras cruzadas de segurança (aquecimento) |
| `pensamento_computacional/13_ciberseguranca/` | 12 exercícios de segurança |
| `pensamento_computacional/15_etica_sociedade/` | Dilemas éticos e tecnologia |
| `laboratorio-tech-social/docs/seguranca-criancas.md` | Regras obrigatórias para projetos com menores |

---

## 🏠 Para casa

Escreva o **aviso de privacidade** do seu projeto em linguagem simples (máximo 200 palavras), com um exemplo de como o titular exerce cada direito. Depois, faça a revisão de segurança de um projeto de um colega usando a política dele como checklist.

---

## 🔗 Próximo módulo

[Módulo 6 — Inteligência artificial no trabalho](06-ia-no-trabalho.md)

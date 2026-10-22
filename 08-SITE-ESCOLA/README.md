# Sala de Aula no site (Wix + Google Classroom)

Esta pasta contém a página que apresenta a sala de aula no **despertarqa.net** e o guia para montar as turmas no **Google Classroom** — a opção gratuita escolhida.

**Divisão de papéis**

| Onde | O que fica |
|---|---|
| **Wix** (`despertarqa.net`) | Vitrine: explica o curso, mostra as turmas, leva ao Classroom e ao material |
| **Google Classroom** | Sala real: login, vídeos, podcasts, materiais, avisos, dúvidas e entregas |
| **GitHub** | Material didático aberto (livros em PDF, planos, exercícios) |

Nada é pago: Classroom, Drive, YouTube e GitHub têm plano gratuito. O Wix que você já tem continua sendo só o site.

---

## 1. Arquivos

| Arquivo | Para que serve |
|---|---|
| `sala-de-aula.html` | Página pronta para publicar no Wix (ou usar como modelo visual) |
| `README.md` | Este guia |

**Antes de publicar**, abra o HTML e procure por `SUBSTITUA` (são 10 links; o bloco de aviso também usa a palavra). Troque:

| Marcador | Substituir por |
|---|---|
| `SUBSTITUA_PELO_CONVITE_CLASSROOM_8_12` | Link de convite da turma 8–12 |
| `SUBSTITUA_PELO_CONVITE_CLASSROOM_13_17` | Link de convite da turma 13–17 |
| `SUBSTITUA_PELO_CONVITE_CLASSROOM_18` | Link de convite da turma 18+ |
| `SUBSTITUA_PELO_LINK_DO_PODCAST_8_12` | Link do episódio/playlist da turma |
| `SUBSTITUA_PELO_LINK_DO_PODCAST_13_17` | Link do episódio/playlist da turma |
| `SUBSTITUA_PELO_LINK_DO_PODCAST_18` | Link do episódio/playlist da turma |
| `SUBSTITUA_PELO_EMAIL` | E-mail que recebe as dúvidas (aparece 4 vezes) |

Depois de substituir, **apague o bloco vermelho de configuração** entre os comentários `<!-- ⚠️ BLOCO DE CONFIGURAÇÃO` e `<!-- ⚠️ FIM DO BLOCO`.

Para testar: clique com o botão direito no arquivo → **Abrir com** → navegador. Confira os links e o layout no celular (F12 → modo dispositivo).

---

## 2. Pré-requisitos

| Item | Situação |
|---|---|
| Conta Google da escola | Necessária para criar as turmas |
| Google Classroom | Gratuito em `classroom.google.com` |
| Contas dos alunos | Cada aluno precisa de uma conta Google |
| Alunos de 8 a 12 anos | **Atenção:** o Google exige idade mínima (13 anos no Brasil). Para menores, use **Google Workspace for Education** (gratuito para instituições de ensino) ou **Family Link**, com consentimento do responsável. Confirme a regra vigente antes de criar as contas |
| Vídeos | Arquivos no Drive ou canal do YouTube |
| Podcast | Arquivos MP3 no Drive, Spotify ou Anchor |
| Wix | Plano atual do site, com possibilidade de editar páginas |

> **Alternativa para 8–12 sem conta Google:** mantenha essa turma na área de membros do Wix ou entregue o material impresso e use o Classroom apenas como mural do professor. Não crie uma conta única compartilhada: isso elimina a privacidade e a individualização.

---

## 3. Criar as turmas no Classroom

1. Entre em `classroom.google.com` com a conta da escola.
2. **Criar turma** → nome padronizado:
   - `Despertar QA · 8–12 · Exploradores`
   - `Despertar QA · 13–17 · Makers`
   - `Despertar QA · 18+ · Prática`
3. Em **Configurações da turma**, copie o **código da turma** e guarde.
4. Convide os alunos por e-mail (aba **Pessoas** → **Convidar**).
5. Em **Configurações**, defina:
   - `Quem pode postar no mural`: somente professores;
   - `Quem pode comentar`: alunos (se quiser moderação, desligue e use comentários particulares);
   - `Resumo semanal`: ativado para responsáveis poderem acompanhar.

**Regra de ouro:** uma turma por faixa etária. Nunca misture 8–12 com 18+ na mesma turma.

---

## 4. Organizar o conteúdo (modelo igual nas três turmas)

Crie os tópicos na aba **Atividades**:

```text
📌 Comece aqui        -> boas-vindas, como usar a turma, livro em PDF
🎬 Aulas              -> vídeo + resumo + exercício de cada aula
🎧 Podcast            -> episódios por módulo
📚 Material           -> livros, planos e banco de exercícios
📝 Atividades         -> entregas com prazo e rubrica
💬 Dúvidas            -> post fixo explicando os canais de contato
```

Cada aula vira uma **atividade** com:
- título `Aula 03 — Python: variáveis e entrada de dados`;
- vídeo (ver seção 5);
- uma pergunta de saída;
- prazo e critério de avaliação (copie da rubrica em `05-AVALIACAO/`).

---

## 5. Vídeos

| Forma | Privacidade | Recomendação |
|---|---|---|
| Vídeo no **Drive** anexado à atividade | Só quem tem acesso à turma | **Melhor opção**: o aluno assiste dentro do Classroom |
| **YouTube não listado** | Qualquer pessoa com o link | Aceitável para conteúdo público; o link circula |
| **YouTube público** | Aberto | Só para divulgação, nunca para aula com menores |

No Drive: clique com o botão direito no vídeo → **Compartilhar** → **Restrito** → adicione a turma. Depois, no Classroom, **Atividades → Adicionar → Drive**.

---

## 6. Podcast

1. Grave em MP3 (Audacity ou celular).
2. Suba no **Drive** (restrito à turma) ou publique no **Spotify for Creators/Anchor**.
3. No Classroom, anexe o arquivo ou o link no tópico `🎧 Podcast`.
4. No site, use o mesmo link no botão “Ouvir o podcast”.

Dica: nomeie `T03-episodio-variaveis.mp3` para o aluno achar fácil.

---

## 7. Material didático

Os arquivos já estão no GitHub, abertos:

| Turma | Livro | Trilha | Exercícios |
|---|---|---|---|
| 8–12 | [PDF 17 pág.](../07-LIVROS-PDF-PARA-ALUNO/LIVRO-DO-ALUNO-EXPLORADORES-DA-TECNOLOGIA-8-12.pdf) | [plano](../01-CRIANCAS-8-12/00-plano-da-trilha.md) | [fundamentos](../04-BANCO-DE-EXERCICIOS/01-exercicios-fundamentos.md) |
| 13–17 | [PDF 29 pág.](../07-LIVROS-PDF-PARA-ALUNO/LIVRO-DO-ALUNO-MAKERS-E-DESENVOLVEDORES-13-17.pdf) | [plano](../02-ADOLESCENTES-13-17/00-plano-da-trilha.md) | [Python](../04-BANCO-DE-EXERCICIOS/03-exercicios-python.md) |
| 18+ | [PDF 24 pág.](../07-LIVROS-PDF-PARA-ALUNO/LIVRO-DO-ALUNO-TECNOLOGIA-NA-PRATICA-18%2B.pdf) | [plano](../03-JOVENS-E-ADULTOS-18+/00-plano-da-trilha.md) | [simulados](../04-BANCO-DE-EXERCICIOS/07-provas.md) |

No Classroom, anexe o PDF como **material** (não como atividade) para o aluno baixar quando quiser.

---

## 8. Dúvidas por e-mail

Três canais, do mais privado ao mais geral:

1. **Comentário particular** na atividade (só aluno e professor veem) — use para notas e casos individuais.
2. **E-mail** `mailto:` do site — chega na caixa do professor com assunto já preenchido por turma.
3. **Mural** — apenas para dúvidas que interessam a todos.

Para o e-mail funcionar bem, crie um endereço dedicado, por exemplo `professor@despertarqa.net`, e responda em até 48 h úteis. Nunca peça dados sensíveis por e-mail.

---

## 9. Publicar no Wix

### Opção A — página nativa (recomendada)

1. No editor do Wix, crie a página `Sala de Aula` (`despertarqa.net/sala-de-aula`).
2. Use o HTML como **modelo visual**: título, três cartões (turmas), botões e perguntas frequentes.
3. Cada botão “Entrar na turma” aponta para o convite do Classroom (`target="_blank"`).
4. Adicione o livro em PDF como botão de download e o e-mail como link `mailto:`.

Vantagens: carrega rápido, é responsiva de verdade, indexa no Google e não tem iframe.

### Opção B — Embed HTML

1. Adicione o elemento **Embed HTML** (ou “HTML incorporado”).
2. Cole o conteúdo de `sala-de-aula.html`.
3. Defina altura entre **1200 e 1600 px** (o conteúdo rola dentro do quadro).
4. Confira no celular: o iframe pode cortar a largura; se cortar, use a opção A.

**Limitação real:** dentro do embed, o login do Google abre em outra aba (comportamento normal e seguro). Não tente reproduzir o login do Classroom dentro do Wix.

---

## 10. Privacidade e menores (LGPD)

- [ ] Nenhum nome, foto ou e-mail de aluno na página pública
- [ ] Convite nominal, nunca link aberto divulgado
- [ ] Responsáveis informados sobre o uso do Classroom
- [ ] Contas de menores criadas pela escola ou pelo responsável
- [ ] Vídeos e materiais restritos à turma
- [ ] Política de privacidade curta no site (o que se coleta e por quê)
- [ ] Canal para o responsável pedir acesso, correção ou exclusão

Base: [segurança para crianças](https://github.com/Marquezbertin/laboratorio-tech-social/blob/main/docs/seguranca-criancas.md) e [LGPD](https://www.gov.br/anpd/).

---

## 11. Checklist de publicação

- [ ] Três turmas criadas com nomes padronizados
- [ ] Convites enviados e aceitos por todos os alunos
- [ ] Tópicos criados nas três turmas
- [ ] Pelo menos a aula 1 com vídeo + atividade + prazo
- [ ] Podcast publicado e testado
- [ ] Livros anexados como material
- [ ] E-mail de dúvidas testado (envie um para você mesmo)
- [ ] `SUBSTITUA` trocado e bloco de configuração apagado
- [ ] Página publicada e testada no celular
- [ ] Links do site abrindo o Classroom correto
- [ ] Responsáveis avisados

---

## 12. Modelos de mensagem (copiar e colar)

**Convite para o aluno (13+)**

```text
Oi, [NOME]! Sua turma do Despertar QA já está no ar. 🎓

Entre pelo link: [LINK DO CONVITE]
Use o e-mail que a escola cadastrou. Se pedir código, é: [CÓDIGO DA TURMA]

Lá você encontra o vídeo da aula, o material em PDF e o espaço para tirar dúvidas.
Qualquer problema, responda esta mensagem.
```

**Comunicado aos responsáveis (8–12)**

```text
Olá, responsáveis pelo(a) [NOME]!

As aulas do Despertar QA começam em [DATA]. A sala on-line é fechada, por convite, e usamos o Google Classroom apenas para vídeos, materiais e devolutivas.

• A conta de [NOME] foi criada pela escola: [E-MAIL]
• O acesso é individual; não é necessário publicar nada nas redes
• Para dúvidas e ausências, fale com [PROFESSOR] pelo e-mail [E-MAIL]

O material também pode ser impresso e usado sem internet. Qualquer dúvida sobre dados ou privacidade, estou à disposição.
```

**Lembrete de primeira aula**

```text
Lembrete: a primeira aula da turma [TURMA] é [DATA], às [HORA].
Antes de entrar, assista ao vídeo de boas-vindas no Classroom e separe o livro em PDF.
Dúvidas: responda aqui ou use o comentário particular na atividade.
```

---

## 13. Manutenção mensal

| Tarefa | Tempo |
|---|---|
| Revisar links quebrados | 10 min |
| Publicar os episódios do mês | 20 min |
| Conferir entregas e devolutivas | 30 min |
| Atualizar avisos do mural | 10 min |
| Revisar permissões das turmas | 5 min |

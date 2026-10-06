---
description: Atualiza um post de um mês de uma marca (legenda, material do Drive, capa e status)
argument-hint: <marca> <dia/mês> + legenda e link do Drive (pode anexar prints)
---

Atualize um post no planejamento. Entrada do usuário: $ARGUMENTS

Leia primeiro o `CLAUDE.md` (identidade, anatomia da página, convenções de imagens). Trabalhe só na marca e no mês informados; se faltar a marca, o dia ou o mês, pergunte antes de mexer em qualquer arquivo.

## O que o usuário costuma enviar
- **Marca** (bendito, mane, ...) e **dia** (ex.: 04/10). Se o dia tiver mais de um post, ele diz qual (Reels, Post, Carrossel).
- **Legenda** completa (texto colado). Preserve quebras de linha e emojis exatamente como vieram.
- **Link do Google Drive** do material (arquivo ou pasta) e, se houver, da pasta dos stories do dia.
- Opcional: horário, editoria, capa anexada, mudança de formato.

## Passos
1. Abra a página do mês: `<marca>/AAAA-MM/index.html`. Localize o card do post (Bendito: `id="post-DD"`, ou `post-DD-2` para o segundo do dia; Mané: `id="post-NN"`, confira pela data dentro do card).
2. **Card (post a post):** coloque a legenda; troque `postcard-idea` (rascunho) por `postcard-legenda`; troque o botão "Material ainda não disponível" pelo botão do Drive ("Assistir material" para vídeo, "Abrir material no Drive" para pasta/arte), com `target="_blank" rel="noopener"`. Atualize horário/editoria se vierem.
3. **Capa:**
   - Se o material for **imagem/arte/carrossel**: baixe pelo conector do Google Drive, reduza para ~720 px de largura em JPG (PowerShell + System.Drawing; não há ffmpeg) e salve na pasta do mês seguindo as convenções de nome do `CLAUDE.md`. Para carrossel, salve todas as telas na galeria.
   - Se for **vídeo (Reels)**: tente a miniatura do próprio Drive; se não for possível extrair um quadro, **peça ao usuário um print/capa** e diga isso claramente. Não invente imagem.
   - Troque o bloco "Capa ainda não definida / Em criação" (`isdraft`) pelo `<img>` da capa.
4. **Grade do feed:** troque o tile "Em criação" pelo tile com a capa e a legenda de data/formato, no mesmo padrão dos outros.
5. **Calendário:** remova a marca de rascunho do dia/item (e o estilo tracejado do chip, se não restar nenhum rascunho no dia).
6. **Contadores/avisos:** se a página tiver contagem de "prontas / em criação" (Mané, no hero), atualize.
7. **Stories:** se o usuário enviou a pasta de stories do dia, atualize o link "Ver stories do dia".
8. Confira que todos os `src`/`href` novos existem, abra a página no navegador local (servidor estático) e verifique o card, a grade e o calendário. Se algo não puder ser verificado, diga.
9. Faça um commit local com mensagem clara (ex.: "Bendito 04/10: legenda e material"). **Não faça push**: avise que falta dar o Push origin no GitHub Desktop.

## Regras
- Não altere o visual nem posts que o usuário não citou.
- Se o Drive não abrir pelo conector (arquivo sem permissão), diga qual link falhou e o que o usuário precisa liberar.
- Resuma no final: o que mudou, o que ficou pendente (ex.: capa de vídeo) e o que não foi testado.
- Marcas ainda "em construção" (Espetto Carioca, Seu Rufino, Sirène) não têm página de mês: avise e pergunte se deve criar o mês primeiro.

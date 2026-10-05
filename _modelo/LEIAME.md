# Modelos de mês

Esta pasta guarda o HTML-base de um mês de cada marca com planejamento pronto:

- `bendito/index.html` — modelo do Momento Bendito (outubro/2026)
- `mane/index.html` — modelo do Boteco Mané (outubro/2026)

Servem como **referência do layout**. As imagens (`covers/`, `img/`, `stories/` etc.) **não** estão aqui; elas ficam em `bendito/2026-10/` e `mane/2026-10/`. Por isso, abrir estes arquivos diretamente mostra imagens quebradas — isso é esperado.

## Para uma marca que já tem mês publicado (Bendito, Mané)

Não use esta pasta: copie o mês mais recente da própria marca.

1. Copie `bendito/2026-10/` para `bendito/2026-11/` (ou `mane/...`).
2. Apague as imagens antigas e edite o `index.html` (hero, calendário, grade do feed, post a post, resultados zerados).
3. Adicione o mês em `bendito/index.html` e atualize o card em `/index.html`.

## Para uma marca nova (Espetto Carioca, Seu Rufino, Sirène)

1. Escolha o modelo mais próximo da personalidade da marca (Bendito = acolhedor/editorial; Mané = informal/irreverente).
2. Crie `<marca>/AAAA-MM/` e copie para lá o `index.html` do modelo. Crie as pastas de imagens seguindo a convenção do modelo escolhido.
3. Troque **cores, fontes, logo, textos e conteúdo** conforme o manual de marca. Mantenha a estrutura (barra de navegação do topo, hero, calendário, grade do feed, post a post, resultados).
4. Troque a página "em construção" da marca pela lista de meses (copie de `bendito/index.html`) e atualize o card na home.

Detalhes de identidade visual e convenções: veja `CLAUDE.md` na raiz.

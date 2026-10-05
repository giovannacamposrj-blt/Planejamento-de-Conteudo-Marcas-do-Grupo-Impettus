# Planejamento de Conteúdo · Marcas do Grupo Impettus

Site com os planejamentos mensais de conteúdo de Espetto Carioca, Boteco Mané, Momento Bendito, Buteco Seu Rufino e Sirène.

**Endereço:** https://planejamento-marcas-do-grupo-impett.vercel.app/

É um site simples: só arquivos HTML, CSS e imagens. Não tem login, banco de dados nem programa para instalar. Tudo que é publicado aqui fica acessível para quem tiver o link.

## O que já está no ar

| Marca | Situação |
|---|---|
| Momento Bendito | Outubro/2026 completo |
| Boteco Mané | Outubro/2026 completo |
| Espetto Carioca | Em construção |
| Buteco Seu Rufino | Em construção |
| Sirène | Em construção |

## Como o site é organizado

- `index.html` — página inicial com um card por marca.
- `bendito/`, `mane/`, `espetto-carioca/`, `seu-rufino/`, `sirene/` — uma pasta por marca, com a lista de meses.
- `bendito/2026-10/`, `mane/2026-10/` — o planejamento de cada mês (calendário, grade do feed, post a post e resultados).
- `assets/` — estilos e logos da página inicial.
- `_modelo/` — cópias prontas para começar um novo mês.
- `CLAUDE.md` — instruções detalhadas (identidade visual, estrutura das páginas, passo a passo). É o arquivo que o Claude lê para continuar o trabalho.

## Como atualizar ou criar um mês

**Com o Claude (recomendado):** abra esta pasta no Claude Code (ou no app do Claude, aba Code) e peça, por exemplo: *"Crie o planejamento de novembro da Bendito"* ou *"Atualize os resultados de outubro da Mané com estes números"*. Ele lê o `CLAUDE.md` e mantém o mesmo visual.

**Sem o Claude:** siga o passo a passo da seção "Como criar um novo mês" do `CLAUDE.md` e do `_modelo/LEIAME.md`.

## Como publicar

1. Salve as alterações no GitHub (no GitHub Desktop: escreva um resumo e clique em *Commit to main*, depois em *Push origin*).
2. A Vercel publica o site sozinha em cerca de 1 minuto.

## Contas envolvidas

- **GitHub** — repositório com todos os arquivos.
- **Vercel** — hospedagem; conectada ao GitHub, publica a cada alteração.
- **Google Drive** — os vídeos e artes ficam lá; o site só aponta para as pastas.
- **Google Fonts** — fontes carregadas pela internet (não precisa de conta).

> **Atenção:** o repositório e o projeto da Vercel foram criados na conta pessoal da Giovanna. Para o site não depender de uma pessoa, transfira ambos para a conta da empresa (ver "Contas e propriedade" no `CLAUDE.md`).

## Origem

Os planejamentos de outubro foram criados como páginas do Claude (artifacts) e migrados para cá. O conteúdo completo está neste repositório; nada depende dos links originais.

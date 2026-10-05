# Planejamento de Conteúdo · Marcas do Grupo Impettus

Site **100% estático** (HTML/CSS/JS puro) com os planejamentos mensais de conteúdo das marcas do Grupo Impettus. Sem backend, sem login, sem banco, sem build. Hospedado na Vercel com deploy automático a cada push na branch `main` do GitHub.

Idioma de tudo (conteúdo, textos de interface, commits): **português do Brasil**.

## Estrutura

```
/index.html                      home com 1 card por marca
/assets/css/site.css             estilo SÓ do portal (home, listas, "em construção")
/assets/logos/                   logos usados nos cards
/<marca>/index.html              lista de meses da marca (ou "em construção")
/<marca>/AAAA-MM/index.html      planejamento do mês (página autônoma)
/<marca>/AAAA-MM/...             imagens do mês (ver "Convenções de imagens")
/_modelo/                        modelos prontos para copiar (ver _modelo/LEIAME.md)
```

Pastas de marca: `bendito`, `mane`, `espetto-carioca`, `seu-rufino`, `sirene`.

Status atual: **Bendito** e **Mané** têm `2026-10` completo. **Espetto Carioca**, **Seu Rufino** e **Sirène** estão como "em construção".

## Regra de ouro do visual

Cada **página de mês é autônoma**: traz o próprio `<style>` e `<script>` dentro do `index.html` e só depende de fontes do Google Fonts e das imagens da sua pasta. O CSS do portal (`site.css`) **não** é usado nelas. Por isso, para um mês novo, **copie o HTML do mês anterior da mesma marca** e troque só o conteúdo. Não reescreva o layout nem "melhore" o CSS: o visual aprovado deve se manter idêntico entre meses.

Os links entre páginas usam caminhos absolutos (`/bendito/`, `/assets/...`) no portal e caminhos relativos para imagens dentro de cada mês.

## Identidade das marcas

**Momento Bendito** (`bendito`) — vinho/bordô e creme. Fontes: *Newsreader* (títulos, serifada) + *IBM Plex Sans* (corpo). Cores: bordô `#b3273c`, bordô escuro `#8c1f30`, creme `#fff6ec`, marrom `#3a2216`, marrom do logo `#6a2711`. Tom: acolhedor, "cafeteria para todas as horas". Emoji de café/coração com moderação nas legendas.

**Boteco Mané** (`mane`) — vermelho/vinho quente sobre creme, com hero escuro. Fontes: *Caveat Brush* (títulos, estilo pincel; substitui a Blowbrush do manual de marca) + *Montserrat* (corpo). Cores usadas: vermelho Mané `#DA0F15`, bordô `#640C00`, creme `#FFF6EC`, carmesim `#C32A3C`, tons de formato (Reels vermelho, Post bordô, Carrossel âmbar `#B9730F`, Stories verde-azulado `#1D6B73`). Do manual de marca (não usadas nesta versão, mas oficiais): Amarelo Chope `#fddf45`, Grená HNK `#0a4021`, Cimento Queimado `#3d3d3b`, Preto night `#1e1e1e`. Tom: boteco carioca, informal, irreverente — "Um Boteco F*#@". Os manuais de marca em PDF ficam fora do repositório (pasta local da Giovanna / SharePoint).

**Portal e demais marcas** (apenas cor de acento nos cards): Espetto Carioca `#e59500`, Seu Rufino `#1b3a6b`, Sirène azul-petróleo `#0e6e7e` (logo amarelo sobre fundo petróleo). O portal usa Newsreader + IBM Plex Sans e tema claro/escuro automático.

**Fundos fotográficos do portal:** a home e as páginas de cada marca (lista de meses / "em construção") têm foto de fundo com véu escuro. As fotos ficam em `assets/fundos/` (`home.webp`, `<marca>.jpg`) e são ligadas no `site.css` pelas classes `body.home` e `body.bg-<marca>` (a página da marca usa `class="b-<marca> brand-bg bg-<marca>"` no `<body>`). Para trocar uma foto, substitua o arquivo mantendo o nome. Isso **não** se aplica às páginas de mês, que têm visual próprio.

## Anatomia da página de mês

Todas têm 4 seções, nesta ordem (os links do menu apontam para esses IDs):

1. **Hero** — texto de direcional criativo do mês (estratégia, fases, editorias) + logo.
2. **Calendário** — grade semanal Seg–Dom. Dia com conteúdo mostra formato (Reels / Post / Carrossel / Stories), editoria e, se ainda não está pronto, a marca **Rascunho**. Datas comemorativas aparecem como **DC**. Dia sem post fica "blank" (tracejado).
3. **Grade do feed** — capas na ordem real de publicação, **sem Stories**. Itens sem arte ainda viram tile "Em criação". (Mané tem botão para inverter a ordem como no perfil.)
4. **Post a post** — um card por publicação: data/hora, formato, editoria, legenda completa, capa, link do material no **Google Drive**, galeria das telas do carrossel e miniatura + link dos stories do dia.
5. **Resultados do mês** — métricas de seguidores/alcance/engajamento e Top 3 Reels / Top 3 Posts. Enquanto o mês não fecha, os números ficam **zerados** com um aviso de "modelo aguardando dados reais"; depois, substituir pelos valores reais e **remover o aviso**.

Observações específicas:
- **Bendito**: tem abas de meses dentro da própria página (Outubro/Novembro/Dezembro), controladas por JS no fim do arquivo (`.month-tab` / `.month-panel`). Novembro e Dezembro são placeholders.
- **Mané**: abas parecidas (`.mtab` / `.mes`), mais um menu fixo (Calendário, Grade do feed, Post a post, Resultados do mês).
- No topo de cada página de mês existe uma barra escura injetada logo após `<body>` com os links "← Todas as marcas" e "Marca · todos os meses". Mantenha ao copiar.
- Todas as páginas têm `<meta name="robots" content="noindex">` (site de uso interno; não deve aparecer em buscas).

## Convenções de imagens

- **Bendito**: `covers/cover_DDMM.jpg` (capa; `_a` se houver duas no dia), `carrossel/car_DDMM_N.jpg` (telas), `stories/story_DDMM.jpg`, `hero_bg.jpg`, `logo.png`.
- **Mané**: tudo em `img/` — `tNN_K.jpg` (publicação NN, tela K; `_1` é a capa), `sNN.jpg` (stories da publicação NN), `hero.jpg`, `logo.jpg`.
- Imagens leves (JPG, ~30–230 KB). Carrosséis usam `loading="lazy"`.
- Os vídeos e artes originais **não** ficam no repositório: são links para pastas do Google Drive dentro de cada card.

## Como criar um novo mês (ex.: Novembro/2026 da Bendito)

1. Copie a pasta `bendito/2026-10/` para `bendito/2026-11/` e **apague as imagens antigas** (mantenha logo e hero se servirem).
2. Edite `bendito/2026-11/index.html`: hero (texto, mês), calendário, grade do feed, cards do post a post (legendas, horários, links do Drive) e resultados (zerados). Ajuste a aba ativa e o nome do mês nas abas internas.
3. Coloque as novas imagens seguindo as convenções acima e confira que todos os `src` existem.
4. Em `bendito/index.html`, adicione o item do mês na lista (copie o `<li>` de Outubro e troque mês/link).
5. Em `/index.html`, atualize "Último plano: ..." no card da marca.
6. Teste localmente (precisa de um servidor estático; abrir o arquivo direto com `file://` quebra os caminhos absolutos do portal) e publique.

Para uma marca "em construção" que ganha seu primeiro mês: troque `/<marca>/index.html` pela lista de meses (copie de `bendito/index.html`, ajuste cor de acento `b-<marca>` do `site.css` e logo) e crie a pasta do mês a partir do `_modelo/`.

## Publicar

- Push na `main` → a Vercel publica sozinha (~1 min). Projeto Vercel: *Framework Preset: Other*, sem build command, diretório de saída = raiz.
- No computador da Giovanna o `git` não está no PATH: usa-se o Git embutido do GitHub Desktop e o push é feito pelo próprio GitHub Desktop (credenciais ficam lá). Em outras máquinas, `git push` normal.
- Nunca commitar PDFs de manuais de marca, senhas, tokens ou dados pessoais de clientes.
- URL de produção: https://planejamento-marcas-do-grupo-impett.vercel.app/

## Contas e propriedade (pendente)

Repositório e projeto Vercel foram criados na conta pessoal da Giovanna (`giovannacamposrj-blt`). Recomendado transferir para a organização do GitHub e o time Vercel da empresa (GitHub: Settings → Transfer ownership; Vercel: reconectar o projeto ao novo repositório). Os planejamentos de outubro nasceram como artifacts do Claude na conta dela; já estão integralmente neste repositório, então os artifacts servem só de backup.

# Design system da ACK

Cada página carrega o próprio `<style>` inline no `<head>` (sem stylesheet compartilhado, mesmo
padrão do site pessoal). Página nova: copie o bloco de `index.html` e ajuste só o necessário.
Não invente cores, fontes ou espaçamentos.

Identidade visual separada do site pessoal de propósito: lá é navy + dourado com serifa
(Playfair); aqui é azul-marinho + verde-petróleo do logo, com sans geométrica. As duas não
devem se confundir.

## Logo

- Selo: quadrado arredondado verde `#0F6E56`, "ACK" em branco e três barras crescentes em
  menta `#9FE1CB` (alusão às colunas de um quadro Kanban). Funciona sozinho, sem o nome por extenso.
- Arquivo: `assets/logo-ack.svg` (recriado em vetor a partir da peça original, 64×64). Usado
  no cabeçalho (40px), no rodapé (22px) e como favicon.
- Imagem de compartilhamento: `assets/og-ack.png` (1200×630, logo completo com "Consultoria em TI").
- No site, o nome ao lado do selo é texto: **ACK** em `--ink` peso 700 + "Consultoria" em
  `--ink-soft`. Não redesenhe o selo, não mude as cores dele e não use o selo sobre fundo verde.

## Paleta (tokens em `:root`, com tema escuro)

| Token | Claro | Escuro | Uso |
|---|---|---|---|
| `--bg` | `#F2F5F7` | `#0A131D` | fundo da página |
| `--surface` | `#FFFFFF` | `#111F2E` | cartões e caixas |
| `--ink` | `#0D1B2A` | `#EAF0F5` | texto principal |
| `--ink-soft` | `#44546A` | `#9FB1C4` | texto secundário |
| `--line` | `#D5DDE5` | `#223245` | bordas e divisores |
| `--accent` | `#0F6E56` | `#9FE1CB` | botões e marcadores (verde do logo; no escuro, a menta das barras) |
| `--mint` | `#9FE1CB` | `#9FE1CB` | linha das etapas na faixa escura |
| `--accent-ink` | `#FFFFFF` | `#06201F` | texto sobre `--accent` |
| `--band` / `--band-ink` / `--band-soft` | `#0D1B2A` / `#EAF0F5` / `#9FB1C4` | `#050B12` / ... / `#8CA0B5` | faixa escura "Como trabalhamos" |

O tema escuro segue `prefers-color-scheme` do visitante. Cor nova só como token, definida nos
dois temas.

## Tipografia

- Google Fonts com `preconnect`: **Space Grotesk** (500/600/700) em títulos e marca, **Inter**
  (400/500/600) no texto.
- Escala: `h1` clamp(32px, 5vw, 52px); `h2` clamp(26px, 3.5vw, 34px); `h3` 18-19px; corpo 16px;
  apoio 14.5px; rótulos 12px em caixa alta com `letter-spacing: 1px`.
- Títulos com `text-wrap: balance`.

## Componentes

- **Marca** (`.brand`): selo `assets/logo-ack.svg` + "**ACK** Consultoria". Rodapé: `.foot-brand`.
- **Botão** (`.btn`): fundo `--accent`, texto `--accent-ink`, raio 4px. Variante `.btn-ghost`
  com borda `--line`.
- **Lista de serviços do hero** (`.svc-list`): borda superior de 2px em `--ink`, itens separados
  por `--line`.
- **Cartão** (`.card`): `--surface`, borda `--line`, raio 4px, tags (`.tags span`) com borda fina.
- **Etapas** (`.steps`): lista ordenada na faixa escura, linha superior em `--mint`, rótulo "Etapa N" gerado por CSS counter.
- **Caixa de contato** (`.box`): `dl` com rótulos em caixa alta, botões de contato abaixo.

## Layout

Coluna de 1080px (`.in`), gutter lateral `max(16px, env(safe-area-inset-*))`. Hero em duas
colunas que viram uma abaixo de 820px. Sem animações.

## SEO e `<head>` (obrigatório em toda página)

`<html lang="pt-BR">`, `<title>`, meta description, `meta robots`, `link rel="canonical"`, Open
Graph (`og:type`, `og:title`, `og:description`, `og:url`, `og:site_name`, `og:locale`), Twitter
card (`summary_large_image`), `og:image`, favicon e JSON-LD `ProfessionalService` (com `logo` e `image`) (sem `founder`/`author` com nome pessoal).

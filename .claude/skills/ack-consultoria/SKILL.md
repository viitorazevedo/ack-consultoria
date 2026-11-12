---
name: ack-consultoria
description: Fluxo completo de manutenção do site da ACK Consultoria LTDA (landing page institucional da empresa: gestão de projetos e produtos, desenvolvimento de sistemas, consultoria e marketing), HTML estático publicado no GitHub Pages com domínio próprio. Use esta skill sempre que o usuário pedir para escrever ou revisar textos do site, mexer em index.html, sitemap.xml, robots.txt, CNAME ou qualquer página do site, ajustar SEO, contato ou métricas, validar a página, ou fazer deploy/publicar mudanças. Dispare mesmo sem a palavra "skill", por exemplo "ajusta o texto do hero", "coloca o WhatsApp da ACK", "sobe essa mudança pro site", "cria uma página de serviço".
---

# Site da ACK Consultoria

Site 100% HTML/CSS/JS estático (sem framework, sem build step), hospedado no GitHub Pages
(branch `main`, root) no domínio da ACK (ver `CNAME`). **Qualquer push na `main` publica direto
em produção.** A validação visual acontece antes, em um artefato do Claude (ver seção 3).

Este projeto nasceu dos mesmos playbooks do site pessoal (`~/Documents/site_pessoal`), com uma
diferença central: **este site é da empresa, não da pessoa.** Leia antes de qualquer edição:

1. [references/content-rules.md](references/content-rules.md): regras de conteúdo e a lista de
   afirmações aprovadas. É o maior risco do projeto: citar o nome pessoal ou inventar um número.
2. [references/design-system.md](references/design-system.md): paleta, tipografia e componentes.
   Toda página nova copia o bloco `<style>` de `index.html` em vez de estilizar do zero.
3. [references/brief-lp-v1.md](references/brief-lp-v1.md): brief original aprovado da landing page.

## 1. Escrever ou revisar textos do site

Mesmo pipeline do site pessoal, adaptado para páginas e seções em vez de posts. Cada agente fica
em `.claude/agents/` e é invocado com o Agent tool (`subagent_type` = nome do agente). Eles
trocam o texto por `_drafts/<slug>.md` (formato em [references/draft-format.md](references/draft-format.md)).

1. **`writer`**: escreve o texto de uma seção ou página nova a partir do pedido do usuário.
2. **`editor`**: revisa gramática, clareza e tom. Confere as regras de `content-rules.md`.
3. **`seo-optimizer`**: ajusta `<title>`, meta description, headings e JSON-LD.
4. **`publisher`**: aplica o texto no HTML, atualiza `sitemap.xml`, roda o checklist de
   publicação (seção 4) e faz o commit local. **Não dá `git push` sozinho.**

Rode os três primeiros em sequência sem parar. Depois do `seo-optimizer`, mostre ao usuário o
texto final antes de acionar o `publisher`. Ajustes pequenos de texto que o usuário já ditou
(trocar uma palavra, preencher o e-mail) vão direto para a edição, sem pipeline.

## 2. Editar a landing page (`index.html`)

- Edite dentro das seções existentes (`.hero`, `#servicos`, `#metodo`, `#contato`, `footer`).
- Os serviços aparecem em dois lugares (lista do hero e cartões de `#servicos`). Mudou o nome de
  um serviço, mude nos dois.
- Os links da nav apontam para âncoras. Se surgir uma segunda página, a nav passa a ser duplicada
  em cada arquivo e precisa ser replicada manualmente, como no site pessoal.
- Todo link de contato leva `data-track="..."` para a medição (seção 5).

## 3. Validar antes de publicar (artefato do Claude)

Antes de qualquer push com mudança visual ou de mensagem, publique uma prévia como artefato do
Claude (Artifact tool, tipo "Design" para comparar variações lado a lado, ou página simples para
revisar a página inteira) e mande o link ao usuário. Só dê push depois da aprovação dele.
Canvas atual: https://claude.ai/artifact/CUeGMpZKbGdtiLVCYe7aV1

## 4. Deploy

O deploy é o próprio `git push` para `main`. Trate como publicação em produção: peça confirmação
explícita no chat, dizendo quais arquivos e o resumo das mudanças.

Checklist antes do push (o `publisher` roda e reporta):
- `grep -rn "PENDENTE\|DOMINIO-ACK" index.html sitemap.xml robots.txt` não retorna nada.
- Nenhuma ocorrência do nome pessoal do sócio no repositório público (ver `content-rules.md`).
  Inclui `.claude/`: o repositório do GitHub Pages é público, então os playbooks também ficam
  visíveis no GitHub (o site em si não serve pastas que começam com ponto).
- Autor dos commits: identidade da conta pessoal do GitHub (decisão do usuário em 2026-11-12),
  com o e-mail `noreply` do GitHub configurado só neste repositório, para não expor e-mail
  pessoal. O nome aparece no histórico do repositório, não no site.
- `<title>`, meta description, canonical, Open Graph e JSON-LD presentes e com o domínio certo.
- Links de e-mail e WhatsApp testados (abrem o app certo, com o destino certo).
- Página conferida em largura de celular e nos temas claro e escuro.

```bash
git add -A
git commit -m "mensagem descrevendo a mudança"
git push origin main
```

Depois do push, a mudança aparece em https://ackconsultoria.com em alguns minutos (HTTPS forçado).

Se o certificado HTTPS travar (domínio responde com certificado `*.github.io`), remova e
adicione de novo o domínio no Pages. Isso cria commits do próprio GitHub no `CNAME`: rode
`git pull --ff-only` antes do próximo commit local.

**Conta do GitHub:** o repositório é `viitorazevedo/ack-consultoria`, na conta pessoal do
usuário (decisão de 2026-11-12), como um projeto separado do site pessoal. Esta máquina também
tem uma conta corporativa logada no `gh`, e ela costuma ser a ativa. Nunca crie repo nem dê push
com ela. Para comandos `gh`, use o token da conta pessoal sem trocar a conta ativa:
`GH_TOKEN=$(gh auth token -u viitorazevedo) gh ...`. O `git push` usa a URL do remote com o
usuário (`https://viitorazevedo@github.com/...`), para o keychain escolher a credencial certa.

## 5. Métricas

Objetivo dos 3 primeiros meses: medir visitas e cliques nos botões de contato (taxa de
visitantes que pedem contato). Usar uma ferramenta sem cookies, para não exigir banner de
consentimento (LGPD). Os botões já têm `data-track` (`cta-hero`, `contato-email`,
`contato-whatsapp`). O snippet fica comentado no fim de `index.html` até a ferramenta ser escolhida.

## 6. Governança (PMO)

O agente `pmo` mantém `.claude/pmo/backlog.md` (pendências e ideias) e
`.claude/pmo/changelog.md` (publicações, testes, decisões). Acione-o quando o usuário perguntar
o que está pendente, registrar uma decisão, ou pedir uma checagem geral do site.

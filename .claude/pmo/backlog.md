# Backlog do site da ACK

Fonte única de verdade sobre o que falta para publicar e o que vem depois. Mantido pelo agente `pmo`.

Status: `Ideia` → `Em andamento` → `Bloqueado` → `Pronto` → `Publicado`.

Proposta de ordem e próximos passos do próximo ciclo: [`proximo-ciclo.md`](proximo-ciclo.md).

## Para publicar a v1

| Item | Status | Notas |
|---|---|---|
| Domínio da ACK | Pronto | `ackconsultoria.com` (registrado no WordPress.com). Aplicado em `index.html`, `sitemap.xml`, `robots.txt` e `CNAME` |
| E-mail de contato | Publicado | `contato@ackconsultoria.com` na LP e no JSON-LD desde 2026-11-12, redirecionando para `ackconsultoriati@gmail.com` |
| WhatsApp de contato | Pronto | (12) 99121-1582, link `wa.me/5512991211582` |
| Área de atendimento | Pronto | São José dos Campos, SP, e remoto para todo o mundo |
| CNPJ no rodapé | Pronto | 66.137.185/0001-99, também no JSON-LD (`taxID`) |
| Repositório no GitHub | Pronto | https://github.com/viitorazevedo/ack-consultoria, Pages ativo na `main` com domínio `ackconsultoria.com` |
| Identidade git dos commits | Pronto | Conta pessoal, com e-mail noreply do GitHub configurado só neste repositório |
| DNS do domínio apontando para o GitHub Pages | Publicado | 4 registros A do GitHub + `www` CNAME `viitorazevedo.github.io`, no WordPress.com. Propagado em 2026-11-12. Ignorar os avisos "Restore default" do WordPress |
| HTTPS (Enforce HTTPS) | Publicado | Certificado Let's Encrypt para `ackconsultoria.com` e `www`, válido até 2027-02-10 (renovação automática). HTTP e www redirecionam para https://ackconsultoria.com |
| Testar links de WhatsApp e e-mail no celular | Publicado | Testados pelo usuário no celular em 2026-11-12 |
| Logotipo | Publicado | `assets/logo-ack.svg` no cabeçalho, rodapé e favicon; `assets/og-ack.png` para compartilhamento |

## Depois de publicar

| Item | Status | Notas |
|---|---|---|
| **Escolher ferramenta de métricas** (visitas e cliques em contato) | Ideia — prioridade alta | Decisão importante, a fazer com calma. Critérios: sem cookies (dispensa banner LGPD), gratuita ou barata, conta eventos de clique. Botões já têm `data-track` (`cta-hero`, `contato-whatsapp`, `contato-email`) |
| Estratégia de backlinking com vitorbazevedo.com | Em andamento | Decisão do usuário (2026-11-12): link só do pessoal para a ACK. **Publicado** no vitorbazevedo.com: card em Atuação, item em Contato, rodapé de todas as páginas, author-box dos posts, `worksFor` no JSON-LD. Falta (com o usuário): página da ACK no LinkedIn, Search Console dos dois domínios. Ver `proximo-ciclo.md` |
| E-mail no domínio | Publicado | Redirecionamento gratuito do WordPress.com (`contato@` → Gmail), MX `smtp-fwd.wordpress.com`, testado pelo usuário. Respostas ainda saem do Gmail; caixa própria (paga) fica como opção futura |
| Versão em inglês | Ideia | Opcional. "Para todo o mundo" significa remote first, não exige versão em inglês |
| Página/rascunho de cases | Ideia | Só com casos e números aprovados pelo usuário |
| Nova aba de notícias do mercado financeiro (fintechs, FIDCs, fraudes) | Ideia | Sugerida pelo usuário em 2026-11-12. Primeira página além da LP: a nav passa a ser replicada em cada arquivo (SKILL, seção 2). A definir: frequência, formato (curadoria com resumo + link para a fonte, ou análise própria), e se reaproveita o pipeline writer → editor → seo-optimizer → publisher. Notícia sempre com fonte e data; resumo curto com link, sem copiar texto de terceiros. Existe a pasta `~/Documents/news_antifraud` (vazia hoje) que pode ser relacionada |

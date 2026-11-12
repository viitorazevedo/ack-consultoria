# Backlog do site da ACK

Fonte única de verdade sobre o que falta para publicar e o que vem depois. Mantido pelo agente `pmo`.

Status: `Ideia` → `Em andamento` → `Bloqueado` → `Pronto` → `Publicado`.

## Para publicar a v1

| Item | Status | Notas |
|---|---|---|
| Domínio da ACK | Pronto | `ackconsultoria.com` (registrado no WordPress.com). Aplicado em `index.html`, `sitemap.xml`, `robots.txt` e `CNAME` |
| E-mail de contato | Pronto | `ackconsultoriati@gmail.com`. Melhoria futura: endereço no domínio (ex.: contato@ackconsultoria.com) |
| WhatsApp de contato | Pronto | (12) 99121-1582, link `wa.me/5512991211582` |
| Área de atendimento | Pronto | São José dos Campos, SP, e remoto para todo o mundo |
| CNPJ no rodapé | Pronto | 66.137.185/0001-99, também no JSON-LD (`taxID`) |
| Repositório no GitHub | Pronto | https://github.com/viitorazevedo/ack-consultoria, Pages ativo na `main` com domínio `ackconsultoria.com` |
| Identidade git dos commits | Pronto | Conta pessoal, com e-mail noreply do GitHub configurado só neste repositório |
| DNS do domínio apontando para o GitHub Pages | Bloqueado | Com o usuário, no WordPress.com: trocar os A 192.0.78.24/25 pelos 4 IPs do GitHub e o `www` por CNAME `viitorazevedo.github.io` |
| HTTPS (Enforce HTTPS) | Bloqueado | Depende do DNS propagar e do certificado ser emitido |
| Teste dos 5 segundos (5 pessoas) | Ideia | Canvas: https://claude.ai/artifact/CUeGMpZKbGdtiLVCYe7aV1 (versões A e B do hero). Registrar resultado no changelog |
| Logotipo | Ideia | Opcional para a v1. Hoje a marca é tipográfica |

## Depois de publicar

| Item | Status | Notas |
|---|---|---|
| Métricas de visitas e cliques em contato | Ideia | Ferramenta sem cookies. Botões já têm `data-track` |
| E-mail no domínio | Ideia | Redirecionamento do WordPress.com ou caixa própria |
| Versão em inglês | Ideia | Opcional. "Para todo o mundo" significa remote first, não exige versão em inglês |
| Página/rascunho de cases | Ideia | Só com casos e números aprovados pelo usuário |

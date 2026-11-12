# Changelog do projeto (governança)

Eventos e decisões que não ficam óbvios pelo `git log`. Mantido pelo agente `pmo`; mais recente no topo.

---

## 2026-11-12 — Plano do próximo ciclo preparado

Novas ideias no backlog: aba de notícias (fintechs, FIDCs, fraudes) e backlinking com
vitorbazevedo.com. Proposta de ordem e próximos passos em `proximo-ciclo.md`, aguardando
priorização do usuário.

## 2026-11-12 — Botões de contato testados; teste dos 5 segundos removido

Usuário testou WhatsApp e e-mail no celular. Decidiu não fazer o teste dos 5 segundos (critério
do brief original deixa de valer). Escolha da ferramenta de métricas fica no backlog como
prioridade alta.

## 2026-11-12 — HTTPS ativo

O certificado não foi emitido sozinho em 1 hora. Resolvido removendo e adicionando o domínio no
Pages, o que gerou dois commits do GitHub no `CNAME` (Delete/Create). Enforce HTTPS ligado.

## 2026-11-12 — Logo publicado

Selo da ACK em SVG no cabeçalho, rodapé e favicon; imagem de compartilhamento 1200×630;
destaque da paleta alinhado ao verde do logo (`#0F6E56`) e à menta das barras (`#9FE1CB`).
Miniaturas para o LinkedIn geradas em `entregas/linkedin/` (fora do repositório).

## 2026-11-12 — DNS trocado: site no ar em ackconsultoria.com

DNS no WordPress.com apontado para o GitHub Pages. A LP responde em `http://ackconsultoria.com/`
e o `www` redireciona. `vitorbazevedo.com` conferido e sem impacto. HTTPS aguardando certificado.

## 2026-11-12 — Publicação da v1 no GitHub Pages

Repositório `viitorazevedo/ack-consultoria` criado (público), Pages ativo na `main` com domínio
`ackconsultoria.com`. O site só abre no domínio depois da troca de DNS no WordPress.com.

## 2026-11-12 — Decisão: repositório e commits na conta pessoal do GitHub

Repositório `viitorazevedo/ack-consultoria`, projeto separado do site pessoal. Commits com a
identidade pessoal (e-mail noreply do GitHub). O nome aparece só no histórico do repo, não no
site. "Remoto para todo o mundo" confirmado como posicionamento remote first.

## 2026-11-12 — Dados de contato e domínio confirmados

Domínio `ackconsultoria.com`, e-mail `ackconsultoriati@gmail.com`, WhatsApp (12) 99121-1582,
CNPJ 66.137.185/0001-99 no rodapé. Área de atendimento mudou de "remoto para todo o Brasil"
para "remoto para todo o mundo".

## 2026-11-12 — Projeto criado a partir dos playbooks do site pessoal

Estrutura `.claude/` (skill `ack-consultoria`, agentes writer/editor/seo-optimizer/publisher/pmo,
PMO) adaptada de `site_pessoal`. Diferenças: regras de conteúdo da empresa (sem nome pessoal, só
afirmações aprovadas), identidade visual própria (azul-marinho + verde-petróleo, Space Grotesk +
Inter) e etapa de validação em artefato do Claude antes do push.

## 2026-11-12 — Recomendação: hospedagem no GitHub Pages (aguarda confirmação do usuário)

Mesma stack do site pessoal (HTML estático, deploy por `git push`, HTTPS gratuito). O domínio
continua registrado no WordPress.com; só o DNS aponta para o GitHub Pages.

## 2026-11-12 — Revisão do rascunho da LP

Mantido o texto aprovado do brief. Acrescentados: `<head>` completo de SEO, JSON-LD, botões de
contato clicáveis com `data-track`, favicon, lista semântica no hero e rodapé com ano.

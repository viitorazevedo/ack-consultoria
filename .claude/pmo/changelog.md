# Changelog do projeto (governança)

Eventos e decisões que não ficam óbvios pelo `git log`. Mantido pelo agente `pmo`; mais recente no topo.

---

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

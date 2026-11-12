# Formato do rascunho (`_drafts/<slug>.md`)

Formato intermediário que os agentes usam para passar texto entre si. Não é publicado
(`_drafts/` está no `.gitignore`).

```markdown
---
slug: hero-v2                # nome curto, sem acento
target: index.html#hero      # arquivo e seção onde o texto entra
status: rascunho             # rascunho | revisado | seo | pronto
title_tag: ""                # só se a mudança afetar o <title> (preenchido pelo seo-optimizer)
meta_description: ""         # idem
claims_used: []              # afirmações da tabela de content-rules.md usadas no texto
---

## <bloco 1, ex: Título>
Texto.

## <bloco 2, ex: Subtítulo>
Texto.
```

Cada `##` corresponde a um elemento da página (título, subtítulo, botão, cartão). O `publisher`
aplica bloco por bloco no HTML.

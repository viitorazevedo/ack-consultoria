# Próximo ciclo de desenvolvimento: proposta para priorizar

Preparado pelo PMO em 2026-11-12. A ordem abaixo é uma **proposta**: a decisão de prioridade é
do usuário. Depois que ele decidir, atualizar os status em `backlog.md` e registrar no
`changelog.md`.

Critérios usados: impacto no objetivo dos 3 primeiros meses (separar PF de PJ, tom
profissional, networking e leads), esforço, e dependência entre itens.

## Visão geral

| # | Item | Impacto | Esforço | Depende de | Por que nesta posição |
|---|---|---|---|---|---|
| 1 | Ferramenta de métricas | Alto | Baixo | — | Sem medir, não dá para saber se os outros itens trazem visitas ou contatos. Já marcado como prioridade alta |
| 2 | Backlinking com vitorbazevedo.com + Google Search Console | Alto | Baixo | 1 (para medir o efeito) | Leva o público do perfil pessoal para a empresa e ajuda a ACK a ser indexada. Pouco trabalho |
| 3 | E-mail no domínio | Médio | Baixo | — | Tom profissional no contato. Pode correr em paralelo, é configuração |
| 4 | Aba de notícias (fintechs, FIDCs, fraudes) | Alto | Alto e recorrente | 1, 2 | Gera conteúdo para SEO e networking, mas exige rotina de publicação. Melhor com métricas e indexação prontas |
| 5 | Página de cases | Alto | Médio | Casos aprovados | Depende de ter casos e números que o usuário possa publicar |
| 6 | Versão em inglês | Baixo | Médio | — | Opcional. "Para todo o mundo" é posicionamento remote first, não exige inglês |

Sugestão de escopo para o ciclo: itens 1, 2 e 3 (baixo esforço, base para o resto) e a
**definição** do item 4 (formato e frequência), deixando a construção da aba para o ciclo seguinte.

## Próximos passos por item

### 1. Ferramenta de métricas

- [ ] Comparar opções sem cookies (dispensam banner LGPD), por exemplo GoatCounter, Cloudflare
      Web Analytics, Plausible e Umami: preço, se conta cliques em botões, onde os dados ficam.
- [ ] Usuário escolhe a ferramenta e cria a conta (criação de conta é dele).
- [ ] Colar o snippet no fim de `index.html` e ligar os eventos dos botões com `data-track`
      (`cta-hero`, `contato-whatsapp`, `contato-email`).
- [ ] Definir o indicador principal: **taxa de contato = cliques em WhatsApp ou e-mail ÷ visitas**.
- [ ] Combinar a frequência de leitura (ex.: mensal) e registrar a linha de base no changelog.

### 2. Backlinking com vitorbazevedo.com

Hoje o site pessoal não cita a ACK. A ideia é ligar os dois sites sem quebrar a regra de não ter
o nome pessoal no site da ACK.

**Decisão do usuário antes de começar:** o link vai só do pessoal para a ACK (recomendado, não
mexe na regra) ou também da ACK para o pessoal? A segunda opção põe o nome pessoal no site da ACK
e exige mudar `content-rules.md`.

Pessoal → ACK (feito com a skill `site-pessoal`, push com confirmação):
- [ ] Citar a ACK na seção de atuação (`#services`) ou na de contato (`#contact`) de
      `vitorbazevedo.com`, com link para `https://ackconsultoria.com`.
- [ ] Link para a ACK no rodapé do site pessoal (replicar em todas as páginas, a nav e o
      rodapé são duplicados por arquivo).
- [ ] Assinatura/bio no fim dos posts do blog pessoal mencionando a ACK.
- [ ] JSON-LD do site pessoal: `Person` com `worksFor` apontando para a organização ACK
      (`url: https://ackconsultoria.com`). Liga as duas entidades para o Google sem pôr nome no site da ACK.

Fora dos sites:
- [ ] Página da ACK no LinkedIn (empresa) e o projeto/experiência no perfil pessoal com link
      para `ackconsultoria.com` (miniaturas já em `entregas/linkedin/`).
- [ ] Cadastrar os dois domínios no Google Search Console e enviar o `sitemap.xml` da ACK.
- [ ] Opcional: perfil da ACK no Google (Perfil da Empresa) com o site, se fizer sentido para
      atendimento remoto.

Medir: visitas vindas de `vitorbazevedo.com` e do LinkedIn (depende do item 1).

### 3. E-mail no domínio

- [ ] Verificar no WordPress.com se há redirecionamento de e-mail gratuito para o domínio.
- [ ] Criar `contato@ackconsultoria.com` redirecionando para o Gmail atual.
- [ ] Trocar o e-mail na LP, no JSON-LD e nas regras de conteúdo; testar o envio.
- [ ] Opcional: configurar o Gmail para responder como `contato@` (exige SMTP ou caixa paga).

### 4. Aba de notícias (fintechs, FIDCs, fraudes)

Decisões do usuário antes de construir:
- [ ] Formato: curadoria (resumo curto + link para a fonte) ou análise própria da ACK.
- [ ] Frequência realista (ex.: 1 por semana) e quem revisa antes de publicar.
- [ ] Nome da aba e URL (ex.: `/noticias/`).

Construção (ciclo seguinte):
- [ ] Página de listagem + template de post, copiando o padrão do blog do site pessoal.
- [ ] Nav replicada em todas as páginas; `sitemap.xml` atualizado a cada notícia.
- [ ] Pipeline `writer → editor → seo-optimizer → publisher` adaptado para notícia: fonte e
      data obrigatórias, sem copiar texto de terceiros.
- [ ] Avaliar se a pasta `~/Documents/news_antifraud` (vazia hoje) vira o lugar da coleta.

### 5. Página de cases

- [ ] Usuário lista 2–3 casos que pode publicar (sem nome de cliente se houver confidencialidade).
- [ ] Para cada caso: contexto, o que foi feito, resultado (só números aprovados).
- [ ] Decidir se vira seção da LP ou página própria.

### 6. Versão em inglês

- [ ] Só reavaliar se aparecer demanda de contato de fora do Brasil (o item 1 mostra a origem
      das visitas).

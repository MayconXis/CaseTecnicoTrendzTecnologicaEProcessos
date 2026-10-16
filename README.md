# Hub Trendz

Protótipo navegável do MVP de um hub interno que liga marcas, creators e eventos numa base só e acompanha cada entrega da campanha até a comprovação. Feito para o case de Estágio em Produto & Tecnologia da The Trendz.

Acesse em https://mayconxis.github.io/CaseTecnicoTrendzTecnologicaEProcessos/

Protótipo conceitual para processo seletivo. Não é um produto da The Trendz. Todos os dados são fictícios.

## Por onde começar

1. Campanhas: a linha do tempo de cada entrega, a pré-checagem do roteiro feita pela IA e a visão da marca, que aprova por link, sem login.
2. Casting: escolha um evento, peça as sugestões e aprove ou descarte cada creator indicado.

## O que está pronto

| Módulo | Estado | O que mostra |
|---|---|---|
| Visão | Funcional | Nuvem de pontos com três cenas de evento e o resumo da proposta |
| Painel | Esqueleto | Leads, interesse por evento e propostas, com gráficos de dados fictícios |
| Eventos | Esqueleto | Ficha de evento em dois níveis, link próprio e filtros |
| Creators | Esqueleto | Cadastro único do creator e a base que o filtro do casting lê |
| Casting | Funcional | Sugestão de creators pela IA, com nota, justificativa e aprovação do time |
| Campanhas | Funcional | Linha do tempo das entregas, pré-checagem do roteiro e visão da marca |

## Como a IA funciona no protótipo

1. Um filtro em código reduz a base por região, nicho, formato e valor.
2. O LLM ranqueia só os perfis pré-filtrados, com nota e justificativa.
3. O código descarta qualquer id que não esteja na lista enviada.
4. O time aprova ou descarta cada indicação. Nada segue sem aprovação.

As sugestões do Casting são uma resposta gravada de uma chamada real ao Claude Sonnet 5.5, feita em 14/10/2026. O parecer da pré-checagem, em Campanhas, também é gravado. A opção de IA ao vivo só funciona dentro do claude.ai e aparece desativada neste endereço.

## Tecnologias

- Protótipo: um arquivo HTML com CSS e JavaScript, Three.js na nuvem de pontos, GSAP e Lenis, sem etapa de build.
- Produto real (proposta): a plataforma atual em React com Supabase, Claude API para os três usos de IA e Resend para os e-mails.

## Rodar localmente

```bash
git clone https://github.com/MayconXis/CaseTecnicoTrendzTecnologicaEProcessos.git
cd CaseTecnicoTrendzTecnologicaEProcessos && python3 -m http.server 8000
```

Depois abra http://localhost:8000 no navegador.

## Autor

Maycon Douglas da Silva · [LinkedIn](https://www.linkedin.com/in/maycon-douglas-da-silva-9a791a2aa/) · [GitHub](https://github.com/MayconXis)

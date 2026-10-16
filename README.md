# Hub Trendz

Protótipo navegável de um hub interno que liga marcas, creators e eventos numa base só e acompanha cada entrega da campanha até a comprovação. Feito para o case de Estágio em Produto & Tecnologia da The Trendz.

**Acesse:** https://mayconxis.github.io/CaseTecnicoTrendzTecnologicaEProcessos/

> Protótipo conceitual para processo seletivo. Não é um produto da The Trendz. Todos os dados são fictícios e nenhuma marca, creator ou evento real aparece aqui.

## A tese em uma frase

A Trendz já tem marcas, creators e eventos. O gargalo é o processo entre eles, e foi essa a dor que o time citou em 14/10/2026. Este hub organiza esse processo: um registro único, do interesse à entrega comprovada.

## Por onde começar (roteiro de 10 minutos)

Se você tem pouco tempo, siga esta ordem. Ela mostra o problema resolvido antes de mostrar as telas de apoio.

1. **Visão** (aba 00): a tela de abertura. Mostra a nuvem de pontos com a cena de um festival, com a marca e os creators numa mesma base. Use as setas ou a barra inferior para trocar de cena.
2. **Campanhas** (aba 05): o coração do MVP.
   - Em **Visão do time**, veja a linha do tempo de cada entrega: briefing enviado, roteiro enviado, pré-checagem pela IA, aprovação da marca, publicado e comprovação.
   - Abra a entrega EV-012. A pré-checagem compara o roteiro com o briefing e aponta o que precisa de ajuste. O time decide o próximo passo.
   - Clique em **Visão da marca · link sem login**. É a tela que a marca recebe por link. Ela aprova o roteiro ou pede ajuste, sem criar conta.
3. **Casting** (aba 04): escolha um evento e veja as sugestões. Cada creator indicado traz nota da IA e justificativa. Aprove ou descarte. Nada vai para a marca sem aprovação do time.
4. **Painel** (aba 01): interesses por semana, por dia e hora, eventos mais procurados e leads por segmento de marca. Os dados são fictícios.
5. **Eventos** e **Creators** (abas 02 e 03): esqueleto. Mostram a estrutura da ficha de evento e do cadastro de creator, sem a funcionalidade completa.

## O que está pronto

| Módulo | Estado | O que mostra |
|---|---|---|
| Visão | Funcional | Nuvem de pontos em três cenas (festival, corrida e feira), com o resumo do hub |
| Painel | Esqueleto | Quatro gráficos com dados fictícios: leads na semana, interesse por dia e hora, eventos por interesse e leads por segmento |
| Eventos | Esqueleto | Ficha de evento em dois níveis: a parte pública e a parte que só aparece na proposta |
| Creators | Esqueleto | Cadastro único do creator, que alimenta o filtro do Casting |
| Casting | Funcional | Filtro em código, sugestões da IA com nota e justificativa, aprovação ou descarte pelo time |
| Campanhas | Funcional | Linha do tempo das entregas, pré-checagem do roteiro e a visão da marca por link |

Nos módulos funcionais, as ações mudam a tela e seguem a lógica que o MVP teria. Nos esqueletos, os botões mostram a estrutura, mas não gravam nada.

## Como a IA funciona no protótipo

A IA entra em três pontos: sugerir creators para um evento, rascunhar o briefing de cada creator aprovado e pré-checar o roteiro contra o briefing. Em todos, o fluxo é o mesmo:

1. Um filtro em código reduz a base por região, nicho, formato e valor.
2. O modelo ranqueia só os perfis que passaram no filtro, com nota e justificativa.
3. O código descarta qualquer id que não esteja na lista enviada. A IA não inventa creator.
4. O time aprova, ajusta ou descarta. Nada segue sem essa etapa.

**Modo demonstração:** as sugestões do Casting e o parecer da pré-checagem são respostas gravadas de uma chamada real ao Claude Sonnet 5.5, feita em 14/10/2026 com dados fictícios. Assim o avaliador vê o resultado sem precisar de conta ou de créditos. A opção de IA ao vivo só funciona dentro do claude.ai. Neste endereço ela aparece desativada, com o aviso "IA ao vivo indisponível neste acesso".

## Acessibilidade e desempenho

- **Movimento reduzido:** se o sistema operacional pedir movimento reduzido, a nuvem de pontos fica parada e o aviso "movimento reduzido pelo sistema" aparece na tela.
- **Pausar movimento:** o botão no canto superior direito para e retoma a animação. A escolha fica salva no navegador.
- **Sem WebGL:** em navegadores ou celulares sem suporte, a cena aparece como imagem estática desenhada em canvas 2D, com os mesmos pontos.
- **Celular:** o layout se reorganiza em uma coluna, com a navegação em barra horizontal. Não há rolagem lateral da página.
- **Teclado:** os seis módulos podem ser acessados com Tab e Enter, com contorno de foco visível.

## Documentos do case

O deck (13 slides) e o documento de evidências (fontes, análises e registro do uso de IA) não estão neste repositório. Eles foram enviados por e-mail junto com a candidatura. Se precisar deles novamente, escreva para mayconcontacts@gmail.com.

## Tecnologias

- **Protótipo:** um arquivo HTML com CSS e JavaScript, Three.js para a nuvem de pontos, GSAP e Lenis para o movimento. Não há etapa de build.
- **Produto real (proposta):** a plataforma atual de eventos, em React com Supabase. Claude API para os três usos de IA, Resend para os e-mails, Tally para formulários e PostHog para métricas. Custo de ferramentas estimado em US$ 30 a 50 por mês na fase 1, sem salários.

## Rodar localmente

Requer Python 3 ou qualquer servidor estático.

```bash
git clone https://github.com/MayconXis/CaseTecnicoTrendzTecnologicaEProcessos.git
cd CaseTecnicoTrendzTecnologicaEProcessos
python3 -m http.server 8000
```

Abra http://localhost:8000 no navegador.

## Estrutura do repositório

```
index.html     o protótipo completo (um arquivo)
assets/        favicon e imagem de compartilhamento
README.md      este arquivo
.nojekyll      diz ao GitHub Pages para servir os arquivos sem processar
.gitignore     deixa de fora PDFs, material de apoio e arquivos do sistema
```

## Limites deste protótipo

- Os dados são fictícios e não vêm de nenhuma API.
- Não há login, banco de dados nem envio real de e-mail ou WhatsApp.
- Eventos e Creators são esqueleto. Histórico de campanhas, dashboard da marca e extração de mídia kit ficam para a fase 2 da proposta.
- Métricas de Instagram e TikTok dependem de acesso às APIs, previsto para a fase 3.

## Autor

Maycon Douglas da Silva · [LinkedIn](https://www.linkedin.com/in/maycon-douglas-da-silva-9a791a2aa/) · [GitHub](https://github.com/MayconXis)

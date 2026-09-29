# Inedit — instruções do projeto

Leia este arquivo no início de toda sessão.

## O que é
Inedit é um app de edição de vídeo por modelos para quem vende com vídeo e não tem editor (primeiro público: corretores de imóveis; depois lojistas e arquitetos). O usuário escolhe um modelo, envia os clipes gravados no celular e o app devolve o vídeo pronto: cortes, legendas, redução de ruído, estabilização, filtro de cor (LUT), logo e cartão final com WhatsApp.
Promessa: **Você grava. O Inedit edita.**

## Quem trabalha aqui
- A dona do projeto **não é programadora** e quer aprender enquanto constrói.
- Explique cada passo em português simples, antes de fazer. Diga o que é cada termo técnico na primeira vez que aparecer.
- Fale em português do Brasil. Frases curtas. Sem jargão desnecessário.
- Todo o código, nomes de arquivos e comentários curtos podem ficar em inglês; textos para o usuário final ficam em português.

## Regras que nunca se quebram
1. **Nunca peça nem aceite senhas ou chaves de API na conversa.** Chaves ficam só nas variáveis de ambiente da Vercel, da Railway e do Supabase. Localmente, num arquivo `.env.local`, que **nunca** vai para o GitHub (já está no `.gitignore`).
2. **Nunca coloque chaves no código.** Use `process.env.NOME_DA_VARIAVEL` e documente o nome em `.env.example`.
3. **Pagamento, login e armazenamento são feitos por serviços prontos** (Supabase, Asaas/Mercado Pago). Não guarde senhas nem dados de cartão.
4. **Se o prazo apertar, corte recurso, não a data.** O essencial é: enviar clipes, receber um vídeo bonito, pagar.
5. **Antes de mudar algo grande, explique o plano e espere o ok.** Pequenos ajustes podem ser feitos direto.
6. Commits pequenos, com mensagem clara em português. Trabalhe em branches quando a mudança for grande; a `main` deve sempre funcionar.

## Stack decidida
- App web: **Next.js (TypeScript)**, hospedado na **Vercel**. Funciona no celular e pode ser instalado na tela inicial (PWA).
- Login, banco e arquivos: **Supabase**.
- Motor de vídeo: **FFmpeg** num servidor **Railway** (sem GPU no começo).
- Legendas: transcrição por **Deepgram** ou **AssemblyAI** (o Claude não processa áudio).
- Inteligência: **API do Claude** (modelo `claude-opus-5-5`) para roteiro, revisão de legendas, texto do post e plano de edição em JSON.
- Pagamento: **Asaas** ou **Mercado Pago** (Pix e cartão recorrente).
- Métricas e erros: PostHog e Sentry (depois do lançamento).

## Plano (lançamento: quinta, 27 de novembro de 2026, Black Friday)
Plano completo: https://claude.ai/artifact/Vo7GKNTW2rNf5Sxq4cTHNn

| Semana | Datas | Tema |
| --- | --- | --- |
| 1 | 29 set a 4 out | Contas, projeto e instruções (**estamos aqui**) |
| 2 | 5 a 11 out | Página de vendas, pré-venda de Fundador, link de pagamento |
| 3 | 12 a 18 out | Login, banco de dados, upload de clipes |
| 4 | 19 a 25 out | Motor de vídeo, LUTs da AFIO |
| 5 | 26 out a 1 nov | Legendas, ruído, estabilização |
| 6 | 2 a 8 nov | Roteiro por IA, teleprompter, custo por vídeo |
| 7 | 9 a 15 nov | Assinatura Pro, termos, beta |
| 8 | 16 a 30 nov | Correções, aulas, lançamento |

**Como iniciar uma sessão de cada semana:** a dona diz "Vamos começar a semana N do plano do Inedit". Leia a tabela acima, confira o que ficou pendente da semana anterior e proponha os passos da semana.

## Escopo do MVP (novembro)
Entra: login; escolha de modelo (5 para imóveis, 2 para lojas); envio de clipes; edição automática (junta, corta, LUT, ruído, estabilização); legendas nas composições Manchete e Legenda fina; logo, cores e cartão final com WhatsApp; roteiro por IA e teleprompter; texto do post; plano grátis (3 vídeos com marca d'água) e Pro; Escola Inedit (aulas em vídeo).
Fica para depois: peças 3D, pedidos de animação por texto, todos os 12 filtros e 7 composições, biblioteca de músicas, plano Equipe, app nas lojas, comunidade de criadores.
Música no lançamento: o usuário adiciona a trilha no Instagram/TikTok na hora de postar (evita direito autoral).

## Marca e design
Tudo em `docs/marca/`: `marca.md` (voz e fundamentos), `tokens.json` (cores, tipografia, espaçamentos), `modelos-de-video.md` (filtros, composições de texto, peças 3D), e os logos em SVG.
Resumo: tema escuro primeiro (grafite `#111318`), uma cor de marca violeta (`#8C7CFF`), vermelho (`#FF5A4E`) **só** para gravação. Fontes gratuitas do Google Fonts: Sora (títulos), Manrope (interface), JetBrains Mono (dados). Nome escrito em texto corrido: **Inedit** (sem parênteses); o logo usa `(in)edit`.
Voz: frases curtas, verbo no imperativo, sem emoji, sem promessas que o app não cumpre.

## Regras do produto
- Vídeo com até 90 s no lançamento. Arquivos apagados após 30 dias.
- Só fontes gratuitas (OFL). Só filtros criados pela AFIO. Nada de nome de artista nos filtros.
- Formato de saída: 9:16, 1080×1920, 30 fps.
- Custo por vídeo (IA + servidor + transcrição): meta abaixo de R$ 1,50. Medir sempre.

## Estado atual
- [x] Repositório criado e ligado ao Claude
- [ ] Contas: Supabase, Vercel, Railway, Anthropic Console
- [ ] Projeto Next.js criado
- [ ] Conversa com o contador sobre faturar pelo CNPJ da AFIO

Atualize esta lista ao terminar cada tarefa.

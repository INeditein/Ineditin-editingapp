# Inedit

Inedit é um app de edição de vídeo por modelos para quem vende com vídeo e não tem editor: corretores, lojistas, arquitetos, prestadores de serviço e pequenos negócios. A pessoa escolhe um modelo, grava com o celular e o app aplica cor, legenda, estabilização, redução de ruído e sugestão de trilha.

Promessa: **Você grava. O Inedit edita.**

Personalidade: **confiável e ágil**. A estética vem da direção "Estúdio": uma ferramenta profissional e silenciosa, em que o vídeo é o protagonista.

## Voz

- Frases curtas, verbo no imperativo, uma instrução por vez: "Grave a sala. Agora a cozinha."
- Confirme o que foi feito: "Pronto. Legenda, cor e som aplicados."
- Prometa só o que o app entrega. Nada de "revolucione", "IA de ponta" ou "incrível".
- Sem emoji na interface. Pontos de exclamação só na tela de vídeo pronto.
- Fale a língua de quem vende: "imóvel", "produto", "cliente", nunca "asset", "render" ou "LUT".

## Fundamentos visuais

- **Escuro primeiro.** `surface` grafite é o fundo padrão, porque o vídeo aparece melhor sobre grafite. O tema claro existe para as telas de conta e de planos.
- **Uma cor de marca.** `violet` marca a ação principal (um botão por tela), o item selecionado e os parênteses do logo. Nunca pinta áreas grandes da interface.
- **Vermelho só para gravar.** `rec` aparece somente enquanto a câmera grava.
- **Conteúdo primeiro.** Miniaturas de modelo em grade de duas colunas, com `radius-md` e `space-2` entre elas. O texto fica sobre a miniatura só no rodapé dela.
- **Poucos elementos por tela.** Uma pergunta, poucas escolhas e um botão principal com `radius-lg` na base da tela.
- **Bordas, não sombras.** Separação por `line` e por diferença entre `surface`, `surface-raised` e `panel`.

## Tipografia

Sora (`display`) nos títulos, no logo e nas legendas dos vídeos. Manrope (`sans`) em toda a interface. JetBrains Mono (`mono`) só para duração, formato e timecode (`00:45 · 9:16`). As três fontes vêm do Google Fonts.

## Logo

- **Wordmark:** `(in)edit` em Sora 700 minúscula, com espaçamento -0.04em. Os parênteses ficam em `violet` e mais leves (Sora 600), e o restante em `ink`. O nome escrito em texto corrido é sempre **Inedit**, sem parênteses.
- **Símbolo:** `(i)`, dois parênteses e um "i", em `assets/Logos`. Serve de ícone do app, avatar das redes e marca d'água do plano gratuito.
- **Área de respiro:** a altura do "i" em volta do símbolo. Tamanho mínimo: 20px (símbolo) e 72px de largura (wordmark).
- **Pendente:** converter o wordmark em curvas (SVG) com a Sora final e fazer o ajuste fino de kerning com o designer.

## Movimento

- **Abertura do app (600ms):** o "i" aparece, e os dois parênteses se fecham em volta dele, vindos de fora, com ease-out. Um corte seco para a tela inicial.
- **Transições de interface:** 200 a 250ms, ease-out, sem quicar.
- Respeite a opção do sistema de reduzir movimento: sem animação, só troca direta.

## Iconografia

Ícones de linha com traço de 2px, pontas arredondadas e grade de 24px, na cor `ink` ou `ink-muted`. O ícone ativo usa `violet`. A família recomendada é Lucide, por ser aberta e consistente com o traço do símbolo. Sem ícones preenchidos, sem emoji.

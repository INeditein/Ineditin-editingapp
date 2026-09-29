# Estética dos modelos de vídeo

Os vídeos exportados não carregam a marca Inedit (exceto a marca d'água do plano gratuito). Eles carregam o **kit de marca do usuário**: logo, duas cores e contato. O Inedit define o padrão de qualidade; a identidade é do cliente.

## Regras comuns a todos os modelos

- **Formato:** 9:16, 1080×1920, 30 fps. Opção 1:1 e 16:9 no plano pago.
- **Legendas:** Sora 700, caixa alta e baixa, até 2 linhas e no máximo 32 caracteres por linha, com margem segura de 12% em cima e embaixo. Palavra falada em destaque na cor principal do usuário.
- **Cor:** correção automática de balanço de branco e exposição, depois o filtro do pacote.
- **Áudio:** voz com redução de ruído e normalização a -14 LUFS. Trilha 18 dB abaixo da voz, subindo quando ninguém fala.
- **Encerramento:** cartão final de 2s com logo, nome e contato do usuário.

## Pacotes de lançamento

| Pacote | Modelo | Duração | Ritmo | Filtro |
| --- | --- | --- | --- | --- |
| Imóveis | Tour do imóvel | 45s | cortes a cada 2 a 3s, movimento suave | Natural claro |
| Imóveis | Destaque rápido | 15s | cortes a cada 1s, texto grande | Contraste |
| Loja | Produto novo | 15s | close, giro, preço na tela | Vivo |
| Projetos | Antes e depois | 30s | tela dividida e revelação | Natural quente |
| Serviços | Depoimento | 30s | plano único e legendas destacadas | Natural |

Filtros com estética analógica (grão, carimbo de data) podem virar um pacote extra, sem mudar a marca do app.

## Pacote Cinema

Opções que o usuário pode trocar dentro de cada modelo. O modelo sempre define uma combinação padrão, então o usuário nunca começa do zero. **Só fontes gratuitas (Google Fonts, licença OFL).** Fontes enviadas pelo usuário no plano Pro ficam sob responsabilidade dele.

### Composições de texto

| Nome no app | Fontes | Uso |
| --- | --- | --- |
| Manchete | Bodoni Moda (destaque em caixa alta) + Montserrat Light | Chamadas de imóvel, estilo AFIO |
| Legenda fina | Montserrat Light, minúsculas, +0.08em | Legendas de fala |
| Editorial | Italiana + Lato Light | Arquitetura, decoração, moda |
| Impacto | Oswald + Lato | Ofertas e números |
| Clássica | Playfair Display itálico + Montserrat | Alto padrão, gastronomia |
| Estreia | Cinzel + Montserrat Light | Aberturas de lançamento |
| Trailer | Bebas Neue + Lato | Em breve, contagem regressiva |

### Filtros da AFIO (LUT .cube + camadas)

Calibrados em frames reais da AFIO. Toda exportação passa antes pelo **Realce de qualidade** (nitidez, redução de ruído, correção de luz).

| Nome | Look | Camadas |
| --- | --- | --- |
| Natural | só correção | nenhuma |
| Nogueira | interiores em madeira, pele natural, contraste macio | halation leve, vinheta leve |
| Hora Dourada | fim de tarde com névoa | halation forte, vinheta |
| Petróleo | sombras frias, pele quente, externas | grão fino, vinheta |
| Creme | pretos lavados, tons de creme | nenhuma |
| Âmbar | quente e profundo | halation leve |
| Ciano | frio e limpo | vinheta leve |
| Laranja e Verde | verde nas sombras, pele laranja | grão fino |
| Laranja e Azul | sombras azuis, luzes laranja | vinheta |
| Marrom Retrô | anos 70, dessaturado | grão visível, vinheta |
| Mood Vintage | desbotado, sombras verde-água | grão de filme, vinheta forte |
| Tropical | saturado, flash de película | grão, halation |

### Animações 3D sob pedido

O usuário descreve em texto. O Claude escolhe uma peça da biblioteca e devolve um plano em JSON (peça, ângulos, duração, filtro, composição e textos), que o motor de vídeo (Remotion ou Three.js) renderiza no servidor. No MVP a IA não cria animações do zero; ela combina e ajusta as peças abaixo.

| Peça | O que faz |
| --- | --- |
| `celular_3d` | tela de celular girando com o vídeo, fundo desfocado |
| `texto_no_chao` | título deitado no chão avançando para o fundo |
| `texto_na_parede` | título em perspectiva na parede, acompanhando a câmera |
| `cartao_3d` | cartão de vidro com preço e ficha, em camadas |
| `transicao_cubo` | cena gira e revela o cartão de contato |
| `letras_em_profundidade` | letras chegam do fundo, uma a uma |

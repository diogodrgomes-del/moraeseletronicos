# Moraes Celulares & Eletrônicos — link na bio

Página única, em HTML/CSS/JS puro, que **cabe inteira na tela do celular sem
rolagem**. Sem build, sem dependências, sem requisição externa: a foto da loja e
a logo vão embutidas no próprio arquivo.

```
index.html                 → a página inteira
assets/logo.png            → logo original, como enviada (1254×1254, com transparência)
assets/logo-recortada.png  → a mesma logo, recortada na caixa do conteúdo (1054×751)
assets/loja.webp           → foto da loja (941×1672)
```

Os arquivos de `assets/` são as fontes. O `index.html` já carrega tudo embutido
em base64, então funciona sozinho — dá para abrir com dois cliques ou mandar por
WhatsApp.

## O que falta para publicar

Preencher o bloco `const MORAES` no fim do `index.html`:

| Campo | O que é |
|---|---|
| `whatsappIphone` | WhatsApp da venda de iPhone — só dígitos: `55` + DDD + número |
| `whatsappAndroid` | WhatsApp da venda de Android — mesmo formato |
| `instagramUrl` | Link completo do Instagram, começando com `https://` |
| `googleMapsUrl` | Link completo do Google Maps da loja |

Enquanto estiverem vazios, os botões abrem um aviso em vez de mandar o cliente
para um destino errado. É proposital.

## Como o "cabe em uma tela" funciona

Toda medida vertical é `dvh` (altura real da tela, já descontando a barra do
navegador) e toda fonte é `min(vw, dvh)` — vale o que for menor. Assim o layout
encolhe junto com a tela em vez de transbordar.

Testado em 7 tamanhos, do iPhone SE ao 15 Pro Max, incluindo os dois piores
casos: com a barra do navegador do Instagram comendo altura (390×700 e 375×560).
Zero rolagem em todos, com 9 a 14px de folga dentro de cada cartão.

## As fotos dos cartões

Não há imagem separada por cartão: é a **mesma foto da loja**, recortada em
cinco pedaços diferentes por `background-position`. Um arquivo só serve à
abertura e aos quatro cartões.

Para trocar um recorte, mexa nas classes `.c-iphone`, `.c-android`,
`.c-instagram` e `.c-endereco`.

## Publicar

Arquivo estático: sobe direto em Netlify, Vercel ou GitHub Pages, sem build.

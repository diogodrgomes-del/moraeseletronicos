# Moraes Celulares & Eletrônicos — link na bio

Página única para a bio do Instagram: logo, frase de impacto e quatro
atalhos. Preto, branco e ouro. Sem build, sem dependência — um HTML e uma
imagem.

```
index.html       → a página inteira (estilo e script dentro)
assets/logo.png       → o logo, recortado e otimizado (64 KB)
assets/logo-original.png → o original enviado, intocado
assets/icone.png      → ícone da aba e do atalho de celular
assets/LEIA-ME.md     → o que é cada arquivo e como regerar
```

## Os quatro atalhos

| # | Botão | Vai para |
|---|---|---|
| 1 | Procurando um iPhone? — CLIQUE AQUI | WhatsApp, com mensagem já digitada |
| 2 | Prefere Android? — CLIQUE AQUI | WhatsApp, com mensagem já digitada |
| 3 | Veja nosso Instagram | `instagram.com/<usuário>` |
| 4 | Venha nos visitar | Google Maps |

Os dois primeiros são os de venda, então carregam o ouro. Os outros dois
ficam em preto e branco para não disputar atenção.

## O que editar

Tudo que muda de verdade está no bloco `const MORAES`, no fim do
`index.html`:

| Campo | O que é |
|---|---|
| `whatsappIphone` | WhatsApp da venda de iPhone — só dígitos: `55` + DDD + número |
| `whatsappAndroid` | WhatsApp da venda de Android — mesmo formato |
| `msgIphone` / `msgAndroid` | Mensagem que já vem escrita para o cliente |
| `instagram` | Usuário do Instagram, sem o `@` |
| `cidade` | Texto de apoio do botão da loja |
| `mapsUrl` | Link do Google Maps da loja |

O `@usuário` e a cidade que aparecem nos botões saem desse mesmo bloco —
não é preciso editar o HTML em dois lugares.

## Tipografia e cor

- **Sora** nos títulos e rótulos, **Manrope** no resto (Google Fonts, com
  fallback de sistema declarado).
- Ouro `#F6C210` — o valor exato do logo —, com `#FFE27A` no brilho e `#9A7A06` na sombra.
- Pretos levemente quentes (`#0B0A09`, `#17150F`) para não brigar com o ouro.
- O ouro aparece em poucos lugares de propósito: a palavra *iPhone*, os
  losangos entre os selos, os dois botões de venda e a régua do rodapé.

## Animação

Entrada em cascata: cada bloco sobe 14 px e aparece, com ~70 ms entre um e
outro. Termina em cerca de 1,1 s — a página assenta sozinha, sem rolagem e
sem nada preso em `opacity: 0`.

O brilho dourado atrás do logo respira num ciclo de 9 s, e os botões de
venda têm um clarão que atravessa no toque.

Tudo isso desliga em `prefers-reduced-motion: reduce`.

## Publicar

Arquivo estático: sobe direto em Netlify, Vercel ou GitHub Pages, sem build.

## Pendências

- [ ] Trocar os dois WhatsApp de exemplo (`5543000000000`) pelos números reais
- [ ] Confirmar o usuário do Instagram
- [ ] Trocar o `mapsUrl` pelo link exato da loja (hoje é uma busca por nome)

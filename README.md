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
| `instagram` | Usuário do Instagram da loja, sem o `@` |
| `instagramAgencia` | Usuário do Instagram da agência, usado na assinatura do rodapé |
| `cidade` | Texto de apoio do botão da loja |
| `mapsUrl` | Link do Google Maps da loja |

O `@usuário` e a cidade que aparecem nos botões saem desse mesmo bloco —
não é preciso editar o HTML em dois lugares.

## Tipografia e cor

- **Sora** nos títulos e rótulos, **Manrope** no resto e **Playfair Display**
  itálico só em "iPhone em Londrina" (Google Fonts, com fallback de sistema
  declarado).
- Ouro `#F6C210` — o valor exato do logo —, com `#FFE27A` no brilho e `#9A7A06` na sombra.
- Pretos levemente quentes (`#0B0A09`, `#17150F`) para não brigar com o ouro.
- O ouro aparece em poucos lugares de propósito: "iPhone em Londrina", os
  quatro ícones, os losangos entre os selos, os dois botões de venda e a
  régua do rodapé.

## Animação

Entrada em cascata: cada bloco sobe 14 px e aparece, com ~70 ms entre um e
outro. Termina em cerca de 1,1 s — a página assenta sozinha, sem rolagem e
sem nada preso em `opacity: 0`.

Depois disso a página não fica parada:

| O quê | Como |
|---|---|
| "iPhone em Londrina" | degradê de sete paradas, duas vezes e meia mais largo que o texto, deslizando em 6 s — é o que faz o brilho correr pelas letras |
| Logo | flutua 6 px num ciclo de 6,5 s, começando depois da entrada |
| Pílulas CLIQUE AQUI | um clarão atravessa cada uma a cada 5 s, defasadas em 2,5 s |
| Losangos dos selos | cintilam em 3,6 s, o segundo defasado em 1,8 s |
| Setas dos dois últimos botões | acenam 4 px a cada 4,2 s, defasadas |
| Brilho atrás do logo | respira num ciclo de 9 s |

Tudo isso desliga em `prefers-reduced-motion: reduce`.

## Os três selos em uma linha

`aparelhos originais · até 18x no cartão · novos e seminovos` não quebra em
nenhuma tela: a linha é `nowrap` e o corpo da fonte acompanha a largura do
aparelho, em `clamp(6.2px, 2.05vw, 11px)`. Medido de 320 a 440 px — em
todas sobra pelo menos 7% de folga.

Mexer no texto dos selos exige refazer essa conta.

## Publicar

Arquivo estático, sem build. No GitHub Pages: Settings → Pages → Source
`Deploy from a branch` → branch `claude/festive-newton-50kxif`, pasta
`/ (root)`. Sai em `diogodrgomes-del.github.io/moraeseletronicos/`.

A branch padrão do repositório é outra e tem outra versão da página, com
os WhatsApp vazios — não aponte o Pages para ela.

Todos os caminhos do `index.html` são relativos, então a página funciona
tanto na raiz de um domínio quanto numa subpasta.

## Conferido

- [x] Logo oficial em `assets/logo.png`
- [x] WhatsApp `5543996774144` nos dois botões, com as mensagens do cliente
- [x] Instagram da loja: `moraeseletronicos`
- [x] Instagram da agência: `agenciamarktiva`
- [x] Link do Maps apontando para o ponto da loja

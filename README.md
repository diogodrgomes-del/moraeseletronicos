# Moraes Celulares & Eletrônicos — link na bio

A arte da marca **é** a página. Nada é redesenhado: a imagem aparece inteira na
tela e, por cima dela, ficam quatro áreas clicáveis invisíveis alinhadas com os
botões que já existem no desenho.

```
index.html         → a página
assets/arte.jpg    → a arte (você coloca aqui)
assets/LEIA-ME.md  → nomes e proporção aceitos
```

## O que falta para funcionar

Só uma coisa: colocar a arte em `assets/arte.jpg`. Enquanto o arquivo não
existir, a página mostra um aviso com o passo a passo em vez de ficar preta.

## Como editar os contatos

Tudo no bloco `const MORAES` no fim do `index.html`:

| Campo | O que é |
|---|---|
| `whatsappIphone` | WhatsApp da venda de iPhone — só dígitos: `55` + DDD + número |
| `whatsappAndroid` | WhatsApp da venda de Android — mesmo formato |
| `msgIphone` / `msgAndroid` | Mensagem que já vem digitada para o cliente |
| `instagram` | Usuário do Instagram, sem o `@` |
| `mapsUrl` | Link do Google Maps da loja |

## Como as áreas clicáveis funcionam

Cada botão é um `<a>` posicionado em **porcentagem** da arte:

```css
.t-iphone { left: 17.6%; top: 39.7%; width: 65.3%; height: 9.6%; }
```

Como tudo é percentual, a arte pode encolher ou crescer que as áreas acompanham
— ficam alinhadas em qualquer tela. As medidas valem para uma arte **941 × 1672**
(9:16). Trocando a arte por outra de proporção diferente, é preciso ajustar o
`aspect-ratio` da classe `.arte` e essas porcentagens.

Em repouso as áreas são invisíveis, para não alterar a arte. Elas só acendem de
leve no toque, e ganham contorno dourado no foco por teclado.

## Acessibilidade e busca

Como todo o conteúdo está dentro de uma imagem, cada área clicável tem
`aria-label` e a imagem tem `alt` descritivo — senão leitor de tela e Google não
enxergariam nada da página.

## Publicar

Arquivo estático: sobe direto em Netlify, Vercel ou GitHub Pages, sem build.

## Pendências

- [ ] Colocar a arte em `assets/arte.jpg`
- [ ] Trocar os dois WhatsApp de exemplo pelos números reais
- [ ] Confirmar usuário do Instagram e link do Maps
- [ ] Conferir se a arte final tem mesmo 941 × 1672; se não, ajustar as %

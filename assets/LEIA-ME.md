# Fotos da página

A página procura estes arquivos. Enquanto não existirem, ela mostra um aparelho
desenhado em CSS no lugar — nada quebra, nada aparece vazio. Assim que o arquivo
for colocado aqui, a foto entra sozinha, sem mexer no código.

| Arquivo | Onde aparece | Formato ideal |
|---|---|---|
| `hero.jpg` | Cartão de abertura, acima de "iPhone" | deitada, 16:10, mín. 1200×750 |
| `produto-1.jpg` | Vitrine "Na loja", 1ª caixa | quadrada, mín. 600×600 |
| `produto-2.jpg` | Vitrine "Na loja", 2ª caixa | quadrada, mín. 600×600 |
| `produto-3.jpg` | Vitrine "Na loja", 3ª caixa | quadrada, mín. 600×600 |

Pode usar `.jpg`, `.png` ou `.webp` — se trocar a extensão, ajuste o `src`
da `<img>` correspondente no `index.html`.

As legendas da vitrine ("iPhone Pro", "iPhone", "Xiaomi") ficam nas tags
`<figcaption>` do `index.html`.

Dica: fundo claro e neutro funciona melhor, porque a caixa tem cantos
arredondados e a legenda entra por cima do rodapé da imagem.

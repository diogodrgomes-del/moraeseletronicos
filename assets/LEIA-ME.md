# Os arquivos da marca

| Arquivo | Para que serve |
|---|---|
| `logo-original.png` | O original enviado, 1254 × 1254, intocado. É a fonte de tudo. |
| `logo.png` | O que a página carrega: mesmo desenho, sem a margem transparente e reduzido para 660 × 477. |
| `icone.png` | Ícone da aba e do atalho de celular, 192 × 192, quadrado. |

## Por que não usar o original direto

O original tem 479 KB e uma margem transparente larga em volta do
desenho — em `object-fit` isso vira espaço morto no topo da página, e em
rede móvel é meio megabyte só para mostrar a marca.

O `logo.png` é o mesmo arquivo recortado no limite do desenho e reduzido
para 2× o tamanho em que aparece na tela. Como a marca é feita de três
cores chapadas (`#F6C210` no ouro, `#868585` no cinza e branco na linha
de baixo), encaixar cada pixel na cor mais próxima devolve o PNG ao que
ele deveria ser: **64 KB**, sem perda visível.

## Se o logo mudar

Substitua o `logo-original.png` e gere os outros dois a partir dele.
O `index.html` aponta para `assets/logo.png` e `assets/icone.png` — os
nomes não mudam.

Atenção ao fundo: o logo é **transparente** e a linha "CELULARES &
ELETRÔNICOS" é branca. Ela só aparece sobre fundo escuro, que é o caso
da página.

# A arte

A página usa a arte inteira como imagem, sem redesenhar nada. Por cima dela
ficam quatro áreas clicáveis invisíveis, alinhadas com os botões.

## O arquivo

Coloque a arte aqui com um destes nomes:

- `arte.jpg`  (procurado primeiro)
- `arte.png`
- `arte.webp`

Enquanto o arquivo não existir, a página mostra um aviso com o passo a passo,
em vez de ficar preta.

## Proporção

As áreas clicáveis foram medidas sobre uma arte de **941 × 1672** (proporção
9:16). Se a sua arte tiver outra proporção, ajuste no `index.html`:

1. O `aspect-ratio` da classe `.arte`
2. As porcentagens das classes `.t-iphone`, `.t-android`, `.t-endereco` e
   `.t-instagram`

Cada área é definida por `left`, `top`, `width` e `height` em porcentagem da
arte — por isso continuam alinhadas em qualquer tamanho de tela.

## Peso

Exporte em JPG com qualidade 80 e no máximo 1200px de largura. Acima disso o
ganho visual no celular é nulo e a página só demora mais para abrir.

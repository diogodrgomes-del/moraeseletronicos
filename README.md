# Moraes Celulares & Eletrônicos — link na bio

Mini landing page (link na bio) da Moraes Celulares & Eletrônicos.
HTML/CSS/JS puro, arquivo único, sem build e sem dependências.

## Estrutura

```
index.html         → a página inteira (estilos, ícones SVG e configuração)
assets/            → as fotos de produto (ver abaixo)
assets/LEIA-ME.md  → quais arquivos a página procura
```

## Como editar

Tudo que muda no dia a dia está no bloco `const MORAES = { ... }`, no final do
`index.html`:

| Campo | O que é |
|---|---|
| `whatsappIphone` | WhatsApp da venda de iPhone — só dígitos: `55` + DDD + número |
| `whatsappAndroid` | WhatsApp da venda de Android — mesmo formato |
| `msgIphone` / `msgAndroid` | Mensagem que já vem digitada para o cliente |
| `instagram` | Usuário do Instagram, sem o `@` |
| `mapsUrl` | Link do Google Maps da loja |
| `endereco` / `horario` | Textos do rodapé |

As cores ficam nos tokens `:root` no topo do `<style>` (`--gold`, `--ground`,
`--surface`, etc.). Mudou o token, mudou a página inteira.

## Como ver no navegador

Abrir o `index.html` direto no navegador já funciona. Para servir localmente:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Publicar

Por ser um arquivo estático, sobe direto em Netlify, Vercel, GitHub Pages ou
qualquer hospedagem. Não há passo de build.

## As fotos

A página tem quatro espaços de foto, todos ligados à pasta `assets/`:

| Arquivo | Onde aparece | Formato |
|---|---|---|
| `hero.jpg` | Cartão de abertura | deitada 16:10, mín. 1200×750 |
| `produto-1.jpg` | Vitrine, 1ª caixa | quadrada, mín. 600×600 |
| `produto-2.jpg` | Vitrine, 2ª caixa | quadrada, mín. 600×600 |
| `produto-3.jpg` | Vitrine, 3ª caixa | quadrada, mín. 600×600 |

**Enquanto o arquivo não existir**, a página mostra um aparelho desenhado em CSS
no lugar — nunca fica um buraco nem um ícone de imagem quebrada. Basta soltar os
arquivos na pasta que as fotos entram sozinhas, sem tocar no código.

Quem faz isso é o bloco `fotos()` no final do `index.html`: se o `<img>` falha,
a `<figure>` ganha a classe `sem-foto` e o desenho aparece.

## Como o visual está montado

- **Vidro fosco** — `backdrop-filter` sobre a luz de fundo, nos cartões e chips
- **Contorno em degradê** — classe `.stroked`, feita com `mask-composite` em vez
  de borda falsa, então o degradê corre pela borda sem pintar o miolo
- **Grão** — ruído em SVG embutido sobre o fundo, a 4%, para o degradê não ficar
  com aquele aspecto chapado
- **Tipos** — Archivo variável (o eixo `wdth` deixa o "iPhone" mais largo) e
  Plus Jakarta Sans no texto corrido

## Enxugado para a primeira tela

Marca, chamada, produto, as quatro garantias e os dois botões de WhatsApp cabem
em ~650px. Endereço, Instagram, vitrine, marcas e rodapé vêm logo abaixo.
O controle central do espaçamento é o `gap` do `.wrap`.

## Pendências

- [ ] Trocar os WhatsApps de exemplo pelos números reais
- [ ] Confirmar usuário do Instagram e link do Maps
- [ ] Substituir o monograma SVG pelo arquivo oficial da marca
- [ ] Colocar as fotos reais em `assets/` (hero + 3 produtos)
- [ ] Endereço e horário reais da loja em Londrina
- [ ] Favicon e imagem de compartilhamento (Open Graph)

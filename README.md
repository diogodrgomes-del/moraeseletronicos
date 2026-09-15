# Moraes Celulares & Eletrônicos — link na bio

Mini landing page (link na bio) da Moraes Celulares & Eletrônicos.
HTML/CSS/JS puro, arquivo único, sem build e sem dependências.

## Estrutura

```
index.html   → a página inteira (estilos, ícones SVG e configuração)
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

## Os aparelhos da abertura

Os três iPhones são desenhados em CSS — nenhuma imagem é carregada, então a
página abre sem esperar download. Ficam no bloco `3. Os aparelhos` do `<style>`:

- `.dev--azul`, `.dev--laranja`, `.dev--titanio` — as três cores
- `.cam` — o módulo da câmera; os `<i>` são as lentes e os `<b>` o flash e o sensor
- `.maca` — o símbolo da Apple

Para trocar uma cor, basta mudar o `background` da classe. Para usar foto real
de produto, trocar a `<div class="trio">` por `<img>` e manter a mesma altura.

## Enxugado para a primeira tela

A ordem foi pensada para o cliente ver tudo que importa sem rolar: marca,
"Referência em iPhone em Londrina", os aparelhos, as quatro garantias e os dois
botões de WhatsApp cabem em ~740px. Endereço, Instagram, marcas e rodapé vêm
logo abaixo.

Se for mexer no espaçamento, o controle central é o `gap` do `.wrap`.

## Pendências

- [ ] Trocar os WhatsApps de exemplo pelos números reais
- [ ] Confirmar usuário do Instagram e link do Maps
- [ ] Substituir o monograma SVG pelo arquivo oficial da marca
- [ ] Avaliar trocar os iPhones em CSS por foto real de produto
- [ ] Endereço e horário reais da loja em Londrina
- [ ] Favicon e imagem de compartilhamento (Open Graph)

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

## Pendências

- [ ] Trocar os WhatsApps de exemplo pelos números reais
- [ ] Confirmar usuário do Instagram e link do Maps
- [ ] Substituir o monograma SVG pelo arquivo oficial da marca
- [ ] Endereço e horário reais no rodapé
- [ ] Favicon e imagem de compartilhamento (Open Graph)

# Plano de Mudança do Gibo

Slides interativos em HTML puro (sem build) para decidir cidade, vizinhança, tipo de moradia, cômodos e planta do próximo imóvel alugado.

## Rodar localmente

```bash
python -m http.server 8765
```

Abra http://localhost:8765. Abrir o `index.html` direto pelo arquivo também funciona na maioria dos navegadores.

## Publicar no GitHub Pages

1. Suba `index.html` e a pasta `src/` para a raiz do repositório.
2. Em **Settings → Pages**, escolha *Deploy from a branch*, branch `main`, pasta `/ (root)`.

Site publicado: https://exceededits.github.io/plano-de-mudanca-do-gibo/

## Navegação

- Setas ← → do teclado, botões da barra inferior ou swipe no celular.
- `#N` na URL abre direto o slide N (ex.: `index.html#11`).
- As respostas ficam salvas no navegador de quem responde (localStorage).

## Imagens

- `images.js`: diz qual foto aparece em cada espaço do quiz (cidade, vizinhança, moradia e os 16 cômodos), com nome, descrição e crédito. Para trocar uma foto, edite esse arquivo.
- `src/`: fotos locais (cômodos de inspiração, rua arborizada e república).
- Fotos externas (Wikimedia Commons e rawpixel, licenças abertas) são carregadas por link. Os créditos aparecem no slide final. Se alguma sair do ar, aparece um bloco com o nome da opção.
- Painel de manutenção: https://claude.ai/artifact/C9PbRsWsZzAaLX2LjPfNRM (privado). Nele você marca a foto de cada espaço, adiciona links novos e copia o `images.js` gerado. O código do painel está em `painel/painel.html`.

## Mapa

O slide de cidade usa Leaflet com tiles do OpenStreetMap (sem chave de API). Os pontos são coordenadas aproximadas dos centros dos bairros e municípios.

# Scoutvaardig

De voorpagina van [scoutvaardig.nl](https://scoutvaardig.nl): apps om scoutingtechnieken te leren.

- **Water:** [Lelievlet 3D](https://github.com/wiebren/lelievlet), op `scoutvaardig.nl/lelievlet/`.
- **Land:** [Scoutingtechnieken](https://github.com/wiebren/scoutingtechnieken), op `scoutvaardig.nl/scoutingtechnieken/`
  (binnenkort).

Eén statische pagina (`index.html`), zonder bouwstap. Elke push naar `main` publiceert hem met GitHub Pages
(`.github/workflows/pages.yml`). Dit is de *user site* van GitHub (`wiebren.github.io`): het eigen domein ervan geldt
ook voor de Pages-sites van de apps, die elk hun eigen repository houden. Zo staan ze vanzelf onder
`scoutvaardig.nl/lelievlet/` en `scoutvaardig.nl/scoutingtechnieken/`, en sturen de oude adressen op
`wiebren.github.io` door.

## Het domein

`scoutvaardig.nl` staat onder *Settings → Pages* van deze repository (met *Enforce HTTPS*); met een workflow als
bron is een bestand `CNAME` niet nodig. De DNS: A-records `185.199.108.153` t/m `185.199.111.153`, AAAA-records
`2606:50c0:8000::153` t/m `2606:50c0:8003::153`, en `www` als CNAME naar `wiebren.github.io`. Haal je het domein hier
weg, dan staan ook de apps weer op `wiebren.github.io`.

## Beelden

- `img/lelievlet.png`: het icoon van Lelievlet 3D (uit `wiebren/lelievlet`, `web/demo/icons/icon-512.png`, verkleind).
- `img/scoutingtechnieken.svg`: het merk van Scoutingtechnieken, gemaakt met `web/src/merk.js` uit
  `wiebren/scoutingtechnieken`.
- `img/scoutvaardig.svg`: het favicon, water en land naast elkaar.

## Licentie

© 2026 Wiebren Braakman, onder [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.nl), net als
de apps.

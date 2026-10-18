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

## Het domein aanzetten

Pas als de DNS van scoutvaardig.nl naar GitHub wijst, anders werken ook de apps niet meer:

1. DNS: A-records `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`; AAAA-records
   `2606:50c0:8000::153` t/m `2606:50c0:8003::153`; `www` als CNAME naar `wiebren.github.io`.
2. Het domein verifiëren onder *Settings → Pages* van het account (TXT-record `_github-pages-challenge-wiebren`).
3. Een bestand `CNAME` met `scoutvaardig.nl` toevoegen en pushen, of het domein zetten onder *Settings → Pages* van
   deze repository; daarna *Enforce HTTPS*.

Lokaal bekijken: `python3 -m http.server` in deze map, en dan <http://localhost:8000/>.

## Beelden

- `img/lelievlet.png`: het icoon van Lelievlet 3D (uit `wiebren/lelievlet`, `web/demo/icons/icon-512.png`, verkleind).
- `img/scoutingtechnieken.svg`: het merk van Scoutingtechnieken, gemaakt met `web/src/merk.js` uit
  `wiebren/scoutingtechnieken`.
- `img/scoutvaardig.svg`: het favicon, water en land naast elkaar.

## Licentie

© 2026 Wiebren Braakman, onder [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.nl), net als
de apps. Geen apps van Scouting Nederland: een eigen project, gemaakt voor scouts en leiding.

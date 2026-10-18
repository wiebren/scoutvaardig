# Scoutvaardig

De voorpagina van [scoutvaardig.nl](https://scoutvaardig.nl): apps om scoutingtechnieken te leren.

- **Water:** [Lelievlet 3D](https://github.com/wiebren/lelievlet), op `scoutvaardig.nl/lelievlet/`.
- **Land:** [Scoutingtechnieken](https://github.com/wiebren/scoutingtechnieken), op `scoutvaardig.nl/scoutingtechnieken/`
  (binnenkort).

De voorpagina is één statische pagina (`index.html`), zonder bouwstap. GitHub Pages publiceert hem samen met een
kopie van beide apps (`.github/workflows/pages.yml`): elke app wordt gebouwd uit zijn eigen repository, net als daar,
en komt in `lelievlet/` en `scoutingtechnieken/`.

## Twee adressen

Lelievlet 3D publiceert zichzelf ook nog vanuit zijn eigen repository, op `wiebren.github.io/lelievlet/`: daar stond
hij tot oktober 2026. Een app die vanaf dat adres is geïnstalleerd, krijgt daar zijn updates en verhuist dan
(`web/demo/verhuizen.js`): een browsertab gaat meteen naar dezelfde pagina hier, een geïnstalleerde app vraagt het
eerst. Wat de app op het apparaat bewaart, gaat mee achter de `#`. Een eigen domein voor de *user site*
(`wiebren.github.io`) zou ook gelden voor de apps, en dan stuurt GitHub het oude adres door; daar kan een service
worker niet langs, en de geïnstalleerde apps zouden geen update meer krijgen. Daarom heeft het domein een eigen
repository, en heet deze niet `wiebren.github.io`.

Scoutingtechnieken was net uit en had geen installaties van het oude adres: op `wiebren.github.io/scoutingtechnieken/`
staat alleen een pagina die naar hetzelfde adres hier doorstuurt (`.github/doorsturen.html` in die repository).

Als de oude installaties van Lelievlet 3D verhuisd zijn, kan zijn oude adres ook zo doorsturen.

## Bijwerken

Van elke app staat hier de commit die de Pages-workflow van de app als laatste met succes heeft gedraaid (bij
Lelievlet 3D dezelfde versie als op het oude adres). `versies.json` op de site zegt welke dat zijn. Elke 15 minuten kijkt de workflow of een app iets
nieuws heeft gepubliceerd, en bouwt dan opnieuw; met de hand kan het ook (*Actions → Pages → Run workflow*).

Sneller, zonder te wachten: laat de app na zijn eigen publicatie een `repository_dispatch` (`app-gepubliceerd`) naar
deze repository sturen. Daar is een token voor nodig (*fine-grained*, alleen deze repository, *Contents: write*), als
geheim in de repository van de app.

GitHub zet een geplande workflow uit als er 60 dagen niets in de repository is gebeurd; je krijgt daar vooraf een
mail over. Zet hem dan weer aan onder *Actions → Pages*, of push iets.

## Het domein

`scoutvaardig.nl` staat onder *Settings → Pages* van deze repository (met *Enforce HTTPS*); met een workflow als
bron is een bestand `CNAME` niet nodig. De DNS: A-records `185.199.108.153` t/m `185.199.111.153`, AAAA-records
`2606:50c0:8000::153` t/m `2606:50c0:8003::153`, en `www` als CNAME naar `wiebren.github.io`.

## Beelden

- `img/lelievlet.png`: het icoon van Lelievlet 3D (uit `wiebren/lelievlet`, `web/demo/icons/icon-512.png`, verkleind).
- `img/scoutingtechnieken.svg`: het merk van Scoutingtechnieken, gemaakt met `web/src/merk.js` uit
  `wiebren/scoutingtechnieken`.
- `img/scoutvaardig.svg`: het favicon, water en land naast elkaar.

## Licentie

© 2026 Wiebren Braakman, onder [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.nl), net als
de apps.

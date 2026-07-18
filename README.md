# Ratapulssi

Ratapulssi on kevyt verkkosivu Suomen junaliikenteen seurantaan. Sivun karttanäkymä hakee Digitrafficin avoimesta rajapinnasta junien viimeisimmät GPS-sijainnit ja esittää ne Suomen rataverkon havainnollistavalla kartalla.

## Ominaisuudet

- Interaktiivinen, OpenStreetMap-pohjainen koko Suomen kartta: zoomaus, panorointi ja karttamerkintöjen tiedot
- Reaaliaikainen junien GPS-sijaintien haku 15 sekunnin välein sekä pehmeä liikeanimaatio päivitysten välillä
- Paikannuspainike, joka näyttää käyttäjän sijainnin ja paikannustarkkuuden kartalla käyttäjän luvalla
- Aktiivisten junien määrä ja laskettu keskinopeus
- Suomen rataverkon karttanäkymä ja tärkeimpien kaupunkien merkinnät
- Helsingin seuraavien lähtöjen esimerkkikooste
- Responsiivinen käyttöliittymä puhelimille ja työpöydille
- Selkeä käyttökatkotila silloin, kun reaaliaikainen rajapinta ei vastaa

## Teknologia

Sivu on toteutettu ilman rakennusvaihetta tai ulkoisia JavaScript-riippuvuuksia:

- HTML, CSS ja tavallinen JavaScript yhdessä `index.html`-tiedostossa
- Leaflet-karttakirjasto ja OpenStreetMap-karttalaatat
- Google Fonts: DM Sans, DM Mono ja Space Grotesk
- Digitraffic Rail API: `https://rata.digitraffic.fi/api/v1/train-locations.geojson/latest`

## Käyttö paikallisesti

Koska toteutus on staattinen, sivun voi avata suoraan selaimessa:

1. Avaa `index.html`.
2. Hyväksy tarvittaessa selaimen verkkoyhteys, jotta reaaliaikaiset GPS-sijainnit voidaan hakea.

## Julkaiseminen GitHub Pagesissa

Repositorio sisältää GitHub Actions -työnkulun tiedostossa `.github/workflows/deploy-pages.yml`.

Työnkulku:

1. käynnistyy aina, kun `master`-haaraan pushataan muutos;
2. pakkaa staattisen sivuston;
3. julkaisee sen GitHub Pagesiin.

GitHubissa tulee valita kerran **Settings → Pages → Build and deployment → Source → GitHub Actions**. Julkaistu sivu on osoitteessa:

`https://paanpe.github.io/codex_ratapulssi/`

## Data ja käyttöehdot

Reaaliaikainen data tulee [Digitrafficin rautatieliikenteen avoimesta rajapinnasta](https://www.digitraffic.fi/rautatieliikenne/), jonka käyttöehdot ovat Creative Commons Nimeä 4.0. Rajapinnan tiedoissa voi olla viiveitä tai puutteita, joten sivua ei tule käyttää turvallisuuskriittisiin tarkoituksiin.

## Projektirakenne

```text
.
├── index.html                         # Sovellus ja käyttöliittymä
├── README.md                          # Projektin dokumentaatio
└── .github/workflows/deploy-pages.yml # GitHub Pages -julkaisu
```

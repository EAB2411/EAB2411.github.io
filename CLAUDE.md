# Berg Boligfoto – bergboligfoto.no

Portefølje- og markedsføringsside for Berg Boligfoto (ENK), eiendomsfoto og dronefoto i Levanger og omegn. Eier: Even Berg.

## Hosting og publisering
- Hostes på GitHub Pages fra `main`. Alt som havner på `main` er live etter 1–2 minutter.
- Domenet `bergboligfoto.no` er kjøpt hos Webhuset.no og pekes hit via `CNAME`-filen. Ikke endre eller slett `CNAME`.

## Regler for endringer
- **Aldri push direkte til `main`.** Lag en egen gren og åpne en pull request. Even godkjenner og merger selv.
- Én pull request per tema, med en kort forklaring på norsk av hva som er endret og hvorfor.
- Even tester hver endring før neste. Hold endringene små og avgrensede.
- Ikke installer eller last ned pakker/biblioteker uten å si hva det er og få Evens godkjenning først.
- Ikke legg inn plassholdertekst (som «[Navn]») eller oppdiktet innhold på siden.
- Aldri bruk stockbilder eller andres bilder som om de var Evens arbeid.

## Struktur
- `index.html` – hele siden: HTML, CSS (i `<style>`) og JavaScript (i `<script>`) i én fil.
- `images/` – alle bilder. `og-bilde.jpg` er forhåndsvisningen ved deling på sosiale medier.
- `favicon.svg` – ikonet i nettleserfanen.
- Seksjoner (i rekkefølge): hero, `#om-meg`, `#tjenester`, `#portfolio`, `#kontakt`. Scrolling styres av JavaScript (seksjonene snapper), ikke vanlig sidescroll.
- Porteføljen bygges fra `categories`-lista i `<script>`. Tre kategorier som alltid skal vises: `boligfoto`, `navnlos` (Navnløs Media, hvit bakgrunn) og `selective`. Tom kategori viser «Prosjekter kommer snart».
- Prosjekter med `link` åpner en ekstern side (f.eks. Instagram eller Navnløs Media) i ny fane. Prosjekter uten `link` åpner bildene i lightbox.

## Bilder
- Format: WebP, kvalitet ca. 80. Maks 2000 px på lengste side for vanlige bilder, 1500 px holder for porteføljen.
- Fjern alltid all EXIF-data, særlig GPS fra dronebilder (kunders adresser skal ikke kunne leses ut av bildene).
- Filnavn: små bokstaver, bindestrek, ingen æøå eller mellomrom, f.eks. `boligfoto-levanger-stue-1.webp`.
- Alle bilder skal ha en kort, beskrivende `alt`-tekst på norsk.
- Originaler og RAW-filer skal ikke inn i repoet.

## Stil
- Farger: svart `#080808`, off-white `#f0ede8`, gull/aksent `#cbb48f`, grå `#bbb`.
- Fonter: Cormorant Garamond (overskrifter), Montserrat (brødtekst).
- Språk på siden: norsk bokmål.

## Kontakt og firmainfo
- Kontakt skjer foreløpig via Instagram: https://www.instagram.com/evenaberg/ (knappen i `#kontakt`).
- Det finnes ingen jobb-e-post ennå. En e-postknapp ligger kommentert ut i `#kontakt`, klar til bruk.
- Org.nr. 931 783 173 står i bunnteksten. Adresse skal **ikke** vises på siden.
- Navnløs Media: Instagram https://www.instagram.com/navnlosmedia/ og nettside https://navnlos.no/#portfolio

## Kvalitetssjekk før pull request
- Kjør en syntakssjekk av JavaScript-en og åpne siden i en nettleser (desktop og mobilbredde) for å se at intro, seksjoner, portefølje og lightbox fungerer.
- Sjekk at alle bildereferanser peker på filer som finnes.

## Sikkerhet
- `index.html` har en Content-Security-Policy (meta-tag i `<head>`). Siden får bare laste fra seg selv og Google Fonts. Legges det til en ny ekstern kilde (video, kart, skript), må CSP-en oppdateres, ellers blokkeres den.
- Ikke legg inn eksterne skript, sporing eller tredjeparts-widgets uten at Even har godkjent det.
- Bygg innhold med DOM-metoder (`textContent`, `createElement`), ikke `innerHTML` med data.
- Eksterne lenker: kun `https://`, og alltid `rel="noopener noreferrer"` / `noopener,noreferrer`.
- Aldri legg passord, API-nøkler eller andre hemmeligheter i repoet. Repoet er offentlig.

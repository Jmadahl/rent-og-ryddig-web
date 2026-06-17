# Rent og Ryddig AS — nettside

Statisk bedriftsside for Rent og Ryddig AS. Leveres ferdig hostet på Cloudflare Pages, med et valgfritt admin-panel i nettleseren for eieren.

## Innhold

```
rent-og-ryddig/
├── index.html        Selve nettsiden
├── styles.css        Design og layout
├── images/           Bilder som brukes på siden
│   ├── hero.jpg
│   ├── about.jpg
│   ├── service-husvask.jpg
│   └── service-bedrift.jpg
├── admin/            Valgfritt admin-panel (Decap CMS)
├── README.md         Denne filen
├── DEPLOY.md         Hvordan publisere siden
└── INNHOLD.md        Hvordan endre tekster og bilder
```

## Hva du kan gjøre lokalt

Forhåndsvis siden uten å laste opp noe:

```bash
cd ~/projects/rent-og-ryddig
python3 -m http.server 8000
```

Åpne så `http://localhost:8000` i nettleseren. Stopp serveren med Ctrl+C.

## Steg for å publisere

Se `DEPLOY.md` for full fremgangsmåte. Kortversjonen:

1. Opprett et nytt repository på GitHub
2. Last opp mappen dit
3. Koble Cloudflare Pages til repoet
4. Siden er live på `rent-og-ryddig.pages.dev`

## Hvordan endre innhold

Se `INNHOLD.md`. De viktigste tingene:

- Telefonnummer: rediger `index.html`, søk etter `+47 000 00 000`
- E-post: samme fil, søk etter `post@rentogryddig.no`
- Tjenester: samme fil, seksjonen `<!-- TJENESTER -->`
- Bilder: bytt filer i `images/`

## Vedlikehold

Siden er bygget for å være ferdig og glemt. Den trenger ingen oppdateringer, ingen plugins, ingen database. For å endre noe, rediger filene og last opp på nytt.

Hvis noe går galt: hele siden er 4 filer. Ta backup av hele mappen, og du har alt.

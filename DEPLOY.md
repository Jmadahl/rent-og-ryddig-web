# Slik publiserer du siden

Denne guiden tar deg fra ferdig lokalt prosjekt til en live nettside som alle kan besøke. Helt til slutt kobler vi til domenet deres.

## Oversikt

1. Opprett et GitHub-repository
2. Last opp prosjektet dit
3. Koble Cloudflare Pages til repoet
4. Siden er live på `rent-og-ryddig.pages.dev`
5. (Senere) Koble til domenet deres

Hele prosessen tar omtrent 10-15 minutter, og alt er gratis.

## 1. Opprett GitHub-repository

1. Logg inn på github.com
2. Klikk `+` øverst til høyre → `New repository`
3. Navn: `rent-og-ryddig-web`
4. Velg `Public` (gratis hosting krever public repo)
5. IKKE kryss av for "Add a README file" — vi har allerede en
6. Klikk `Create repository`

## 2. Last opp prosjektet

GitHub viser deg en URL etter at repoet er opprettet. Den ser ut som:
`https://github.com<DITT-BRUKERNAVN>/rent-og-ryddig-web.git`

Kjør disse kommandoene i terminalen:

```bash
cd ~/projects/rent-og-ryddig
git init
git add .
git commit -m "Første versjon av nettsiden"
git branch -M main
git remote add origin https://github.com<DITT-BRUKERNAVN>/rent-og-ryddig-web.git
git push -u origin main
```

Hvis Git spør om brukernavn og passord: bruk GitHub-brukernavnet ditt, og et "Personal Access Token" som passord (ikke det vanlige passordet ditt). Du lager et token på github.com → Settings → Developer settings → Personal access tokens.

## 3. Koble til Cloudflare Pages

1. Gå til dash.cloudflare.com og logg inn (eller opprett konto — gratis)
2. I menyen til venstre: `Workers & Pages` → `Create application` → `Pages` → `Connect to Git`
3. Velg GitHub → velg `rent-og-ryddig-web` repoet
4. I "Build settings":
   - Framework preset: `None`
   - Build command: la stå tom
   - Build output directory: `/` eller la stå tom
5. Klikk `Save and Deploy`

Etter 1-2 minutter er siden live på:
`https://rent-og-ryddig-web.pages.dev`

(Du kan endre prosjektnavnet i Cloudflare hvis du vil ha en annen URL.)

## 4. Hver gang du endrer noe

```bash
cd ~/projects/rent-og-ryddig
# gjør endringene dine
git add .
git commit -m "Beskriv hva som er endret"
git push
```

Cloudflare oppdager endringen automatisk og publiserer ny versjon innen 1-2 minutter. Du trenger ikke gjøre noe mer.

## 5. Domenet (kommer senere)

Når domenet deres er klart:

1. I Cloudflare: `Workers & Pages` → klikk på prosjektet → `Custom domains` → `Set up a custom domain`
2. Skriv inn domenet deres
3. Cloudflare gir deg to DNS-innstillinger (en CNAME og evt. en A-record)
4. Logg inn der domenet er registrert, og legg inn disse
5. Vent 5-30 minutter — siden er nå på domenet deres, med HTTPS automatisk

Hvis domenet er registrert et annet sted enn Cloudflare, er det bare noen få klikk i kontrollpanelet deres.

## Hvis noe går galt

- Siden viser en feilmelding: sjekk at du trykket "Save and Deploy" etter opplasting
- Tom side: sjekk at `index.html` ligger i rot-mappa, ikke i en undermappe
- Gamle bilder vises: hard-refresh i nettleseren (Cmd+Shift+R på Mac)
- Noe annet: spør meg, så fikser vi det

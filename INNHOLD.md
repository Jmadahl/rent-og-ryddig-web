# Slik endrer du innhold

Alle endringer gjøres i `index.html` for tekster og kontaktinfo, og i `images/` for bilder. Åpne filene i hvilken som helst teksteditor (VS Code, Atom, TextEdit, eller GitHub i nettleseren).

## Telefonnummer

Åpne `index.html` og søk (Cmd+F) etter `+47 000 00 000`. Bytt ut med det ekte nummeret.

Det finnes to steder det står:
- I kontakt-seksjonen (det som vises på siden)
- I `tel:`-lenken (brukes på mobil når noen trykker på nummeret)

Eksempel:
```html
<p><a href="tel:+4747123456">+47 47 12 34 56</a></p>
```

## E-postadresse

Søk etter `post@rentogryddig.no` og bytt ut. Samme format overalt:
- Vanlig tekst på siden
- `mailto:`-lenken (når noen trykker på adressen)

## Facebook-URL

Søk etter `facebook.com/people/Rent-og-Ryddig-As` og bytt ut hvis den endrer seg.

## Tjenester

Hver tjeneste er en `<article class="service-card">` i seksjonen `<!-- TJENESTER -->`.

For å legge til en ny tjeneste: kopier en eksisterende `<article>`-blokk og endre innholdet.

For å fjerne tjenester: bare slett hele `<article>`-blokken.

For å endre rekkefølge: flytt blokkene opp eller ned.

## Legge til Instagram, LinkedIn, Google Business osv.

Finn kontakt-seksjonen i `index.html` (søk etter `<!-- KONTAKT -->`). Kopier en eksisterende `<div class="contact-item">` og endre lenken:

```html
<div class="contact-item">
    <h3>Instagram</h3>
    <p><a href="https://instagram.com/dinside" target="_blank" rel="noopener">Følg oss på Instagram</a></p>
    <p class="muted>Bilder fra jobber og oppdateringer</p>
</div>
```

## Bilder

Bilder ligger i `images/`. For å bytte et bilde:

1. Lagre det nye bildet i `images/` med samme filnavn som det gamle
2. Last opp endringen (se README for git-kommandoer)

Tips for bilder:
- Bruk ekte bilder fra jobber — det bygger tillit
- Optimaliser bilder før opplasting (liten fil = rask side)
- Anbefalt størrelse: ca 1200-1600 px bredde for hovedbilder

## Logo

Nå bruker vi en enkel tekst-logo med "R&R"-merke. For å bytte til en ekte logo:

1. Last opp logobildet til `images/logo.png`
2. Åpne `index.html` og finn `<a href="#" class="logo">`
3. Bytt ut innholdet med:
```html
<a href="#" class="logo">
    <img src="images/logo.png" alt="Rent og Ryddig AS" style="height: 40px;">
</a>
```

## Etter alle endringer

```bash
cd ~/projects/rent-og-ryddig
git add .
git commit -m "Kort beskrivelse av endringen"
git push
```

Siden oppdateres automatisk innen 1-2 minutter.

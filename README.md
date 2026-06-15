# WebOwl — eigen site

Eén bestand: `index.html` (HTML + CSS + JS samen). Statisch, geen build-stap.
Drietalig NL/FR/EN via de toggle rechtsboven. Concept: "de site die nooit slaapt" —
nachtblauw + amber (lamplicht), met een live klok + status als signatuurelement.

> Lopende to-do's en change log staan in `CLAUDE.md`.

## Aanpassen
Alle teksten staan in het `I18N`-object onderaan `index.html` (nl + fr + en blokken).
- Portfolio-links: zoek `const links =` in het script → de echte URL's staan er al in.
- WhatsApp: zoek `WHATSAPP_NUMBER` → vul je nummer in als "32xxxxxxxxx" (geen + of spaties).
  Zolang dit leeg is, valt de knop terug op het contactformulier.
- Contactformulier: werkt via Web3Forms (key staat al ingevuld in het `access_key`-veld);
  berichten landen in Gmail.
- E-mail: zoek `dylan@webowl.be` → pas aan als je adres wijzigt.
- KBO-nummer: zoek `foot.kbo` in de I18N-blokken → vul in na inschrijving.

## Social share card
`og-image.png` (1200×630) is de preview die verschijnt als je de link deelt (WhatsApp, socials).
Bron is `og-image.html` — pas die aan en render opnieuw naar PNG (headless Chrome screenshot,
1200×630). De `.html` wordt niet mee gedeployed (staat in de `ignore` van `firebase.json`).

## Lokaal bekijken
Dubbelklik `index.html`, of in VS Code: rechtsklik → Open with Live Server.
(Dit is gewone HTML, dus Live Server wérkt hier wél — anders dan bij het Astro-project.)

## Deployen (Firebase)
1. `firebase deploy` (project-ID staat in `.firebaserc`).
2. Custom domain webowl.be is gekoppeld in Firebase Console → Hosting.
3. DNS staat bij Gandi (A @ → Firebase, www CNAME → webowl-ce246.web.app).

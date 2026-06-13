# WebOwl — eigen site

E�n bestand: `index.html` (HTML + CSS + JS samen). Statisch, geen build-stap.
Tweetalig NL/EN via de toggle rechtsboven. Concept: "de site die nooit slaapt" —
nachtblauw + amber (lamplicht), met een live klok + status als signatuurelement.

## Aanpassen
Alle teksten staan in het `I18N`-object onderaan `index.html` (nl + en blokken).
- Portfolio-links: zoek `const links =` in het script → vul je echte URL's in.
- WhatsApp: zoek `WHATSAPP_NUMBER` → vul je nummer in als "32xxxxxxxxx" (geen + of spaties).
- Contactformulier: zoek `JOUW_WEB3FORMS_KEY` → vervang door je gratis key van web3forms.com
  (maak de key aan op je WebOwl-mailadres). Zonder key toont het formulier een nette melding.
- E-mail: zoek `hallo@webowl.be` (2x) → pas aan naar je echte adres.
- KBO-nummer: zoek `volgt na registratie` in de footer → vul in na inschrijving.

## Lokaal bekijken
Dubbelklik `index.html`, of in VS Code: rechtsklik → Open with Live Server.
(Dit is gewone HTML, dus Live Server wérkt hier wél — anders dan bij het Astro-project.)

## Deployen (Firebase + Cloudflare)
1. Firebase-project aanmaken, project-ID in `.firebaserc` zetten
2. `firebase deploy --only hosting`
3. Custom domain webowl.be koppelen in Firebase Console → Hosting
4. Cloudflare DNS: A-records van Firebase toevoegen, proxy op "DNS only" (grijze wolk)

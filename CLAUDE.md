# WebOwl — progress tracker

Small running log of what's done and what's left on the **marketing site** (`index.html`).
Single file: HTML + CSS + JS together, static, no build step. Trilingual NL/FR/EN via the
toggle top-right. Deploy with `firebase deploy`.

> Full project background lives in the handoff doc (who I am, business model, the kebab-mockup
> next move). This file is just the site to-do list + change log.

---

## ✅ Done
- Site live on Firebase (webowl.be) with SSL, NL/EN.
- Contact form working (Web3Forms → Gmail).
- **French (FR) added** — full third language, seamless toggle between NL / FR / EN.
- **SEO `<head>`** — local keywords (Antwerpen), geo tags, canonical, robots,
  `ProfessionalService` structured data (areaServed Antwerpen → provincie → België).
- **Social share card** — `og-image.png` (1200×630), built from `og-image.html` and
  rendered headless; wired into Open Graph + Twitter meta. Source HTML excluded from deploy.
- **Portfolio links live** — Stesha Gallery (steshagallery.com), Cappy Studios
  (cappystudios.dev), Snake 50 (snake50.com).
- Gallery card relabeled to real name "Stesha Gallery".

## ⏳ To do (small, non-blocking polish)
- [ ] **Images** — add real photos / visuals to the work cards + sections (planned next).
- [ ] **About photo** — replace the "Foto komt hier (Dylan)" placeholder box with a real photo.
      (Search `about-photo` in HTML / `about.photo` in the I18N blocks.)
- [ ] **WhatsApp number** — search `WHATSAPP_NUMBER`, set as `32xxxxxxxxx` (no + or spaces).
      Falls back to the contact form while empty.
- [ ] **KBO / ondernemingsnummer** in footer — after registering as zelfstandige.
      (Search `foot.kbo` in the I18N blocks.)
- [ ] **Google Business Profile** for WebOwl — the real lever for being *found* in Antwerp
      (Maps + local pack + reviews). Free. Bigger SEO impact than any meta tag.
- [ ] (Optional) wire `dylan@webowl.be` into Gmail send-as for one-inbox workflow.

## 🔁 After any change
- Test the NL/FR/EN toggle + contact form locally (open `index.html` / Live Server).
- If `og-image.html` wording changes → re-render the PNG (headless Chrome screenshot, 1200×630).
- `firebase deploy` to push live.

---

## Change log
- **2026-06-15**
  - Added FR as a full third language (nav button + `fr` I18N block + form messages).
  - Upgraded `<head>`: regional SEO meta, geo tags, `ProfessionalService` JSON-LD.
  - Built + wired social share card (`og-image.png` / `og-image.html`).
  - Filled portfolio links; renamed gallery card to "Stesha Gallery".

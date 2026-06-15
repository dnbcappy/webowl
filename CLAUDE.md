# WebOwl — progress tracker

Small running log of what's done and what's left on the **marketing site** (`index.html`).
Single file: HTML + CSS + JS together, static, no build step. Trilingual NL/FR/EN via the
toggle top-right. Deploy with `firebase deploy`.

> Full project background lives in the handoff doc (who I am, business model, the kebab-mockup
> next move). This file is just the site to-do list + change log.

---

## ✅ Done
- Site live on Firebase (webowl.be) with SSL, NL/FR/EN.
- Contact form working (Web3Forms → Gmail).
- **French (FR) added** — full third language, seamless toggle between NL / FR / EN.
- **SEO `<head>`** — local keywords (Antwerpen), geo tags, canonical, robots,
  `ProfessionalService` structured data (areaServed Antwerpen → provincie → België).
- **Social share card** — `og-image.png` (1200×630), built from `og-image.html` and
  rendered headless; wired into Open Graph + Twitter meta. Source HTML excluded from deploy.
- **Portfolio links live** — Stesha Gallery (steshagallery.com), Cappy Studios
  (cappystudios.dev), Snake 50 (snake50.com).
- Gallery card relabeled to real name "Stesha Gallery".
- **Work-card images** — real site screenshots (WebP, 1200×750) in `img/`
  (`work-stesha.webp`, `work-cappy.webp`, `work-snake.webp`); lazy-loaded with
  gradient fallback. Big PNG originals kept locally but excluded from deploy.
- **Security headers** — `firebase.json` sets nosniff, X-Frame-Options SAMEORIGIN,
  Referrer-Policy, Permissions-Policy, HSTS. (Static site, no XSS sink; form key is
  public-by-design and does not reveal the destination inbox.)

## ⏳ To do (small, non-blocking polish)
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
  - **Hero liveliness pass**: floating CSS "browser mockup" on the right
    (`.hero-visual` / `.mock`) with a pulsing `24/7 online` chip; bg glow now
    "breathes"; hero is 2-col (`.hero-inner`, mockup hidden <920px). Mockup text is
    language-aware (`mock.*` keys in all 3 I18N blocks). A real site screenshot can
    drop into the mockup later (~1000×625).
  - **Pricing card glow fix**: glow spans the whole card (ellipse wash) instead of
    cutting off ~⅔ down. (Search `.price-card .glow`.)
  - Image specs for next step: work-card thumbs **1200×750** (16:10), about photo
    **800×1000** (4:5).
  - **Work-card screenshots added** — WebP 1200×750 in `img/` (stesha 29 KB, cappy
    81 KB, snake 55 KB); `.work-thumb img` cover, lazy-load, `onerror` falls back to
    gradient. Old PNG originals excluded from deploy (`img/work-*.png` in ignore).
  - **Security pass** — added response headers in `firebase.json` (nosniff,
    SAMEORIGIN, Referrer-Policy, Permissions-Policy, HSTS). Audited: no personal
    email anywhere on site, no XSS sinks, external links have `rel=noopener`.
  - **CSP added** to `firebase.json` (`default-src 'self'` + explicit allows for
    fonts.googleapis/gstatic, api.web3forms, data: favicon; `'unsafe-inline'` needed
    for the inline style/script + `onerror`). Verified on a preview channel (fonts,
    form submit, console all clean) then deployed live. Note: CSP/headers only apply
    on Firebase, not Live Server — test header changes via `hosting:channel:deploy`.
  - **A11y fix**: underlined the inline `dylan@webowl.be` link (`.contact-alt a`) so
    it's distinguishable beyond colour (Lighthouse "links rely on color" → resolved).

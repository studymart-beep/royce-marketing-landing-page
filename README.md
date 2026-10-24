# R0YCE Marketing — website

Static marketing site for **R0YCE Marketing**: Meta Ads management, TikTok Ads management,
advertising creative production, landing pages and campaign optimisation.

No framework, no build step — plain HTML, Tailwind via CDN, and inline CSS/JS.

## Files

| Path | Purpose |
|---|---|
| `index.html` | Homepage: hero, services, results, process, work, work-with-us, booking form, FAQ. |
| `privacy.html` | Privacy Policy. |
| `terms.html` | Terms & Conditions. |
| `404.html` | Not-found page (used automatically by Vercel / GitHub Pages). |
| `robots.txt` | Crawler rules, points to the sitemap. |
| `sitemap.xml` | Sitemap for the production domain. |
| `googleeb9200bab7701618.html` | Google Search Console verification file. **Do not rename or edit.** |
| `googleba69ea99c10b37f8.html` | Second Google Search Console verification file. **Do not rename or edit.** |
| `assets/` | Brand logo (`royce-logo.png`, `royce-logo-sm.png`, `royce-icon.png`), photography, sample video clips and the TikTok analytics screenshot. |

## Design system

- Ivory `#F7F3E9` — page background (dominant)
- Orange `#F36B21` — primary buttons, links, accents
- Deep forest `#0D3B2E` — headings, results section, footer
- Charcoal `#23302B` — body text
- Warm grey `#E4DDCE` — borders and quiet surfaces
- Headings: Fraunces (editorial serif) · Body: Inter
- Logo: gold Royce "R" mark (transparent PNG derived from the supplied artwork)

There is **no published pricing**. The site uses a “Work With Us” section and asks for a call so
scope and fee are agreed in writing — do not add price cards without the owner confirming figures.

## Deploying

Deploy the repository root as-is. No build command, no output directory.

- **Vercel:** already connected — production URL `https://royce-marketing-landing-page.vercel.app/`
- **GitHub Pages:** Settings → Pages → `main` / `/ (root)`

## Tracking

### Meta Pixel — `2156638741957885`

| Event | When | Notes |
|---|---|---|
| `PageView` | Every page load | From the pixel base code. |
| `ViewContent` | Landing page viewed | Once per session. No `value` sent. |
| `Contact` | First click on a WhatsApp or email link | Once per session. |
| `Lead` | Only after the form has been accepted by FormSubmit | Once per session. No `value` sent. |
| `Schedule` | **Not fired** | Reserved for a real booking confirmation via `window.r0yceTrackSchedule(bookingRef)`. |

No personal data (name, email, phone, message) is ever passed to the pixel.
`view_item` is deliberately **not** used — it is a commerce event, not a standard service-view event.

**Testing:** append `?r0yce_test=1` to the URL for console logs, then watch
Meta Events Manager → Test Events.

### TikTok Pixel

Not configured yet. There is no TikTok Pixel ID in the project. To switch it on, set the ID once
in `index.html`:

```js
window.TIKTOK_PIXEL_ID = 'TIKTOK_PIXEL_ID';  // ← replace with the real ID
```

The loader and events (`ViewContent`, `Contact`, `SubmitForm`, `Schedule`) activate automatically
once the ID is set. Until then no TikTok request is made.

## Booking form

Posts to **FormSubmit** (`roycemarketing72@gmail.com`). One-time setup after any domain change:
submit the form on the live site, then click the activation link in that inbox (check Spam).

## SEO

- Canonical, Open Graph and Twitter tags point to the production URL.
- `robots.txt` and `sitemap.xml` reference the production URL.
- Both Google verification files must stay at the repository root.
- After a domain change, update: `<link rel="canonical">`, the OG/Twitter URLs, `sitemap.xml`
  and the `Sitemap:` line in `robots.txt`.

## Photography credits

All photographs are licensed stock from Wikimedia Commons:

- `assets/workspace-desk.jpg` — “Laptop and coffee on a desk”, Lauren Mancke, CC0.
- `assets/planning-desk.jpg` — “Person writing in notebook while using laptop at a modern workspace”, Shixart1985, CC BY 2.0.
- `assets/content-production.jpg` — “1E1A0124”, CC BY-SA 4.0.
- `assets/laptop-workspace.jpg` — “Coffee-desk-laptop-notebook”, CC0.

Keep the attribution if you republish these images.

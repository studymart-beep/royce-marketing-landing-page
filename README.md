# R0YCE Marketing — landing page

Static landing page for R0YCE Marketing: paid media (Meta Ads, TikTok Ads, YouTube Ads) and AI UGC creative.

## Files

| Path | Purpose |
|---|---|
| `index.html` | The entire landing page — HTML + Tailwind (CDN) + inline CSS/JS. No build step. |
| `assets/` | Videos and images used on the page. |
| `googleeb9200bab7701618.html` | Google Search Console site-verification file. **Do not rename, edit or delete** — Search Console checks it at the site root. |
| `robots.txt` | Crawler rules; points to the sitemap. |
| `sitemap.xml` | Single-URL sitemap for search engines. |
| `404.html` | Not-found page, used automatically by GitHub Pages / Netlify. |

## Deploying

The site is plain static files — deploy the repository root as-is:

- **GitHub Pages:** Settings → Pages → Source: `Deploy from a branch` → `main` / `/ (root)`.
- **Netlify / Vercel:** connect the repo, no build command, publish directory `.` (root).

## After the domain is live

1. **Search Console:** return to the verification screen and press *Verify*. If HTML-file verification fails, the file is not at `https://royce-marketing-landing-page.vercel.app/googleeb9200bab7701618.html` — check it was not renamed and sits in the publish root.
2. **Sitemap:** Search Console → Sitemaps → submit `sitemap.xml`. Already set to https://royce-marketing-landing-page.vercel.app/.
3. **Meta Pixel:** verify events in Events Manager → Test Events (append `?r0yce_test=1` to the URL for console logs).
4. **Booking form:** FormSubmit requires one-time activation of `roycemarketing72@gmail.com` from the live domain.

## Meta Pixel events

| Event | When |
|---|---|
| `PageView` | On every page load (pixel base code). |
| `ViewContent` | Landing page, Services, Pricing and Booking sections — once per session each. |
| `Lead` | Only after the booking form is accepted by FormSubmit. Once per session. |
| `Schedule` | **Not fired.** Reserved for a real booking confirmation via `window.r0yceTrackSchedule(bookingRef)`. |

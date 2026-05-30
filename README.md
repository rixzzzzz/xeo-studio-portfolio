# XEO STUDIO — Portfolio Site

Static single-page marketing site for **XEO STUDIO** (AI short-form content agency).
Live: https://xeostudio.co

## Stack
- Single `index.html` (no framework)
- Tailwind CSS **compiled** to `style.css` (production build — the CDN is NOT used)
- Vanilla JS (sticky nav, FAQ accordion, contact form)
- Contact form via [Web3Forms](https://web3forms.com) (no backend)
- Deployed on Vercel (static, zero-config, served from repo root)

## ⚠️ Editing styles — READ THIS
The site uses a **compiled** Tailwind file (`style.css`). If you add or change any
Tailwind classes in `index.html`, you MUST rebuild the CSS or the new classes won't
be styled in production:

```bash
npm install         # first time only
npm run build:css   # regenerates style.css
```

Then commit **both** `index.html` and `style.css`.
Tip: run `npm run watch:css` to auto-rebuild while editing.

## Contact form
The form posts to Web3Forms. The access key lives in `index.html`
(`<input name="access_key" ...>`). Submissions are emailed to the address registered
at web3forms.com. This key is public by design — safe to commit.

## Deploy
Push to `master` → Vercel auto-deploys the repo root. No build step runs on Vercel
because the compiled `style.css` is committed.

## Files
| File | Purpose |
|------|---------|
| `index.html` | The site |
| `style.css` | Compiled Tailwind (generated — rebuild with `npm run build:css`) |
| `src/input.css`, `tailwind.config.js`, `package.json` | Tailwind build config |
| `xeo-logo.png` | Logo (nav, footer, favicon) |
| `og-image.png` | Social share card (1200×630) |
| `robots.txt`, `sitemap.xml` | SEO |
| `vercel.json` | Security headers |

# ReBloom — Glass Hair. Beauty That Stays.

> Korean glass-hair shampoo & conditioner engineered for India's hard water — in reusable packaging that becomes a vase or planter.

**Live site:** [rebloom-shop.vercel.app](https://rebloom-shop.vercel.app)  
**GitHub:** [github.com/shashankkallahallisuresh/Rebloom](https://github.com/shashankkallahallisuresh/Rebloom)

---

## About

ReBloom is a static marketing and storefront site for a glass-hair care brand targeting the Indian market. The site features:

- **Product showcase** — Shampoo (₹649) and Conditioner (₹649) with full ingredient storytelling
- **Glass-hair ritual** — Step-by-step routine guide
- **Hard-water focus** — GLDA chelation technology explained for Indian consumers
- **Eco-conscious packaging** — Bottles designed to repurpose as vases; tubs as planters (`#betterused`)
- **Working demo storefront** — Cart, OTP login, checkout, and order flow run entirely in the browser (no backend)
- **Dark / light mode** — Respects system preference via `color-scheme`
- **3D ambient canvas** — Three.js particle background
- **Custom cursor** — Lilac dot + ring on desktop

---

## Tech Stack

| Layer | Detail |
|---|---|
| Structure | Single `index.html` — no build step, no bundler, no dependencies |
| Fonts | Fraunces (serif headings), Space Grotesk (body), JetBrains Mono (labels) via Google Fonts |
| 3D | Three.js loaded via CDN |
| Styling | Vanilla CSS with CSS custom properties |
| Interactivity | Vanilla JS — cart state, OTP flow, scroll animations, cursor |
| Hosting | Vercel (static) |
| Config | `vercel.json` — security headers, clean URLs, no trailing slashes |

---

## Project Structure

```
rebloom-static/
├── index.html       # Entire site — markup, styles, and scripts in one file
├── vercel.json      # Vercel deployment config + security headers
├── .gitignore
├── LICENSE
└── README.md
```

---

## Features

### Storefront
- Add to cart, quantity controls, order summary
- OTP-based login simulation (demo, no real auth)
- Checkout flow with address and payment steps
- Toast notifications for cart actions

### SEO & Social
- Open Graph and Twitter Card meta tags
- JSON-LD structured data for Organization, Products, and FAQPage
- Canonical URL set to `https://rebloom.ai/`

### Performance & Security
- All images embedded as base64 SVGs — zero external image requests
- `vercel.json` enforces `X-Content-Type-Options`, `X-Frame-Options`, `Referrer-Policy`, and `Permissions-Policy` headers
- Fonts preconnected for faster load

### UX
- Smooth scroll, scroll-triggered animations
- Sticky nav with blur backdrop that tightens on scroll
- Marquee ingredient ticker
- Mobile-responsive (nav collapses, layout reflows)
- Custom cursor hidden on mobile/touch

---

## Running Locally

No build step needed — just open the file:

```bash
# Option 1: open directly
open index.html

# Option 2: serve locally (avoids any CORS quirks with fonts)
npx serve .
# or
python3 -m http.server 8080
```

---

## Deploying

### Vercel (recommended)

The site is already configured for Vercel via `vercel.json`.

```bash
npm i -g vercel
vercel --prod
```

Or connect your GitHub repo on [vercel.com](https://vercel.com) — every push to `main` redeploys automatically.

### Any static host

Upload `index.html` and `vercel.json` to any static host (Netlify, GitHub Pages, Cloudflare Pages, S3 + CloudFront). No server-side processing required.

---

## Customisation

| What | Where in `index.html` |
|---|---|
| Brand colors | `:root` CSS variables at the top of `<style>` |
| Product prices | Search `₹649` |
| Product descriptions | Hero section and `#shop` section |
| FAQ answers | `<section id="faq">` and the JSON-LD `FAQPage` block |
| OG image | Add an absolute URL to the `og:image` meta tag |
| Canonical URL | Update `https://rebloom.ai/` to your real domain |

---

## Notes

- The cart, login, and checkout are **demo-only** — no real payments or orders are processed. To go live, connect a backend (e.g. Razorpay, Shopify Storefront API, or a custom Node/Python service).
- Ratings and reviews are sample content — replace before launch.
- `vercel.json` security headers work on Vercel only; configure equivalent headers on other hosts manually.

---

## License

[MIT](LICENSE)

# ReBloom — static site

Self-contained marketing + storefront site for ReBloom (glass-hair care).
Single `index.html` with all images embedded — no build step, no dependencies.

## Deploy it yourself (≈3 minutes)

### Option A — GitHub + Vercel (recommended, auto-deploys on every push)

**1. Push to GitHub**
```bash
cd rebloom-static
git init
git add .
git commit -m "ReBloom static site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/rebloom.git   # create this empty repo on github.com first
git push -u origin main
```

**2. Deploy on Vercel**
- Go to **vercel.com → Add New → Project**
- **Import** your `rebloom` GitHub repo
- Framework preset: **Other** · Build command: *(leave empty)* · Output dir: `.` (root)
- Click **Deploy**

Done — you get a live `https://rebloom-xxx.vercel.app` URL, and every future `git push` redeploys automatically.

### Option B — Vercel CLI (no GitHub)
```bash
cd rebloom-static
npx vercel          # links + previews
npx vercel --prod   # production URL
```

## Custom domain
Vercel dashboard → your project → **Settings → Domains** → add `rebloom.ai` (follow the DNS steps shown).

## Notes
- It's a **static front-end**: the cart, accounts, OTP and checkout run in the browser as a working demo (no server). For real orders/payments you'd connect a backend or Shopify — that's a separate build.
- Ratings/reviews are sample content; swap in real ones before heavy promotion.
- `vercel.json` adds sensible security headers; no other config needed.

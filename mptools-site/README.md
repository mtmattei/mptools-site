# MP Cutting Tools Website

Industrial supplies website for MP Cutting Tools, Montreal. Bilingual (EN/FR).

**Live URL:** https://mptools.ca

---

## Quick Start (Local Development)

```bash
npm install
npm run dev
```

Then open http://localhost:4321

---

## Deployment Guide

### Step 1: Buy the Domain

1. Go to [Porkbun](https://porkbun.com) or [Namecheap](https://namecheap.com)
2. Search for `mptools.ca`
3. Purchase (~$12-15/year)
4. Keep the confirmation email—you'll need access to DNS settings later

---

### Step 2: Set Up Formspree (Form Handling)

1. Go to [formspree.io](https://formspree.io)
2. Sign up with `alex@mpcuttingtools.ca`
3. Create a new form
4. Copy your form endpoint (looks like `https://formspree.io/f/xxxxxxxx`)
5. Update both files:
   - `src/pages/index.astro` — find `action="https://formspree.io/f/xyzgbqkl"` and replace
   - `src/pages/fr/index.astro` — same thing

---

### Step 3: Push to GitHub

1. Create a GitHub account if you don't have one: [github.com](https://github.com)
2. Create a new repository called `mptools-site`
3. Push the code:

```bash
cd mptools-site
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mptools-site.git
git push -u origin main
```

---

### Step 4: Deploy to Cloudflare Pages

1. Go to [Cloudflare](https://dash.cloudflare.com) and create an account
2. Click **Workers & Pages** in the sidebar
3. Click **Create** → **Pages** → **Connect to Git**
4. Authorize GitHub and select your `mptools-site` repository
5. Configure the build:
   - **Framework preset:** Astro
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
6. Click **Save and Deploy**
7. Wait ~2 minutes for the first build

You'll get a URL like `mptools-site.pages.dev` — the site is now live!

---

### Step 5: Connect Your Domain

**In Cloudflare:**
1. Go to your Pages project → **Custom domains**
2. Click **Set up a custom domain**
3. Enter `mptools.ca`
4. Cloudflare will show you DNS records to add

**In your domain registrar (Porkbun/Namecheap):**
1. Go to DNS settings for `mptools.ca`
2. Add the records Cloudflare shows you (usually CNAME records)
3. Wait 5-30 minutes for DNS propagation

**Add www redirect:**
1. In Cloudflare Pages, also add `www.mptools.ca` as a custom domain
2. It will automatically redirect to the main domain

---

### Step 6: Verify Everything Works

- [ ] https://mptools.ca loads
- [ ] https://www.mptools.ca redirects to mptools.ca
- [ ] https://mptools.ca/fr loads French version
- [ ] Language toggle works
- [ ] Form submission works (test it!)
- [ ] Phone number links work on mobile

---

## Post-Launch: Google Business Profile

This is critical for local SEO.

1. Go to [business.google.com](https://business.google.com)
2. Click **Manage now**
3. Search for "MP Cutting Tools" — if it exists, claim it. If not, create it.
4. Fill out:
   - Business name: MP Cutting Tools
   - Category: Industrial Equipment Supplier
   - Service area: Montreal, LaSalle, Dorval, Laval, Longueuil
   - Phone: (514) 366-7000
   - Website: https://mptools.ca
5. Verify (usually by phone or postcard)
6. Add photos of products, the shop, etc.
7. Ask happy customers to leave reviews

---

## File Structure

```
mptools-site/
├── src/
│   ├── layouts/
│   │   └── Layout.astro      # Base HTML template
│   ├── pages/
│   │   ├── index.astro       # English homepage
│   │   └── fr/
│   │       └── index.astro   # French homepage
│   └── styles/
│       └── global.css        # All styles
├── public/
│   ├── favicon.svg           # Browser tab icon
│   └── robots.txt            # SEO crawl rules
├── astro.config.mjs          # Astro configuration
├── package.json
└── README.md
```

---

## Making Updates

1. Edit files locally
2. Test with `npm run dev`
3. Commit and push:

```bash
git add .
git commit -m "Description of changes"
git push
```

Cloudflare Pages will automatically rebuild and deploy.

---

## Contact Info (Update Here If Changed)

- **Phone:** (514) 366-7000
- **Email:** alex@mpcuttingtools.ca
- **Domain:** mptools.ca

To update contact info, search and replace in:
- `src/pages/index.astro`
- `src/pages/fr/index.astro`

---

## Need Help?

If something breaks, check:
1. Cloudflare Pages dashboard for build errors
2. Browser console for JavaScript errors
3. Formspree dashboard for form issues

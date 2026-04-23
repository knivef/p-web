# PayRam — Features & Press Section

This repo contains two ready-to-integrate HTML sections for the PayRam website:

1. **"Why PayRam" features grid** — 6 feature cards with emoji headings, hover states, and pill badges
2. **"Featured In" press logo bar** — 6 publication logos with grayscale-to-color hover effect

---

## Where to implement

Both sections sit between the **hero section** and the **merchant dashboard section** on the homepage (`/`).

In the source file, find the closing tag of the hero section:

```html
</section> <!-- hero: class="bg-primary relative overflow-hidden" -->
```

Paste the two sections immediately after it, before the merchant dashboard section begins:

```html
</section> <!-- end hero -->

<!-- INSERT: Why PayRam features grid -->
<!-- INSERT: Featured In press bar -->

<section class="bg-primary py-[60px] md:py-[80px]"> <!-- merchant dashboard -->
```

---

## Files in this repo

```
index.html      Full standalone preview of both sections (open in browser to review)
assets/
  ap-logo.png               AP News logo
  cointelegraph-logo.png    CoinTelegraph logo
  techbullion-logo.webp     TechBullion logo
  thegamblest-logo.svg      The Gamblest logo
  anw-logo.svg              Access Newswire logo
```

> Note: Analytics Insight has no logo file — it renders as styled text.

---

## Asset setup

### 1. Upload assets to the PayRam server

Copy all files from the `assets/` folder into the PayRam project's public assets directory. Based on the existing site structure, the correct path is:

```
/public/assets/
```

Or wherever the site currently serves static files from (check where existing logos like `ap-logo.png` live on the production server).

### 2. Update image paths in the source

Once uploaded, update the `src` attributes in the Featured In section to match the server's asset path. For example, if assets are served from `/assets/`:

```html
<img src="/assets/ap-logo.png" alt="AP News" />
<img src="/assets/cointelegraph-logo.png" alt="CoinTelegraph" />
<img src="/assets/techbullion-logo.webp" alt="TechBullion" />
<img src="/assets/thegamblest-logo.svg" alt="The Gamblest" />
<img src="/assets/anw-logo.svg" alt="Access Newswire" />
```

If the site uses a CDN or a different base path (e.g. `/cdn/assets/`), update accordingly.

---

## Styling notes

- The site uses **Tailwind CSS v4** and **Montserrat** for headings, **Poppins** for body text
- The sections use inline styles for portability — convert to Tailwind classes when integrating into the live codebase (see Tailwind class reference in the comments within `index.html`)
- Background color `#141830` matches the existing "Copy & Paste" section on the page
- Brand accent: `#caff54` (lime green)

---

## Feature card links

Each card heading links to its respective docs page with UTM tracking already applied. Do not modify the URLs unless the UTM parameters need to change.

| # | Feature | URL |
|---|---------|-----|
| 01 | Operator Mode | `payram.com/operator` |
| 02 | Payment Links & APIs | `docs.payram.com/features/payment-links` |
| 03 | Customer Deposit Wallets | `docs.payram.com/features/customer-deposit-wallets` |
| 04 | SmartSweep | `docs.payram.com/features/smartsweep` |
| 05 | Payouts | `docs.payram.com/features/payouts` |
| 06 | Card-to-Crypto | `docs.payram.com/features/card-to-crypto-fiat-onramp` |

All links open in a new tab (`target="_blank" rel="noopener noreferrer"`).

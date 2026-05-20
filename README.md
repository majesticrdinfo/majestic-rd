# Majestic R&D — Website

**Live URL:** https://majestic-peptides.com  
**Stack:** Static HTML → GitHub → Cloudflare Pages  
**Analytics:** Google Analytics G-EE127Y9MQC | Google Search Console  
**Cost:** $0/month (Cloudflare Pages free tier)

---

## Folder Structure

```
majestic-rd/
├── index.html          ← Homepage (R&D overview, AIM teaser, peptide teaser)
├── aim.html            ← AIM Therapeutix dedicated page
├── peptides.html       ← GLP peptide program page
├── cbg.html            ← CBG program (placeholder — in development)
├── _redirects          ← Cloudflare Pages: clean URLs + 404 handling
├── robots.txt          ← Search engine crawl rules
├── sitemap.xml         ← Google Search Console sitemap
├── assets/
│   ├── css/            ← Shared stylesheets (future use — currently inline)
│   ├── js/             ← Shared scripts (future use — currently inline)
│   └── img/            ← Images, logos, COA thumbnails
├── docs/               ← Internal docs (NOT public-facing — do not commit sensitive files)
│   └── .gitkeep
└── pages/              ← Future pages staging area (blog, articles, landing pages)
    └── .gitkeep
```

---

## Deployment (Cloudflare Pages via GitHub)

### First-time setup
1. Push this repo to GitHub (github.com → New Repository → name it `majestic-rd`)
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → Pages → Create a project
3. Connect GitHub → select `majestic-rd` repo
4. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/` (root)
5. Deploy. Cloudflare gives you a `*.pages.dev` preview URL.
6. Add custom domain: Pages → Custom Domains → add `majestic-peptides.com`
7. Cloudflare auto-handles DNS (you own the domain there already).

### Every deploy after that
```bash
git add .
git commit -m "describe what changed"
git push
```
Cloudflare auto-deploys on every push to main. Live in ~30 seconds.

---

## Google Search Console Setup

1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Add property → URL prefix → `https://majestic-peptides.com`
3. Verify via **DNS record** method (easiest since you're on Cloudflare):
   - GSC gives you a TXT record like: `google-site-verification=XXXXX`
   - In Cloudflare DNS → Add record → Type: TXT → Name: @ → Value: paste it
   - Back in GSC → Verify. Done.
4. Submit sitemap: GSC → Sitemaps → add `sitemap.xml`

---

## Pages Status

| Page | Status | Notes |
|------|--------|-------|
| index.html | Ready (pending Issues 1+2) | Gate items: attorney + API grade confirmation |
| aim.html | Ready (pending Issues 1+2) | Gate items: same |
| peptides.html | Ready (pending Issues 1+2) | Gate items: same |
| cbg.html | Live as placeholder | Noindexed until program ready |
| aim_clinical_workflow.html | Built, not in repo | Needs compliance audit |
| aim_physician_onepager.html | Built, not in repo | Needs compliance audit |
| aim_sales_cheatsheet.html | Built, not in repo | Needs compliance audit |

---

## Compliance Gate — DO NOT DEPLOY UNTIL RESOLVED

- [ ] Healthcare attorney consultation (dispensing model + AIM formulation)
- [ ] API grade confirmation in writing (pharma-grade vs RUO)
- [ ] Issues 1 + 2 copy fixes (compounding language, dosing language) — post-attorney
- [ ] Physician Terms of Sale template built

---

*Majestic R&D | Confidential | Last updated: May 19, 2026*

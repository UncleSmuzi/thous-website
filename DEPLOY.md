# THOUS V2.1 Deploy Package

## What Changed

| Fix | Files | Details |
|-----|-------|---------|
| **1. Footer bug** | `library.html`, `journal.html` | Closed unclosed Facebook `<a>` tag that was swallowing the rest of the footer |
| **2. Library pricing** | `library.html` | Removed PayFast references. Empire + Founder Circle now show "Coming Soon" labels. Free tier unchanged |
| **3. Spam gate** | `library.html`, `journal.html`, `contact.html`, `academy.html`, `events.html` | Honeypot field (`name="website"`) on every form + 60s client-side rate limit |
| **4. Journal articles** | `journal.html` + new folder | Each entry now links to its own page. Template + 4 sample articles ready |
| **5. OI Sprint copy** | `index.html`, `services.html` | Broader language covering both established ops and first-time systems |

## File List

Root files (replace existing):
- `index.html`
- `services.html`
- `contact.html`
- `library.html`
- `journal.html`
- `academy.html`
- `events.html`

New folder:
- `journal/article-template.html` (copy this to create new articles)
- `journal/why-good-businesses-poor-decisions.html`
- `journal/your-brand-isnt-confused.html`
- `journal/operational-intelligence-growing-businesses.html`
- `journal/founder-bottleneck.html`

## Deploy Steps

1. **Create the `journal/` folder** in your repo root if it doesn't exist
2. **Replace** the 7 root HTML files with the versions in this package
3. **Copy** all 5 files from `journal/` into the new `journal/` folder
4. Commit and push:
   ```bash
   git add .
   git commit -m "THOUS V2.1: footer fix, pricing hold, spam guard, journal pages, OI copy"
   git push origin main
   ```
5. Wait 2–5 minutes for GitHub Pages to deploy
6. Verify:
   - https://thous.co.za/library.html (footer renders correctly)
   - https://thous.co.za/journal.html (Read More links work)
   - https://thous.co.za/journal/why-good-businesses-poor-decisions.html (article loads)
   - Submit a form twice quickly — second should be blocked for 60s

## How to Add a New Journal Article

1. Copy `journal/article-template.html` to `journal/your-article-slug.html`
2. Replace these placeholders:
   - `ARTICLE_SLUG` → your-article-slug
   - `ARTICLE_TITLE` → Page title (SEO)
   - `ARTICLE_HEADLINE` → Main H1 headline
   - `ARTICLE_DESCRIPTION` → Meta description
   - `PUBLISH_DATE` → e.g. "August 2026"
   - `CATEGORY` → e.g. "Strategy"
   - `ARTICLE_LEAD_PARAGRAPH` → Opening paragraph
   - Replace content between `<!-- ARTICLE_CONTENT_START -->` and `<!-- ARTICLE_CONTENT_END -->`
3. Add a card to `journal.html` linking to the new page

## Security Notes

- **Honeypot**: Hidden field `name="website"`. Bots fill it, humans don't. Formspree will reject submissions where this field has a value.
- **Rate limit**: 60-second cooldown between any form submissions across the site (stored in `localStorage`).
- **GitHub Pages limitations**: You cannot set custom security headers (CSP, HSTS, X-Frame-Options) on GitHub Pages directly. To add these, put Cloudflare in front of your Pages site (free tier).
- **SPF/DKIM/DMARC**: These are DNS records for your domain's email (hello@thous.co.za). Set them up with your domain registrar or email provider — not in the website code.

## Rollback

If anything breaks, revert the commit:
```bash
git revert HEAD
```

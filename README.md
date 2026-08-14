# THOUS — The House of Uncle Smuzi

**Live Site:** [https://thous.co.za](https://thous.co.za)

## Overview
THOUS is a South African brand strategy and operational intelligence consultancy. This is a 14-page static HTML/CSS/JS site hosted on GitHub Pages.

## Structure
- 14 HTML pages (no backend)
- Shared `style.css` (~1600 lines)
- Shared `js/main.js` (nav, mobile menu, scroll reveal, conveyor carousel)
- Form submissions via Formspree (7 distinct endpoints)
- Image assets in `/events/`, `/archetypes/`, `/library-covers/`

## Security Notes
- All textareas limited to 50 characters (`maxlength="50"`)
- Form submissions routed through Formspree (external, no server-side processing)
- No user data stored on-site
- HTTPS enforced by GitHub Pages
- Referrer-Policy and X-Content-Type-Options headers set via meta tags

## Form Endpoints
| Endpoint | Purpose | Pages |
|----------|---------|-------|
| `maewjdyj` | Newsletter + Library tier interests | journal.html, library.html |
| `mojgzkqw` | Discovery calls | contact.html (Discovery Session) |
| `mgawkdva` | Workshop enquiries | academy.html |
| `xeajzkrk` | Private / curated events | brunch.html, events.html |
| `REPLACE_BOOKINGS_ENDPOINT` | Bookings / waitlists / seat reservations | think-tank.html, long-table.html, open-insight.html |
| `xdendzpn` | Collaborations / general enquiries | contact.html (General Enquiry) |
| `xaewbjly` | Advertise with us | advertise.html |

## SEO
- Open Graph tags on all pages
- Twitter Card meta tags
- Canonical URLs
- JSON-LD structured data (Organization schema)
- robots.txt with sitemap reference

## Deployment
1. Push to GitHub repository
2. Enable GitHub Pages in repo settings
3. Ensure `CNAME` file contains `thous.co.za`
4. Update DNS A records to point to GitHub Pages IPs

---
© 2026 THOUS — The House of Uncle Smuzi (Pty) Ltd · Reg.No. 2026/516707/07

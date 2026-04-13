# Clean Money Corporation — website

Marketing site for Clean Money Corporation (CMC), the S-corp that
sells ACE (a rebrand/resale of CHERP) to other construction companies.

## Pages

| URL                    | Purpose                                           |
| ---------------------- | ------------------------------------------------- |
| `/` (`index.html`)     | Wedge landing page — thin-edge offer + 3 promises |
| `/ace` (`ace.html`)    | ACE product page — full feature grid + pricing    |
| `/about`               | Team + origin story + 4 values                    |
| `/contact`             | Contact form (Netlify Forms) + direct emails      |
| `/thanks.html`         | Post-submit confirmation                          |

All pages share `css/site.css` and the logo in `assets/`.

## Deploy

Netlify is hooked to this repo. Every push to `main` auto-deploys.

Local preview (any static server):

    npx serve .            # or python -m http.server, or VS Code Live Server

No build step. No dependencies. No `npm install`.

## Contact form → Sean's email

The form on `/contact.html` uses **Netlify Forms** (the `data-netlify="true"`
attribute + hidden `form-name` field). Submissions land in the Netlify
dashboard automatically.

**One-time setup** after the first deploy:

1. Open the Netlify site dashboard
2. Navigate to **Site settings → Forms → Form notifications**
3. Click **Add notification** → **Email notification**
4. Set:
   - Event: `New form submission`
   - Form: `contact`
   - Email to notify: `sbedard@cleanmoneycorporation.com`
5. Save

After that, every submission pushes an email to Sean. Until that's set,
submissions still capture in the dashboard — nothing is lost.

Optional: add a secondary notification for Ken at `kdeibel@cleanmoneycorporation.com`.

## Branding

Logos come from the S-corp brand pack: `assets/cmc-logo.png` and
`assets/cmc-logo-transparent.png` (the transparent one is the default
used in `<img>` tags so it works on any background).

Colors are set in `css/site.css` as CSS custom properties:

    --ink:    #0b1220   (headlines)
    --accent: #0ea5a4   (teal — trust, clean)
    --gold:   #c89b3c   (reserved, used sparingly)
    --bg:     #f7f8fb   (light backdrop)

Override any of those in the `:root` block to re-skin the whole site.

## Content gaps to fill post-launch

- Replace placeholder ROI numbers on `ace.html` with real customer data once pilot customers are live
- Add customer logos / testimonial carousel on `index.html`
- Optional: embed a short demo video on `/ace` above the feature grid
- Social meta images (og:image) in each page head

## Owners

- **Ken Deibel** — Product & engineering — `kdeibel@cleanmoneycorporation.com`
- **Sean Bedard** — Field operations & sales — `sbedard@cleanmoneycorporation.com`

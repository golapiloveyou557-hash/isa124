# Probashi Voice — Multi-Region Lotto Portal

A deployment-ready static HTML5/CSS3/JavaScript portal for eight regional daily target rooms: Thailand, Saudi Arabia, Kuwait, Bahrain, Qatar, Malaysia, Singapore, and Brunei.

## Run locally

From this folder, run any static server, for example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`. No package installation or build process is required.

## Structure

`index.html` is the region selector. Each file in `countries/` is a dedicated country page with relative links back to the shared stylesheet and JavaScript. `assets/css/style.css` contains the complete responsive dark-gold design system. `assets/js/main.js` contains the country metadata, date display, country-page hydration, and home-page search filter. `assets/images/` is reserved for future logo and banner assets. `manus-routes.json` lists the complete static route set.

## Content updates

Target values in `assets/js/main.js` are sample/demo values. Replace them with verified operator content or connect the data model to a trusted server-side API. Do not put Supabase service-role keys or other secrets in browser JavaScript. Replace the WhatsApp and Telegram placeholders in `index.html` and each country page before production.

## Deployment

The project is compatible with Vercel, Netlify, GitHub Pages, and traditional shared hosting because all links are relative and there is no required server runtime. Upload the folder as-is. For Vercel/Netlify, the default static publish directory is the project root and no build command is needed.

## Supabase handoff

`.env.example` documents optional future Supabase and VIP-channel configuration. If live targets are added, use a server-side or edge-function layer and expose only the minimum public read data to the browser. The local demo should remain usable without Supabase.

## Completed front-end checks

- All eight region routes are present and linked from the home page.
- Country target cards are populated from one shared data model.
- Country search, date display, room-link copy, and native share fallback are wired.
- Empty result rows were replaced with an explicit verification-pending tracker so the UI is not falsely presented as live data.
- Misleading “verified” status labels were removed from the demo result state.
- No live lottery/result values are claimed as verified; demo targets remain clearly labeled.

## Production checklist

Before launch, verify the operator’s legal/compliance requirements, replace demo numbers, configure approved channel URLs, add the final brand assets, and confirm each region’s content is accurate for the current date.

## Permanent website

The published site is live at: https://drawroom-n8kksmok.manus.space

Hosting mode: Autoscale with a 120-minute idle window.


## ZIP-03 update
- Applied the supplied visual stylesheet to `assets/css/style.css`.
- Corrected the missing `.` on `.timer-grid` so the provided grid rules are valid CSS and actually apply.

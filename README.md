# NorthVibes landing page

Minimal static landing page for `northvibes.app`: the only visible page content is the supplied native NorthVibes SVG logo.

## Files

- `index.html` — semantic static markup
- `styles.css` — responsive dark cinematic composition, decorative CSS-only orbits and reduced-motion support
- `assets/northvibes.svg` — supplied source logo, preserved as SVG
- `assets/favicon.ico` — supplied favicon
- `deploy/nginx/northvibes.app.conf` — Nginx, TLS redirect, security headers and static cache policy

## Deployment

## Live deployment

**LIVE VERIFIED 2026-10-07:** the static site is served by Nginx on `nv-j26-web-01` from `/var/www/northvibes`. Cloudflare proxies both DNS records and runs in **Full (strict)** mode with a zone minimum TLS version of 1.2. The origin has a Let's Encrypt certificate for `northvibes.app` and `www.northvibes.app`, expiring 2027-01-05; `certbot.timer` is enabled for renewal.

HTTP redirects to HTTPS and `www.northvibes.app` redirects to the canonical `northvibes.app`. The Nginx configuration adds CSP, `nosniff`, no-referrer, restrictive permissions policy, frame denial, and static cache controls.

No analytics, third-party scripts, external fonts, trackers, cookies, JavaScript, or external assets are used.

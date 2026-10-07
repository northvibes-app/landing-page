# NorthVibes landing page

Minimal static landing page for `northvibes.app`: the only visible page content is the supplied native NorthVibes SVG logo.

## Files

- `index.html` — semantic static markup
- `styles.css` — responsive dark cinematic composition, decorative CSS-only orbits and reduced-motion support
- `assets/northvibes.svg` — supplied source logo, preserved as SVG
- `assets/favicon.ico` — supplied favicon
- `deploy/nginx/northvibes.app.conf` — Nginx, TLS redirect, security headers and static cache policy

## Deployment

The live origin is `nv-j26-web-01`, document root `/var/www/northvibes`. TLS uses Let's Encrypt for both `northvibes.app` and `www.northvibes.app`; Cloudflare proxies DNS and provides edge TLS.

No analytics, third-party scripts, external fonts, trackers, cookies, JavaScript, or external assets are used.

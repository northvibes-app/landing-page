# NorthVibes landing and sign-in entry

Static, framework-free landing/authentication entry for `northvibes.app`. It preserves the supplied NorthVibes compass logo and uses the brand's navy/blue/teal palette. The responsive sign-in panel offers Email plus clearly labeled Microsoft, GitHub and Google choices. Email login uses the same-origin Keycloak BFF at `/auth/login`; social buttons stay visibly unavailable until their authorized OAuth registrations and server-side credentials are configured. Email account creation stays disabled until SMTP delivery and email verification are confirmed.

## Files

- `index.html` — accessible semantic sign-in choices and registration-unavailable status
- `styles.css` — responsive branded layout, visible focus states, reduced-motion support, no external fonts or scripts
- `assets/northvibes-blue.svg`, `assets/northvibes.svg`, `assets/favicon.ico` — existing brand assets
- `deploy/nginx/northvibes.app.conf` — HTTPS, security headers and same-origin BFF proxy routes

## Authentication and provider setup

- The page remains static; it does not store credentials or tokens and adds no frontend framework or third-party scripts.
- Email login redirects to the existing authorization-code/PKCE S256 BFF. Provider buttons must only be enabled after their provider is configured in the existing Keycloak realm, the exact Keycloak broker callback is registered upstream, credentials are stored in Key Vault, and a successful login is verified.
- Do not enable local registration until Keycloak email verification is configured and an actual verification email is received and tested.

## Deployment

GitHub Actions deploys the committed static release to the existing `nv-j26-web-01` origin and verifies the public HTTPS homepage. The Login and Register controls are not considered operational merely because they render; verify the BFF routes and provider/registration state independently.

# shopping.bkia.com.au

Static landing page for the family shopping kiosk. Hosted on GitHub Pages
at the custom subdomain `shopping.bkia.com.au`.

## Why this exists

The real shopping list dashboard lives on Home Assistant at
`https://wooaeilbttvus6etixtt2izabobprcoj.ui.nabu.casa/shopping-list/list`.
Two problems we're solving with this wrapper:

1. **Friendlier URL.** The Nabu Casa cloud subdomain is a random
   alphanumeric string. `shopping.bkia.com.au` is what we share with
   family.
2. **Custom Home Screen icon.** HA serves its own apple-touch-icon for
   all dashboards (the HA logo). iOS captures the icon at "Add to Home
   Screen" time from whichever page is currently visible. This page
   serves a teal cart PNG so the Home Screen icon is recognisable.

## How it works

- Visiting `https://shopping.bkia.com.au/` in Safari shows a landing
  page with the cart, an Add-to-Home-Screen instruction, and a CTA to
  open the dashboard directly.
- iOS standalone mode is detected via `window.navigator.standalone` and
  `display-mode: standalone`. When launched from the Home Screen icon,
  the page redirects to the actual dashboard. When viewed in Safari,
  it stays put so the icon-capture flow works.

## Deploy

Push to `main`. GitHub Pages deploys automatically from the repo root.
TLS cert is auto-issued by GitHub via Let's Encrypt once the DNS CNAME
is verified.

DNS (one-time, at the bkia.com.au registrar / partnerconsole.net):

```
Type:  CNAME
Name:  shopping
Value: shieldsb-hub.github.io.
TTL:   3600
```

GitHub Pages settings (one-time):
- Source: deploy from branch `main`, folder `/`
- Custom domain: `shopping.bkia.com.au`
- Enforce HTTPS: on

## Updating the icon

Edit `icon.svg` (180×180 viewBox), then regenerate `icon.png` via
`sips -s format png -Z 180 icon.svg --out icon.png` (macOS) or
`rsvg-convert -w 180 -h 180 icon.svg -o icon.png` (Linux).

## Related

- `../ha-shopping/` — HA-side packages, scripts, dashboard config.

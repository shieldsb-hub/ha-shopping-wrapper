# shopping.bkia.com.au — DEPRECATED

> **As of 2026-05-08, this repo is retired.** `shopping.bkia.com.au` now
> points at the Vercel-hosted custom kiosk UI in the sibling repo
> [`shieldsb-hub/ha-shopping-proxy`](https://github.com/shieldsb-hub/ha-shopping-proxy).
> The DNS CNAME at partnerconsole.net was migrated from
> `shieldsb-hub.github.io.` to `*.vercel-dns-017.com.`, the GH Pages
> custom-domain config has been cleared, and the `CNAME` file has been
> removed from this repo.
>
> **Why retired:** the Phase 1 wrapper (this repo) only served a
> static landing page that captured a teal cart apple-touch-icon and
> redirected to the Nabu Casa kiosk URL. Phase 2 replaced both the
> redirect and the kiosk with a same-origin custom UI built on HA's
> REST API behind a path-scoped gateway, so anyone in the household
> can use the shopping list without an HA login. Same icon, no
> redirect, no SPA OAuth wall. See
> [`ha-shopping/BRIEFING.md`](https://github.com/shieldsb-hub/ha-shopping/blob/main/BRIEFING.md)
> M5 for the architectural narrative.
>
> **Kept (not deleted) so:** git history of the icon experiment
> remains discoverable; `icon.svg` and `icon.png` here were the source
> for what's now in `ha-shopping-proxy/public/`.

---

## Original purpose (preserved for history)

Static landing page for the family shopping kiosk. Hosted on GitHub
Pages at the custom subdomain `shopping.bkia.com.au` until 2026-05-08.

The page captured a teal cart apple-touch-icon for iOS Add-to-Home-
Screen and redirected to the actual Home Assistant dashboard URL. iOS
detected standalone-mode launches via `window.navigator.standalone`
and auto-redirected; Safari visits stayed on the landing page so the
icon-capture flow worked.

## Related (active)

- [`shieldsb-hub/ha-shopping-proxy`](https://github.com/shieldsb-hub/ha-shopping-proxy)
  — the live successor at `shopping.bkia.com.au`
- [`shieldsb-hub/ha-shopping`](https://github.com/shieldsb-hub/ha-shopping)
  — the HA-side packages, automations, and dashboard config

# Serving the demo at `meetrewrite.com/demo`

The interactive demo lives here as a **single self-contained `index.html`** (no build step, no
backend, no assets except Google Fonts loaded over CDN). It is already live standalone at:

  https://toddfishman.github.io/meetrewrite-demo/

`meetrewrite.com/demo` is a **URL path**, which is controlled by the meetrewrite.com app/host —
not by DNS. So one of the options below wires `/demo` to this content. Pick whichever fits your stack
(the site is **Next.js behind Cloudflare**; `/demo` currently returns 200, so an existing route may
need to be replaced).

---

## Option A — Drop in the single file (simplest, no proxy)
Copy `index.html` from this repo into the Next.js project's public dir:

    public/demo/index.html

Next.js serves it at `/demo`. ⚠️ If there's an existing `app/demo/` (or `pages/demo`) route, remove or
replace it — an app route takes precedence over the static file.

## Option B — Proxy from Next.js (keep it hosted here, auto-updates)
In `next.config.js` — no file copy, always reflects this repo:

    async rewrites() {
      return [
        { source: '/demo',          destination: 'https://toddfishman.github.io/meetrewrite-demo/' },
        { source: '/demo/:path*',   destination: 'https://toddfishman.github.io/meetrewrite-demo/:path*' },
      ];
    }

(Equivalent on Vercel via `vercel.json` "rewrites".)

## Option C — Cloudflare rule (you're already on Cloudflare; no app deploy)
Cloudflare Rules → Origin Rules / a small Worker proxying:

    meetrewrite.com/demo*  →  https://toddfishman.github.io/meetrewrite-demo/

Serves the demo at /demo with no redirect and no change to the Next.js app.

---

### Notes
- The demo is path-agnostic — it works served at `/`, `/demo`, or proxied. No relative asset paths.
- Want a redirect instead of inline serving? Just 301/302 `/demo` → the github.io URL above.
- Source of truth for the file: repo `toddfishman/meetrewrite-demo`, `index.html`.

# Rewrite — Interactive Workflow Demo

An interactive, self-contained demo of the [Rewrite](https://meetrewrite.com) product workflow:
turning a website / web app / storefront into a **native iOS app** (Swift / SwiftUI) — *preview free, pay when it ships*.

Walk through the real **13-step, 3-phase workflow**: scan & scope → preview & quote → build & handoff.

## What's new

**MeetRewrite** (default project) uses **real assets** from a dogfood build:

- Live site captures from `meetrewrite.com` (desktop + mobile)
- Native SwiftUI preview frames rendered from actual polish output
- Side-by-side compare on the free-preview step (web → native)

Three fictional examples (Shopify shop, React SaaS, Next.js invoicing) still illustrate the same flow with stylized placeholders.

## Try it

- **GitHub Pages:** https://toddfishman.github.io/meetrewrite-demo/
- **Local:** `python3 -m http.server 8765` then open http://localhost:8765/

Step through manually, click any step in the rail, or hit **Auto-run** to watch the whole thing. Includes a guided narration tour for first-time viewers.

Single static `index.html` + `assets/`, no backend. Brand styling (navy + pink→purple→cyan gradient, Space Grotesk) matched to meetrewrite.com.

*Unofficial demo — MeetRewrite uses real captures; other projects are illustrative examples. No payment is taken.*

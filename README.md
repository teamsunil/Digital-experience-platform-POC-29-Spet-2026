# Third Street Platform — Unified Digital Experience POC

A clickable proof of concept: **one central platform** (profiles, availability, locations, events, content, analytics) powering **three websites** — Mona's Ranch, Inez's D&D and Spinner City — plus the **Third Street Hub** admin.

## Live demo
Open `index.html` (or the GitHub Pages link) and use the switcher bar at the bottom of the screen.

**Key flow (2 minutes):**
1. Click **Live demo**.
2. On the left (Hub), switch **Juliet** to *Available*.
3. Press **Publish changes**.
4. Mona's website on the right instantly shows Juliet as *Available now* with a "Just arrived" highlight. Spinner City updates too.

Before each presentation, open **Platform** and press **Reset demo data**.

## Screens
| Route | What it shows |
|---|---|
| `#/monas` | Mona's Ranch homepage |
| `#/monas/available` | Who's Available Now (search + filters) |
| `#/inez` | Inez's D&D homepage |
| `#/spinner` | Spinner City gateway (both houses) |
| `#/admin` | Hub dashboard |
| `#/admin/availability` | Availability management + publish |
| `#/admin/analytics` | Visitors, profile views, call/contact clicks |
| `#/platform` | Architecture overview (live) |
| `#/demo` | Side-by-side Hub + website demo |

## Notes
- Single self-contained file; no build step or server needed. Only Google Fonts load from the internet.
- Demo data is stored in the viewer's browser (localStorage); nothing is sent anywhere.
- Portraits are placeholders, replaced by real photography from the CMS in production.
- Search engines are asked not to index this page (`noindex`).

## Proposed production stack
Next.js monorepo with a shared, themed component package → headless CMS (Payload / Sanity / Strapi) with draft & publish → typed Content API with edge caching → webhook-triggered on-demand revalidation → privacy-friendly analytics with a first-party event endpoint.

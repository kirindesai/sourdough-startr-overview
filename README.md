# sourdough-startr-overview
# Sourdough Startr

**Find the cleanest sourdough bread near you — verified.**

🌐 **Live at [sourdoughstartr.com](https://sourdoughstartr.com)**

---

## What It Is

Sourdough Startr is a verified directory of bakeries whose sourdough is made with clean ingredients only. Flour, water, salt, and a natural starter. No enriched flour, dough conditioners, or additives.

Every listing is confirmed directly through in-person visits, phone calls, or official published ingredient lists and nothing is assumed.

Currently live with 35+ verified bakeries across New York City, with San Francisco expansion underway.

---

## The Problem

Most bread sold as "sourdough" in America isn't real sourdough. It's conventional bread with additives designed to speed up the baking process. There's no easy way to tell from a bakery's name or storefront whether what they're selling is the real thing.

I built Sourdough Startr as a runner who got tired of reading ingredient labels at every bakery I walked into.

---

## Tech Stack

| Layer | Tools |
|---|---|
| Backend | Python, Flask |
| Data pipeline | pandas, custom 3-stage ETL (load → clean → analyze) |
| Search | Haversine formula distance search, browser Geolocation API |
| Geocoding | Nominatim (OpenStreetMap) |
| Maps | Leaflet.js + CartoDB dark tiles |
| Email integration | Resend API |
| Frontend | HTML, CSS, JavaScript (no frameworks) |
| Deployment | Vercel + custom domain via Namecheap |
| Version control | Git / GitHub (feature branch workflow, PRs) |
| AI-assisted dev | Claude Code (every diff reviewed before accepting) |

---

## Features

- **GPS proximity search** — finds the nearest verified bakeries from the user's live location
- **Address search** — Nominatim geocoding for manual location input
- **Interactive map** — Leaflet.js with dark CartoDB tiles and custom brown circle markers
- **Browse All** — neighborhood pill filters and premium sort dropdowns (by neighborhood or rating)
- **Bakery submission form** — bakeries can submit their ingredients directly for verification via the Earn Verification form
- **Flour Sourcing Type badges** — three-tier classification: Certified Organic / Heirloom & Stoneground / Transparent Regional
- **Verification status tracking** — Verified in-person / Verified online / Self-reported
- **Mobile-first design** — dark premium theme, Playfair Display + Inter typography, touch-friendly layout

---

## Data Pipeline

The app runs a three-stage Python pipeline on every deploy:

```
load_data.py      → ingests bakeries.csv, validates required fields,
                    reports missing data and verification breakdown
clean_data.py     → filters to verified entries only, validates
                    coordinates, standardizes formatting
search_bakeries.py → haversine distance calculation, find_nearest()
                    function, argparse CLI for location input
```

Data lives in a Google Sheet, exported as CSV, pushed to GitHub, and Vercel auto-deploys on every push to main.

---

## Distribution

- Launched Instagram [@sourdoughstartr](https://instagram.com/sourdoughstartr)
- Educational carousel content on sourdough fermentation, ingredient standards, and NYC/SF bakery spotlights
- Organic reposts from verified bakeries including Librae Bakery and Runner & Stone
- Direct bakery outreach via in-person visits and cold email

---

## Roadmap

- [ ] San Francisco expansion (in progress)
- [ ] Newsletter signup and weekly digest
- [ ] City-specific landing pages for SEO
- [ ] "Sourdough Startr Certified" paid verification tier for bakeries

---

*Built by a runner and UC Berkeley student who got tired of reading ingredient labels.*

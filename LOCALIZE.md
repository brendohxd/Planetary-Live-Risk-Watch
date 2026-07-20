# Localise this baseline in about 90 minutes

Work from the **`main`** branch. Do not start from `australia` unless you are improving the Australian build.

> National agencies issue warnings.  
> This project turns warnings into **plain-language, local, checkable context** so ordinary people prepare *before* the siren.  
> You do not need a movement. **One careful person per country** is enough to start saving lives.

## Minimum viable country fork

Ship when you have:

- [ ] Emergency number(s)
- [ ] National weather / geological service links
- [ ] At least **3 present** local facts with “how to verify”
- [ ] At least **3 historic** anchors people in your country remember
- [ ] Evacuation note: routes are local — name the agency that owns them
- [ ] Plain-language stage words (Watching / Raised / Building / Serious)
- [ ] Offline kit note: install Organic Maps or OsmAnd *before* crisis; paper routes

## 90-minute path

### Minutes 0–15 — `config.json`
Set `country_name`, `country_code`, `tagline`, `official_links`, `language_note`.

### Minutes 15–40 — `local-data.json` (trust engine)
Add **present** items people can check this year and **historic** anchors people remember. Each item needs: title, plain detail, how to verify, sources when possible.

### Minutes 40–70 — `risk-data.json`
Keep categories if they fit. Replace metrics, examples, `prep_priority`, and `conservative_reading` with local meaning. Keep global drivers (nuclear, El Niño) but always say **what they mean where you live**.

### Minutes 70–85 — Offline + actions
Copy the offline kit pattern: offline map apps, paper routes, “two ways out”. Add a Today / This week / This season action strip for your hazards.

### Minutes 85–90 — Deploy
GitHub Pages from your branch. Open once on a phone on Wi‑Fi so the service worker can cache.

## Truth-seeking rule
When models disagree (example: El Niño strength): cite the official product (agency, date, numbers); note when data-driven models look more severe than soft headlines; do not understate because understatement feels safer.

## After you ship
Add your fork to `FORKS.md` on the upstream repo (or open an issue) so others can find a maintained local page.

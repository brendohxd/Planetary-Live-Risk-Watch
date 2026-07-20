# Fork this for your country

**If you care about the place you live — take this baseline and build the local version.**

This is the **clean baseline** (no single-country local content baked in).

The live **Australia** build is maintained on the `australia` branch so you do **not** have to strip Australian agencies, wording, or examples before starting your own country.

One serious person per country is enough to start.

The more *local*, *specific*, and *plain-spoken* the information becomes, the more people can understand it and act. Global jargon loses the majority. Local agencies, local history people recognise, and local evacuation habits win trust.

## Branches

| Branch | Purpose |
|--------|---------|
| `main` | **Baseline template** — start here when forking for a new country |
| `australia` | **Australia build** — local present/historic data, BOM, plain AU English |

Live AU site (set GitHub Pages to the `australia` branch):
https://brendohxd.github.io/Planetary-Live-Risk-Watch/

## What to do when you fork

1. Fork this repo
2. Work from **`main`** (baseline) — not the Australia branch
3. Edit `config.json` with your country name, official warning links, and language
4. Fill `local-data.json` with **present** and **historic** facts people can verify locally
5. Localise plain-language text in `app.js` and category notes in `risk-data.json`
6. Put **your** official warning service first (always)

See [LOCALIZE.md](LOCALIZE.md) for a full checklist.

## Design rules (do not drop these)

1. **Local first** — present + historic local facts before global scores (builds trust)
2. **Plain language** — if something is serious, say **serious**. No hiding behind jargon
3. **Truth-seeking** — prefer documented agency numbers and models that track real observations, even when softer headlines lag
4. **Official warnings win** — this site is never the authority over national warning systems

## The bet

If enough countries get one passionate maintainer each, we get a network of local warning-and-prep pages instead of one thin global summary nobody trusts.

Fork it. Localise it. Make it useful.

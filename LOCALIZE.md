# How to localise this baseline

Work from the **`main`** branch. Do not start from `australia` unless you only want to improve the Australian build.

## 1. config.json

Set:

- `country_name` — e.g. "New Zealand"
- `country_code` — short code for display
- `tagline` — one line people understand
- `official_links` — weather, emergency, fire, quake agencies people already trust
- `language_note` — reminder that official alerts beat this site

## 2. local-data.json (most important for trust)

Add **present** items people can check this year, and **historic** anchors people remember.

Each item should include:

- short title
- plain-language detail
- how to verify (which official site or map)
- sources when possible

If people can verify a fact in their own country, they trust the rest of the system more — and are more likely to prepare.

## 3. risk-data.json

Keep the category list if it still fits. Replace:

- metrics and examples with ones that matter locally
- `prep_priority` with actions that work in your country
- `conservative_reading` in everyday language

Global drivers (nuclear risk, El Niño) can stay, but always explain **what they mean where you live**.

## 4. Plain language pass

Search and replace technical labels with everyday words where you can.

Stage words in the baseline:

- Watching
- Raised
- Building
- Serious

If a risk is severe, say so clearly. Soft wording that hides severity is a failure mode.

## 5. Truth-seeking on contested forecasts

When models disagree (example: El Niño strength):

- cite the official product (agency, date, numbers)
- note when dynamical models that track deep-ocean heat look more severe than softer averages or media summaries
- do not understate because understatement feels safer

Honesty builds long-term trust. Comfortable understatement does not.

## 6. Evacuation and vital local detail

Add what only locals know:

- emergency numbers
- fire/flood/tsunami zones culture
- leave-early norms
- trusted apps

The deeper and more specific you go, the better ordinary people can use the page.

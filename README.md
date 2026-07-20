# Earth Risk Watch

Transparent, data-driven global risk monitoring — built to help people stay informed and prepared without sensationalism or downplaying.

## What this is

Earth Risk Watch is a public dashboard that tracks 12 categories of Earth-impacting risk, pulling from multiple authoritative sources per category and explicitly flagging where those sources disagree. It exists because most risk reporting either buries the signal in noise or smooths over disagreement between sources to avoid alarming people — this project does neither.

## The 12 categories

1. Seismic Activity
2. Volcanic Activity
3. Solar & Space Weather
4. Ocean Temperatures & Marine Heatwaves (incl. El Niño)
5. Sea Level Rise & Coastal Extremes
6. Weather Extremes, Drought & Heat Stress
7. Wildfire Activity & Air Quality
8. Military Conflict & Escalation Risks
9. Near-Earth Objects (NEOs)
10. Geomagnetic Field Stability & Core Dynamics
11. Infrastructure & Financial Strain
12. Nuclear Risk

Nuclear Risk is explicitly linked to the Doomsday Clock (Bulletin of the Atomic Scientists), which is displayed as a dynamic gauge on the dashboard.

## Key principles

- **Data over opinion.** Every assessment is grounded in primary sources (NOAA, USGS, ESA, CPC, SIPRI, Bulletin of the Atomic Scientists, and similar bodies).
- **Discrepancies are shown, not hidden.** Where sources differ on severity, timeline, or interpretation, that disagreement is displayed directly, and the more conservative (cautious) reading is used for the displayed risk level.
- **Cumulative context matters.** A quiet week does not erase a multi-month trend. Categories track trend direction and cumulative context, not just the latest data point.
- **Cross-references.** Risks compound each other — the Cascading Impacts section on the site shows how categories amplify one another (e.g. El Niño → drought → wildfire → infrastructure/financial strain).
- **Preparation-focused.** Every category includes practical, tiered preparation guidance, and a general Preparation Hub covers cross-cutting priorities.

## How the site works

The site is a static, single-page app (`index.html` + Tailwind CDN + Chart.js), reading all of its content from `risk-data.json`. There is no backend — updating the dashboard means updating that one JSON file and pushing to `main`; GitHub Pages redeploys automatically.

Features:
- Doomsday Clock gauge (SVG, driven by `doomsday_clock.seconds_to_midnight` in the data file)
- Primary risk bar chart across all 12 categories
- Clickable category cards expanding into a modal with key metrics, trend/cumulative context, full recent-event history with sources, source comparison + discrepancies, conservative reading, cross-references, and preparation guidance
- Dedicated Cascading Impacts section built automatically from each category's cross-references
- Preparation Hub (immediate / this week / ongoing)
- Transparency & Methodology section
- Location & Alerts panel (manual entry or browser geolocation, stored locally in the browser — nothing is sent to a server)
- Accessibility: high-contrast mode and larger-text mode toggles
- Audio: "Listen" buttons use the browser's built-in text-to-speech (Web Speech API) to read the overall summary or any category's detail aloud
- Dark/light theme toggle

## Updating the data (`risk-data.json`)

For each category, research should pull from at least two (ideally three) independent authoritative sources, explicitly compare their numbers/timelines/severity framing, note any discrepancies, and use the more conservative reading where they diverge. Research should go beyond a single weekly summary report — actively search for recent (7–14 day) regional or fast-moving events that broader summaries can miss (this dashboard previously under-reported a real volcanic/tsunami event off New Zealand because it relied on a single weekly digest; don't repeat that).

Required fields per category object: `name`, `level` (Low/Moderate/High), `score` (0/1/2), `trend`, `cumulative_context`, `metrics`, `recent_events` (array of `{date, description, impact, sources}`), `sources_compared`, `discrepancies`, `conservative_reading`, `cross_references` (array of `{category, connection, metric}`), `prep_priority`.

Top-level fields: `date`, `last_updated`, `doomsday_clock` (`{seconds_to_midnight, as_of, source, context, primary_driver_category}`), `overall_summary` (`{framing, cumulative_context}`), `categories`.

Validate the file (`python3 -m json.tool risk-data.json` or any JSON linter) before committing — a malformed file is the single most common way this dashboard has broken in the past.

## Deployment

Hosted on GitHub Pages, served from the `main` branch root. After pushing changes, allow 30–60 seconds and hard-refresh (Ctrl/Cmd+Shift+R) before assuming a fix didn't work.

## Limitations

This is a public awareness and preparedness tool, not an official warning system. Always follow official local emergency management guidance over this dashboard. Reversal/collapse-style claims (e.g. geomagnetic pole reversal) are presented with scientific consensus context — current evidence does not support an imminent full reversal, even though underlying field weakening and pole drift are real and tracked here.

## Contributing

Feedback on data accuracy, missing events, or usability issues is welcome via GitHub issues.

## License

TBD — currently intended for open, non-commercial use focused on public preparedness.

# TOTORO Crossing ⛵

10-day wind & wave consensus for Aegean crossings — a single self-contained HTML page.

**Live:** https://seymurtari.github.io/totoro-crossing/

## What it does

Pick a point (paste coordinates, tap a preset, or use the inline Mapbox satellite picker showing the whole Aegean) and get a consensus report from two sources:

- **Windy Point Forecast** (GFS + ICON-EU wind, GFSwave + ICON-EU-wave waves) — orange lines, lightly smoothed to damp model-run noise.
- **Poseidon HCMR** (high-resolution Aegean METEO / WAM models, days 1–5) — thick cyan lines, shown raw; the most trusted source.
- **Charts:** wave height first, then wind speed; per-source median lines over a model min–max band, with red stripes where the two sources disagree by ≥ 6 kt wind or ≥ 0.5 m wave.
- **Daily table:** wave avg/max (m), period, wind avg/max (kt), gusts, direction, model counts, agreement rating, and a GO / CARE / NO verdict with editable thresholds.
- **Greek maps panel:** a "Greek maps 🌊" button expands live forecast maps from NOA/meteo.gr (WAM waves, BOLAM wind) and Univ. of Athens (WAM Aegean waves, SKIRON wind) with a shared 3-hourly lead-time slider — visual cross-check only, since neither institute publishes point data.
- All times **GMT+3** (Europe/Istanbul, no DST); both sources' UTC timestamps are converted onto one hourly grid.

## iPhone home screen

Open the live URL in Safari → Share → **Add to Home Screen**. The wave icon and standalone display are preconfigured.

## Notes

- No build, no dependencies to install — everything is in `index.html` (Leaflet loads from CDN only when the map picker opens).
- Horizons: Windy GFS ≈ 10 days, ICON-EU and Poseidon ≈ 5 days — beyond day 5 the forecast rests on Windy alone; treat late days as tendency.
- The embedded Windy key is quota-limited and Poseidon rides a public CORS relay — the page degrades gracefully if either fails.

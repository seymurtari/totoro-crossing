# TOTORO Crossing ⛵

14-day multi-source wind & wave consensus for Aegean crossings — a single self-contained HTML page.

**Live:** https://seymurtari.github.io/totoro-crossing/

## What it does

Pick a point (paste coordinates, tap a preset, or use the Mapbox satellite picker showing the whole Aegean) and get a 14-day consensus report:

- **Sources:** Open-Meteo (ECMWF, GFS, ICON, UKMO wind / WAM, GWAM, EWAM, MFWAM, GFSwave waves), Windy Point Forecast (GFS, ICON-EU / GFSwave, ICON-EU-wave), and Poseidon HCMR (high-res Aegean METEO/WAM, days 1–5, via CORS relay).
- **Charts:** per-source median lines in distinct colors over an all-model min–max band; red stripes where sources disagree by ≥ 6 kt wind or ≥ 0.5 m wave.
- **Daily table:** avg/max wind (kt), gusts, direction, wave height (m), period, model counts, agreement rating, and a GO / CARE / NO verdict with editable thresholds.

## iPhone home screen

Open the live URL in Safari → Share → **Add to Home Screen**. The wave icon and standalone display are preconfigured via `manifest.json` / apple-touch-icon.

## Notes

- No build, no dependencies to install — everything is in `index.html` (Leaflet loads from CDN only when the map picker opens).
- Model horizons differ (3–16 days); late days rest on fewer models and are marked accordingly. Beyond day 7 treat as tendency, not forecast.
- Weather APIs are free tiers; the embedded Windy key is quota-limited — the page degrades gracefully to the remaining sources if any fail.

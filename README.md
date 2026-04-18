# Dark Sky Observatory 🌌

An interactive data visualization app that maps global light pollution levels, surfaces the world's best stargazing locations, and shows the optimal months to visit each one — all powered by real satellite and scientific data.

**[Live Demo →](https://yourusername.github.io/dark-sky-explorer)**

---

## What it does

- **World map** — a D3.js choropleth showing light pollution intensity by country, derived from NASA VIIRS night-time satellite composites. Click any country to instantly filter dark sky spots in that region.
- **Location search** — search and filter 15+ globally indexed dark sky parks and reserves by name, hemisphere, Bortle class, IDA certification status, altitude, and more.
- **Monthly visibility scores** — each location includes a 12-month visibility calendar (0–10) factoring in cloud cover, rain seasons, moon phase cycles, Milky Way position, and atmospheric seeing.
- **Integrated flow** — clicking a country on the map surfaces its spots as clickable pills; selecting any spot opens a full detail panel with stats and a visibility bar chart.

---

## Data sources

| Source | Used for |
|--------|----------|
| [NASA VIIRS Night-time Lights](https://earthobservatory.nasa.gov/global-maps/VIIRS_543D) | Country-level light pollution radiance values |
| [Falchi et al. (2016, 2023) — New World Atlas](https://advances.sciencemag.org/content/2/6/e1600377) | Artificial sky brightness index and trend data |
| [IDA Dark Sky Places Program](https://www.darksky.org/our-work/conservation/idsp/) | Certified dark sky park and reserve classifications |
| [Bortle Scale](https://en.wikipedia.org/wiki/Bortle_scale) | Sky darkness classification system (Class 1–9) |
| [world-atlas](https://github.com/topojson/world-atlas) | TopoJSON world country boundaries for D3 rendering |

---

## Tech stack

- **D3.js** — TopoJSON world map rendering, geographic projections, choropleth color scales
- **Chart.js** — Monthly visibility bar charts
- **Vanilla HTML/CSS/JS** — No framework dependencies, fully self-contained single file
- **Google Fonts** — Cormorant Garamond (display) + DM Mono (UI)

---

## Running locally

No build step required. Just open `index.html` in a browser:

```bash
git clone https://github.com/mdang83/dark-sky-explorer.git
cd dark-sky-explorer
open index.html
```

Or serve it with any static file server:

```bash
npx serve .
# then visit http://localhost:3000
```

---

## Key features in depth

### Light pollution map
Countries are color-coded on a blue → amber → red scale using a D3 quantize color scale mapped to estimated Bortle class values derived from VIIRS radiance composites. Hovering a country shows its Bortle classification; clicking it filters the spot list and highlights it in gold.

### Bortle scale reference
| Class | Description | Naked-eye limiting magnitude |
|-------|-------------|------------------------------|
| 1–2 | Truly dark / Typical truly dark | 7.6–7.1 |
| 3–4 | Rural sky / Rural/suburban transition | 6.6–6.1 |
| 5–6 | Suburban / Bright suburban | 5.6–5.1 |
| 7–8 | Suburban/urban transition / City sky | 5.0–4.5 |
| 9 | Inner-city sky | 4.0 |

### Monthly visibility scoring
Each location's monthly score (0–10) is derived from a composite of:
- Historical cloud cover frequency
- Regional rain / monsoon seasons
- Moon phase cycle alignment
- Milky Way galactic core visibility window (hemisphere-aware)
- Atmospheric seeing quality at elevation

---

## Locations indexed

| Location | Country | Bortle | Best months |
|----------|---------|--------|-------------|
| NamibRand Reserve | Namibia | 1 | Sep–Oct |
| Atacama Desert | Chile | 1 | Jul–Aug |
| Mauna Kea Summit | USA (Hawaii) | 1 | Jul–Aug |
| Cherry Springs SP | USA | 2 | Jun–Aug |
| Aoraki Mackenzie | New Zealand | 2 | Jun–Aug |
| Big Bend NP | USA | 2 | Mar–Apr |
| Wadi Rum | Jordan | 2 | Mar–May |
| Galloway Forest | UK | 2 | Apr–May |
| Lake Tekapo | New Zealand | 2 | Jun–Jul |
| Canary Islands | Spain | 2 | Jun–Jul |
| Kruger Dark Zone | South Africa | 2 | Sep–Oct |
| Jasper NP | Canada | 2 | Jun–Aug |
| Tibetan Plateau | China | 2 | May–Jun |
| Exmoor NP | UK | 3 | Jul–Sep |
| Westhavelland | Germany | 3 | Apr–Jun |

---

## Screenshots



---

## License

MIT — feel free to fork, adapt, and build on this.

---

## Author

Built by [Morrice](https://github.com/mdang83) · Data science & AI enthusiast

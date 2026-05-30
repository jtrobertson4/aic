# A Collection, Measured — The Art Institute of Chicago

A data analysis of the Art Institute of Chicago's collection, written for the museum's
Acquisition Committee: how the collection is distributed across the world's regions and eras,
how it measures against the world's population, how concentrated it is by department and artist,
and a machine-learning model for what predicts whether a work ever gets exhibited.

Final project for **BUSN 32120 — Data Analysis with Python and SQL** · Jillian Robertson · Spring 2026.

---

## The website

The headline deliverable is an interactive presentation site (`index.html`). It opens on a random
artwork pulled live from the Art Institute's open API, samples that image in the browser to build a
colour palette, and themes the whole page from it: the background stays canvas-beige, the text takes
the darkest tone in the artwork, and every chart is rendered in the artwork's brighter notes. Press
**"New artwork"** to re-roll the work and repaint the page.

Everything below the artwork is the analysis itself — seven charts (department mix, acquisition pace,
cumulative growth, artist Lorenz curve, the representation index, the model scorecard, and a
coefficient chart) plus a step-by-step walkthrough of the prediction model.

### View it live

Link: 

To run locally:

```bash
python -m http.server 8000   # then open http://localhost:8000
```

---

## Repository contents

| File | Description |
|------|-------------|
| `index.html` | Interactive presentation website (self-contained, no build step). |
| `aic_collection_final_project_robertson.ipynb` | Main analysis notebook: data quality, EDA across three datasets, feature engineering, two models, and conclusions. |
| `aic_sql_queries.ipynb` | Standalone SQL notebook with the same 15 heavily-commented queries. |
| `README.md` | This file. |

---

## Data sources and credits

This project draws on three datasets:

1. **Art Institute of Chicago open-access API and public catalogue data.** The full catalogue of
   134,078 works was retrieved from the museum's public GitHub repository
   (`art-institute-of-chicago/api-data`). Artwork imagery is served via the museum's IIIF endpoint.
   All open-access images are provided under CC0 1.0 Universal. API documentation:
   <https://api.artic.edu/docs/>.

2. **Art Institute of Chicago local catalogue cache.** A richer per-work extract (place of origin,
   dates, colourfulness scores, exhibition history) produced during earlier coursework (HW4) and used
   here for the geographic, era-level, and exhibition analyses.

3. **World population by region (~2024).** Approximate regional population totals (UN-aligned
   groupings) used as the external benchmark for the representation index.
---

## AI disclosure

Claude (Anthropic) was used as a development tool in this project. It primarily assisted with
building out the data models and constructing the HTML presentation website.

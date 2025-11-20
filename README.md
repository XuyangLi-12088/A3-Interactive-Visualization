# US Age-Adjusted Death Rates — Interactive Visualization (D3 v7)

An interactive visualization of age-adjusted death rates for the 10 leading causes of death in the United States, featuring a choropleth map and trend analysis.

**Live Demo:** [https://xuyangli-12088.github.io/A3-Interactive-Visualization/](https://xuyangli-12088.github.io/A3-Interactive-Visualization/)

## Files
- `index.html` — main application (loads `NCHS_-_Leading_Causes_of_Death__United_States.csv`)
- `NCHS_-_Leading_Causes_of_Death__United_States.csv` — dataset from NCHS/CDC

## Features

### Interactive Controls
- **Cause selector** — filter by leading cause of death
- **Year slider** — select year from 1999 to present
- **Reset button** — restore default settings

### Visualizations
- **US Choropleth Map** — color-coded map showing age-adjusted death rates per 100,000 by state
  - Hover over states for detailed information
  - Click a state to view its 10-year trend
  - Color scale from lower (yellow) to higher (red) rates
- **Trend Chart** — line graph showing the last 10 years of data for the selected state
  - Interactive data points with tooltips
  - Updates dynamically based on cause and state selection

## Run Locally

D3 loads CSV via `fetch`, so you must serve over HTTP (not `file://`).

**Option A — Python (built-in on macOS):**

```bash
cd ~/HospitalViz
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

**Option B — Node (if installed):**

```bash
npx http-server -p 8000 --cors -c-1
```

## Data Schema

The CSV file contains the following columns:
- `Year` — year of the data (1999–present)
- `113 Cause Name` — detailed cause name with ICD codes
- `Cause Name` — simplified cause name (e.g., "Unintentional injuries", "Heart disease")
- `State` — state name or "United States" for national data
- `Deaths` — number of deaths
- `Age-adjusted Death Rate` — age-adjusted death rate per 100,000 population (adjusted to 2000 U.S. standard population)

## Interaction

- **Map hover** — shows state name, cause, and death rate
- **Map click** — selects a state and displays its 10-year trend
- **Cause dropdown** — filters map and trend by cause of death
- **Year slider** — updates map to show data for selected year
- **Reset button** — resets to default cause, latest year, and "United States" selection

## Technical Details

- Built with D3.js v7
- Uses TopoJSON for US state boundaries (via `us-atlas`)
- Color scale uses `d3.interpolateYlOrRd` (yellow to red)
- Map projection: `d3.geoAlbersUsa()`
- Data filtering excludes territories (American Samoa, Guam, Northern Mariana Islands, Puerto Rico, U.S. Virgin Islands)

## Deployment

This project is deployed on GitHub Pages at:
[https://xuyangli-12088.github.io/A3-Interactive-Visualization/](https://xuyangli-12088.github.io/A3-Interactive-Visualization/)

To deploy as a static site, upload `index.html` and `NCHS_-_Leading_Causes_of_Death__United_States.csv` to your hosting service.

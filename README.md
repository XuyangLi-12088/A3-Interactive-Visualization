# US Age-Adjusted Death Rates — Interactive Visualization

An interactive visualization of age-adjusted death rates for the 10 leading causes of death in the United States, featuring a choropleth map and trend analysis.

**Deployed At:** [https://xuyangli-12088.github.io/A3-Interactive-Visualization/](https://xuyangli-12088.github.io/A3-Interactive-Visualization/)

## Files
- `index.html` — main application
- `NCHS_-_Leading_Causes_of_Death__United_States.csv` — dataset from NCHS/CDC

## Features

### Interactive Controls
- **Cause selector** — filter by leading cause of death
- **Year slider** — select year from 1999 to present
- **Reset button** — restore default settings

### Visualizations
- **US Choropleth Map** — color-coded map showing age-adjusted death rates per 100,000 by state
  - Hover over states for detailed information (shows current cause and year)
  - Click a state to view its trend chart for all causes
  - Color scale from lower (yellow) to higher (red) rates
  - Map and trend chart displayed side-by-side
- **Trend Chart** — multi-line graph showing all 10 leading causes of death (1999-2017) for the selected state/region
  - Displays all causes simultaneously with different colors
  - Interactive data points with tooltips
  - **Zoom and Pan Controls:**
    - Zoom In/Out buttons for controlled zooming
    - Reset Zoom button to return to default view
    - Mouse wheel scrolling for zoom
    - Click and drag to pan the chart
  - **Cause Highlighting:**
    - Selected cause line is highlighted
    - Other cause lines are dimmed
    - Legend items are highlighted to match selected cause
  - Dynamic label updates to show selected cause name
  - Updates dynamically based on cause and state selection

## Run Locally

```bash
cd ~/HospitalViz
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

## Data Schema

The CSV file contains the following columns:
- `Year` — year of the data (1999–2017)
- `113 Cause Name` — detailed cause name with ICD codes
- `Cause Name` — simplified cause name
- `State` — state name or "United States" for national data
- `Deaths` — number of deaths
- `Age-adjusted Death Rate` — age-adjusted death rate per 100,000 population


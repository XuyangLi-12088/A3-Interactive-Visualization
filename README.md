# Hospital Beds Interactive (D3 v7)

Pure HTML + JavaScript + D3 v7 interactive visualization with dynamic queries and brushing/linking.

## Files
- `index.html` — main app (loads `hospital.csv`)
- `hospital.csv` — sample dataset (ISO dates)

## Run locally (Mac)
D3 loads CSV via `fetch`, so you must serve over HTTP (not `file://`).

Option A — Python (built-in on macOS):

```bash
cd ~/HospitalViz
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

Option B — Node (if installed):

```bash
npx http-server -p 8000 --cors -c-1
```

## Data schema
- `patient_id`: string (anonymized)
- `age`: number 0–100
- `arrival_date`: YYYY-MM-DD
- `departure_date`: YYYY-MM-DD
- `service`: string (e.g., Cardiology, Oncology, Orthopedics, Neurology, General)
- `satisfaction`: number 0–100

`stay_days` is derived in code as `departure - arrival` (days), clamped at 0.

## Interaction
- Age range sliders — dynamic filtering across all views
- Bar click — filter by service (click again to clear)
- Scatter hover — details-on-demand tooltip

## Notes
- X-axis uses 98th percentile of stay length to reduce outlier impact.
- If filters result in no data, views show an empty-state message.

## Deploy
You can host this as a static site (e.g., GitHub Pages). Upload `index.html` and `hospital.csv`.

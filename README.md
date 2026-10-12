# Wi-Fi Mesh Simulator Lite v1.0

A static browser-only multi-AP RSSI heatmap demo for GitHub Pages.

## Features

- Import `width`, `height`, `wall_map`, and optional `forbidden` from floor-plan JSON.
- Multiple draggable APs. No Client, SINR, interference, backhaul, or mesh connection topology.
- For each indoor open cell, strongest-AP RSSI = max(AP transmit power - free-space path loss - per-cell material loss).
- Indoor-region arithmetic average, minimum, and maximum RSSI; optional coverage %.
- Material coefficients, frequency, transmit power, threshold, color range; mask flood-fill with manual correction.
- Export/import Lite projects as JSON; zoom/pan; RSSI probe; remove APs.

## Deployment

Upload `index.html` and `assets/` to the root of the selected GitHub Pages branch (typically `main`). Settings → Pages → Deploy from branch → `main` / `(root)`.

`index.html` loads `assets/app.js?v=lite1.0` and `assets/style.css?v=lite1.0` to limit stale browser cache. No backend or external dependencies.

## Model notes

Each cell is 0.1 m. Walls use illustrative loss coefficients and an approximate ray grid traversal. When there are no APs, RSSI statistics are undefined and display `—`; no fake noise floor is reported. The average/minimum are computed only over the indoor mask and use the strongest AP RSSI at each cell. The model is for visualization, not calibrated radio engineering.

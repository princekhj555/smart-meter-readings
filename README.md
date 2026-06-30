# Smart Meter Dashboard 

[![Netlify Status](https://api.netlify.com/api/v1/badges/d8930941-5a70-4c67-ae6e-5f302585c3be/deploy-status)](https://app.netlify.com/projects/smartmeterinsights/deploys)

APP URL: : https://smartmeterinsights.netlify.app

A lightweight **smart meter reading dashboard** built as a single static HTML page in `index.html`.

It helps you track and analyze imported or fetched smart meter readings, estimate your bill, plan monthly goals, and inspect usage trends.

## Key Features

- **Smart meter data fetching** from the JPDCL consumer details API with CORS proxy fallback.
- **Local storage persistence** for readings and user settings.
- **Daily usage analytics** with gap-aware unit calculation.
- **Tariff slab billing calculator** that computes energy charges and projections.
- **Monthly bill predictor** and **goal planner** for target bill control.
- **Interactive charts** using Chart.js for daily usage, rolling averages, bill trends, and monthly comparisons.
- **Insights panel** with usage highlights, trends, weekend spikes, and projected bill estimates.
- **History table** with CSV import, JSON export, filtering, and export buttons.
- **Dark/light theme toggle**, manual reading entry, and settings modal.

## What is included

- `index.html` — full dashboard application with UI, data handling, charts, and storage logic.
- No build step required — this is a static page that runs entirely in the browser.

## How to use

1. Open `index.html` in your browser.
2. Enter your **consumer ID** when prompted, or in the top input field.
3. Click **Refresh** to fetch readings from the API.
4. The app stores readings and settings in `localStorage` so your history persists between sessions.

## Data Entry and Import

- **Manual add** — use the **Add** button to insert a date and kWh reading.
- **CSV import** — open the import modal and paste CSV lines in `Date,Reading` format or upload a `.csv` file.
- **Export JSON** — click **JSON** to download the current stored reading history.
- **Reset** — clears stored readings, settings, and consumer ID.

## Settings

The settings modal lets you configure:

- Consumer number
- Auto-refresh interval (minutes)
- Currency symbol
- Daily unit target
- Notifications on high daily usage
- Tariff slab definitions (`upto,rate` per line)

Tariff slabs are used by the bill calculator to compute energy charge and projected bill values.

## UI Overview

- **Statistic cards** show current reading, month units, projected bill, average usage, and more.
- **Monthly Bill Predictor** displays current progress and projected month-end bill.
- **Goal Planner** computes remaining units and allowed daily usage for a target bill.
- **Charts** include daily usage, bill progress, rolling average, and monthly comparison.
- **Insights** provide automated commentary on peaks, trends, and consumption patterns.
- **History table** lists all readings, computed daily units, running totals, and running bill values.

## Notes

- The app uses CDN-hosted libraries: Bootstrap 5, Font Awesome, jQuery, Chart.js, and DataTables.
- The API fetch may require network access and CORS proxy support.
- Stored values are saved locally in the browser via `localStorage`.

## Recommended setup

For the best experience, open the page in a browser using a simple local HTTP server, such as:

```sh
python -m http.server 8000
```

Then visit `http://localhost:8000/` and open `index.html`.

## License

This repository includes the dashboard source code under the existing project license.

# CyberSec Dashboard — Claude Instructions

## After every git push
Always remind the user to pull the latest changes to their local Windows folder:

```powershell
cd C:\Users\cosmicv\Documents\CoworkOS\Programming\cybersec-dashboard-git
git pull origin claude/locate-project-files-hjlQx
```

Then reload `index.html` in the browser to see the changes.

## Project structure
- `index.html` — main shell with tab navigation and Excel import/export
- `dashboard.html` — KPI cards and charts (default tab)
- `calendar.html` — operations calendar
- `notes.html` — notes editor
- `riskregister.html` — risk register
- `vendor-tracking.html` — vendor tracking
- `policy-reviews.html` — policy reviews
- `CyberSec_Dashboard_Data.xlsx` — sample data workbook

## Development branch
Always develop on `claude/locate-project-files-hjlQx` unless instructed otherwise.

## Local path (Windows)
`C:\Users\cosmicv\Documents\CoworkOS\Programming\cybersec-dashboard-git`

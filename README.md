# &#x1F6E1;&#xFE0F; CyberSec Operations Dashboard

A unified, browser-based platform for managing cybersecurity operations, risk tracking, vendor oversight, and policy compliance — all from a single dashboard.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat&logo=chartdotjs&logoColor=white)

---

## Overview

The CyberSec Operations Dashboard brings together the core tools a security team needs into one tabbed interface. It runs entirely in the browser with no server or database required — just open `index.html` and go.

### Modules

| Module | File | Description |
|--------|------|-------------|
| **Operations Calendar** | `calendar.html` | Interactive monthly calendar for scheduling and tracking security tasks with recurring event support |
| **Risk Register** | `riskregister.html` | Risk assessment tracker with auto-calculated severity scoring and Chart.js visualizations |
| **Vendor Tracking** | `vendor-tracking.html` | Third-party vendor security review management with risk tier classification |
| **Policy Reviews** | `policy-reviews.html` | Security policy lifecycle tracking with review scheduling and status monitoring |
| **Info & Help** | *(built into dashboard)* | Usage instructions, CSV format references, and quick-reference guides |

---

## Getting Started

### Option 1: Open Locally

1. Download or clone this repository
2. Open `index.html` in any modern browser
3. That's it — no build step, no dependencies to install

### Option 2: GitHub Pages

This project is GitHub Pages-ready out of the box:

1. Push all files to a GitHub repository
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch** → `main` → `/ (root)`
4. Your dashboard will be live at `https://<username>.github.io/<repo-name>/`

---

## Features

### Operations Calendar
- Monthly calendar view with color-coded event indicators
- Add, edit, and delete security operations tasks
- Recurring events (daily, weekly, monthly, yearly)
- Priority levels: Normal, Warning, Critical
- Task table with sorting and owner assignment

### Risk Register
- Add risks with probability and impact scoring (1–10 scale)
- Auto-calculated severity: Critical (≥70), High (≥40), Medium (≥20), Low (<20)
- Multi-select filtering by status, severity, and owner
- Visual charts for severity distribution and risk trends over time
- People management for team assignments

### Vendor Tracking
- Vendor inventory with classification and risk tiers
- Annual security review scheduling and status tracking
- Data access level documentation

### Policy Reviews
- Policy lifecycle management with review frequency tracking
- Owner assignment and approval status
- Upcoming and overdue review monitoring

---

## Data Import & Export

All modules support **CSV import/export** for interoperability with Excel, Google Sheets, and other tools.

### Calendar CSV Format

```csv
Date,Task,Category,Priority,Owner,Notes
2026-03-15,Firewall Review,Network Security,Critical,Network Team,Quarterly review
```

The calendar also accepts event-style CSVs: `Title,Start,End,Color`

### Risk Register CSV Format

```csv
Title,Description,Category,Probability,Impact,Status,Owner,Notes
Data Breach,Unauthorized access to PII,Cybersecurity,7,9,Open,Security Team,Review quarterly
```

### Tips for CSV Import
- Use **UTF-8 encoding** for best compatibility
- Dates should be in **YYYY-MM-DD** format
- Exported files are fully compatible with re-import (round-trip safe)

---

## Compliance Framework Support

The dashboard is designed to support scheduling and tracking across common frameworks:

- **HIPAA Security Rule** — Risk assessments, access reviews, workforce training
- **SOC 2** — Controls across Trust Services Criteria (security, availability, confidentiality)
- **ISO 27001** — ISMS controls, internal audits, corrective actions

Use calendar categories and risk register entries to map tasks to specific framework controls.

---

## Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — No frameworks, no build tools
- **Chart.js** — Risk visualization charts
- **Browser Local Storage** — Data persistence for the Risk Register
- **Iframe Architecture** — Modular design where each tool works independently or embedded in the dashboard

---

## Project Structure

```
├── index.html              # Main dashboard (entry point)
├── calendar.html           # Operations Calendar module
├── riskregister.html       # Risk Register module
├── vendor-tracking.html    # Vendor Tracking module
├── policy-reviews.html     # Policy Reviews module
└── README.md
```

---

## Data Storage

- **Risk Register** — Persists data in browser local storage
- **Calendar** — Session-based; export to CSV before closing to preserve data
- **Vendor Tracking & Policy Reviews** — Check individual module behavior

> **Note:** Clearing browser data will remove locally stored information. Export regularly for backups.

---

## License

This project is provided as-is for cybersecurity operations management. Feel free to adapt it to your organization's needs.

# &#x1F6E1;&#xFE0F; CyberSec Operations Dashboard

A unified, browser-based platform for managing cybersecurity operations, risk tracking, vendor oversight, policy compliance, and operational notes — all from a single dashboard.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat&logo=chartdotjs&logoColor=white)
![SheetJS](https://img.shields.io/badge/SheetJS-007ACC?style=flat&logo=microsoftexcel&logoColor=white)

---

## Overview

The CyberSec Operations Dashboard brings together the core tools a security team needs into one tabbed interface. It runs entirely in the browser with no server or database required — just open `index.html` and go.

All module data can be imported and exported as a **single Excel workbook** (`.xlsx`) with one sheet per module, making it easy to back up, share, and restore your entire dashboard state.

### Modules

| Module | File | Description |
|--------|------|-------------|
| **Notes** | `notes.html` | Rich-text notepad with formatting toolbar for security operations documentation |
| **Operations Calendar** | `calendar.html` | Interactive monthly calendar for scheduling and tracking security tasks with recurring event support |
| **Risk Register** | `riskregister.html` | Risk assessment tracker with auto-calculated severity scoring and Chart.js visualizations |
| **Vendor Tracking** | `vendor-tracking.html` | Third-party vendor security review management with risk tier classification |
| **Policy Reviews** | `policy-reviews.html` | Security policy lifecycle tracking with review scheduling and status monitoring |
| **Info & Help** | *(built into dashboard)* | Usage instructions, data format references, and quick-reference guides |

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

### Notes
- Full rich-text editor with formatting toolbar
- Text styling: bold, italic, underline, strikethrough, headings, font sizes
- Text and highlight color pickers
- Alignment controls (left, center, right)
- Bullet lists, numbered lists, indent/outdent
- Insert horizontal rules, hyperlinks, tables, and checkboxes
- Undo/redo and clear formatting
- Auto-saves to browser local storage with word and character count
- Clear All button with confirmation

### Operations Calendar
- Monthly calendar view with color-coded event indicators
- Add, edit, and delete security operations tasks
- Recurring events (daily, weekly, monthly, yearly)
- Priority levels: Normal, Warning, Critical
- Task table with sorting and owner assignment

### Risk Register
- Add risks with probability and impact scoring (1–10 scale)
- Auto-calculated severity: Critical (≥70), High (≥40), Medium (≥15), Low (<15)
- Multi-select filtering by status, severity, and owner
- Visual charts for severity distribution and risk trends over time
- People management for team assignments

### Vendor Tracking
- Vendor inventory with classification and risk tiers
- Annual security review scheduling and status tracking
- Data access level and integration type documentation
- Contact information and administration portal tracking

### Policy Reviews
- Policy lifecycle management with review frequency tracking
- Owner and approver assignment with version control
- Compliance framework tagging (HIPAA, SOC 2, ISO 27001, etc.)
- Upcoming and overdue review monitoring

---

## Data Import & Export

### Excel Workbook (Primary)

The dashboard includes a **workbook bar** at the top with **Export .xlsx** and **Import .xlsx** buttons that handle all module data in a single Excel file.

- **Export** creates a workbook with one sheet per module: `Notes`, `Calendar`, `Risk Register`, `Vendors`, `Policy Reviews`
- **Import** reads a `.xlsx` file and distributes each sheet's data to the corresponding module
- Files are auto-named with the current date (e.g., `CyberSec_Dashboard_2026-02-16.xlsx`)
- Only sheets present in the file are imported — missing sheets are skipped
- Column headers are auto-sized for readability in Excel

#### Sheet Formats

**Calendar**
```
Date | Task | Category | Priority | Owner | Notes
```

**Risk Register**
```
Title | Description | Category | Probability | Impact | Severity Score | Severity Level | Status | Owner | Mitigation Plan | Notes | Date Created | Date Modified
```

**Vendors**
```
Vendor Name | Vendor Type | Business Purpose | Information Classification | Risk Rating | Information Security Review | Current | Notes | Contact Information | Review Date | ...
```

**Policy Reviews**
```
Policy Name | Policy ID | Description | Policy URL | Category | Compliance Framework | Review Frequency | Status | Last Reviewed | Next Review | Effective Date | Version | Owner | Approver | Notes
```

**Notes**
```
Notes Content
```

### Tips for Data Management
- **Export regularly** to keep offline backups of your operations data
- Use **UTF-8 encoding** for best compatibility if editing in external tools
- Dates should be in **YYYY-MM-DD** format for reliable import
- Click through each tab at least once before exporting to ensure all modules are loaded
- Workbook import distributes data to each module — only sheets with matching names are processed

---

## Compliance Framework Support

The dashboard is designed to support scheduling and tracking across common frameworks:

- **HIPAA Security Rule** — Risk assessments, access reviews, workforce training
- **SOC 2** — Controls across Trust Services Criteria (security, availability, confidentiality)
- **ISO 27001** — ISMS controls, internal audits, corrective actions
- **NIST CSF 2.0** — Identify, Protect, Detect, Respond, Recover functions

Use calendar categories, risk register entries, and policy reviews to map tasks to specific framework controls.

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5 / CSS3 / Vanilla JavaScript** | No frameworks, no build tools required |
| **Chart.js** | Risk severity distribution and trend visualizations |
| **SheetJS (xlsx)** | Excel workbook import/export across all modules |
| **Browser Local Storage** | Data persistence for Notes and Risk Register |
| **Iframe Architecture** | Modular design — each tool works independently or embedded in the dashboard |
| **postMessage API** | Cross-iframe communication for workbook import/export |

---

## Project Structure

```
├── index.html              # Main dashboard with workbook import/export (entry point)
├── notes.html              # Rich-text operations notepad
├── calendar.html           # Operations Calendar module
├── riskregister.html       # Risk Register module
├── vendor-tracking.html    # Vendor Tracking module
├── policy-reviews.html     # Policy Reviews module
└── README.md               # This file
```

All modules are self-contained HTML files with embedded CSS and JavaScript. No external stylesheets or script files are required beyond the CDN-hosted libraries (Chart.js and SheetJS).

---

## Data Storage

| Module | Storage Method |
|--------|---------------|
| **Notes** | Browser local storage (auto-saved) |
| **Risk Register** | Browser local storage |
| **Calendar** | Session-based (use workbook export to preserve) |
| **Vendor Tracking** | Session-based (use workbook export to preserve) |
| **Policy Reviews** | Session-based (use workbook export to preserve) |

> **Note:** Clearing browser data will remove locally stored information. Use the **Export .xlsx** button regularly to back up all module data to a single file.

---

## Browser Compatibility

Tested and works in modern browsers:
- Google Chrome
- Brave
- Microsoft Edge
- Mozilla Firefox
- Safari

---

## License

This project is provided as-is for cybersecurity operations management. Feel free to adapt it to your organization's needs.

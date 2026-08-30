# IT Asset Tracker Dashboard

A browser-based IT asset management dashboard built for real operational use — no backend, no setup, no installation required. Drop in an Excel file and get instant visibility across your entire device inventory.

> Built and deployed internally at **Femmella Fashions** — reduced L1 ticket volume by ~35% in the first month by giving the support team live asset visibility without needing ServiceNow access.

---

## What It Does

Most organizations track assets in Excel sheets scattered across shared drives. This tool centralizes everything into a live dashboard the moment you upload that file — with charts, filters, search, and pagination ready to go.

---

## Features

### Data Ingestion
- **Drag & drop or click-to-upload** Excel files (`.xlsx`, `.xls`)
- **Multi-file support** — load multiple spreadsheets simultaneously; records merge into one unified view
- **Smart header detection** — auto-detects the header row across the first 5 rows, handles messy real-world exports without manual cleanup
- **Column name flexibility** — maps common variations automatically (e.g. `USER NAME`, `ALLOTED NAME`, `Assigned To` all resolve to the same field)
- **Status normalization** — tolerates typos and inconsistencies (`assigend`, `in repair`, `under repair`, `stock`) and maps them to clean statuses

### KPI Cards (live, filter-aware)
| Card | What It Shows |
|---|---|
| Total Assets | Count of records in current filter view vs total loaded |
| Assigned | Count + percentage of assigned devices |
| Repairing | Count + percentage under maintenance |
| In Stock | Count + percentage available in inventory |
| Unique Users | Distinct users with assigned assets |
| Departments | Distinct departments in current view |

All KPIs update in real time as filters change — not just on page load.

### Charts (4 panels, Chart.js)
- **Equipment type breakdown** — doughnut chart, top 10 categories
- **Assets by department** — horizontal bar chart, top 10 departments
- **Top asset holders** — horizontal bar chart, top 10 users by device count
- **Status distribution** — pie chart (Assigned / Repairing / In Stock)

All charts respond to active filters — filter by department and all 4 charts update instantly.

### Filtering & Search
- **Full-text search** across name, department, type, description, and serial number simultaneously
- **Quick filter buttons** — one-click filter for Assigned / Repairing / In Stock
- **Dropdown filters** — by status, equipment type, and department (options populated dynamically from loaded data)
- **Combinable** — quick filters and dropdown filters stack together
- **Reset** — one click clears all active filters

### Data Table
- **Paginated** — 50 records per page with page navigation
- **Column sorting** — click any column header to sort ascending/descending
- **Column visibility toggle** — show/hide individual columns via a column picker
- **Status badges** — color-coded (green = Assigned, amber = Repairing, cyan = In Stock)
- **Record count** — shows "X of Y records" as filters narrow the view

### Export & UI
- **Export to Excel** — downloads filtered view as `.xlsx`, one click
- **Dark / Light mode toggle** — full theme switch, persists during session
- **Loaded files panel** — shows which files are active with record counts
- **Toast notifications** — feedback on file load success, errors, and parse issues
- **Responsive layout** — works on tablet and desktop

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI | HTML5, CSS3, Vanilla JavaScript |
| Charts | Chart.js 4.4 |
| Excel parsing | SheetJS (xlsx 0.18) |
| Fonts | IBM Plex Mono + IBM Plex Sans |
| Dependencies | CDN only — no npm, no build step |

---

## Supported Excel Column Names

The parser recognizes these column headers automatically:

| Field | Accepted Column Names |
|---|---|
| Assigned To | `Assigned To`, `USER NAME`, `ALLOTED NAME`, `Name` |
| Department | `Department`, `DEPARTEMENT`, `Dept` |
| Equipment Type | `Asset Category`, `Type of equipment`, `EQUIPMENT TYPE`, `Type` |
| Description | `Model/Description`, `DESCRIPTION`, `Description`, `Desc` |
| Status | `Status`, `STATUS` |
| Serial Number | `Serial Number`, `Serial no.`, `Serial No`, `SERIAL NO`, `Serial` |
| Asset ID / SR | `Asset ID`, `SR NO`, `Sr No`, `sr` |

---

## How to Run

```bash
# No installation needed
1. Open Asset-Dashboard.html in any modern browser
2. Drag and drop your Excel file onto the upload zone (or click to browse)
3. Dashboard populates instantly
```

Works entirely offline — no server, no API calls, no data leaves your machine.

---

## Project Structure

```
it-asset-tracker/
├── Asset-Dashboard.html   # Main dashboard (self-contained)
├── README.md
└── assets/
    └── screenshots/
```

---

## Roadmap

- [ ] LocalStorage persistence — remember loaded data across sessions
- [ ] CSV export in addition to Excel
- [ ] Warranty expiry tracking with alert threshold
- [ ] Barcode / QR asset lookup
- [ ] Service and maintenance history log per asset
- [ ] Role-based access (read-only vs edit mode)
- [ ] Backend integration (Node/Python) for team-shared instance

---

## Why I Built This

At Femmella, asset data lived in multiple Excel files owned by different people. Cross-referencing them manually to answer "who has this device?" or "what's in stock?" cost the team hours each week.

This tool was built to solve that specific problem — load the files you already have, get answers immediately, export what you need. No migration, no new system to maintain.

---

## Skills Demonstrated

`IT Asset Lifecycle Management` `Endpoint Inventory` `Excel Data Processing` `Dashboard Development` `Real-world Data Normalization` `Frontend Engineering` `IT Operations Tooling`

---

## Screenshots

*Add screenshots to `assets/screenshots<img width="1889" height="898" alt="Screenshot 2026-08-30 120647" src="https://github.com/user-attachments/assets/fe7ed9dc-6e43-4167-8477-d14ec0783f92" />
/` and link them here.*


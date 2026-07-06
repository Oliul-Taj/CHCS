# CHCS — Centralized Healthcare Communication System 🇧🇩

A nationwide, Vercel-deployable centralized healthcare platform for Bangladesh, enabling real-time patient record management, hospital grading, epidemic tracking, and AI-assisted clinical workflows across 64 districts.

---

## Project Structure

```
CHCS/
├── app.py                   # Flask backend — main entry point (Vercel serverless)
├── vercel.json              # Vercel deployment config
├── requirements.txt         # Python dependencies
├── .gitignore
│
├── templates/               # Flask Jinja2 HTML portals
│   ├── landing.html         # Home / landing page
│   ├── patient.html         # Citizen / patient portal
│   ├── hospital.html        # Hospital admin portal
│   ├── doctor.html          # Doctor clinical portal
│   ├── pharmacy.html        # Pharmacy POS terminal
│   └── ministry.html        # Ministry of Health dashboard
│
├── data/                    # Static data files (served via /data/ route)
│   └── bangladesh.geojson   # Bangladesh district boundary polygons
│
├── Files/                   # Project documentation & datasets
│   ├── Datasets/            # CSV data: NIDs, BCs, hospitals, doctors, pharmacies
│   ├── IMG/                 # Screenshots and design images
│   ├── Poster/              # Project posters (PDF)
│   ├── Reports/             # Full project proposal (DOCX/PDF)
│   └── commands/            # Prompt specifications
│
└── docs/                    # Technical documentation
    ├── ARCHITECTURE.md      # System architecture & deployment guide
    └── speech.md            # Investor elevator pitch
```

---

## Portals

| Portal | Route | Users |
|---|---|---|
| Landing | `/` | Public |
| Patient | `/patient` | Citizens |
| Hospital | `/hospital` | Hospital staff |
| Doctor | `/doctor` | Physicians |
| Pharmacy | `/pharmacy` | Dispensary staff |
| Ministry | `/ministry` | Ministry of Health |

---

## Key Features

- **Longitudinal Patient Records** — NID/BC/Passport-based identity, nationwide medical history
- **Smart Identity Resolution** — Accepts bare numbers (no prefix needed), auto-classifies NID vs Birth Certificate vs Passport
- **AI Epidemic Tracking** — Geographic disease cluster detection with Leaflet + Bangladesh GeoJSON map
- **Hospital Grading System** — Dynamic A+/A/B/N/Z tier ratings with audit dashboard
- **RBAC Data Siloing** — Pharmacy endpoint exposes only medicine names, zero clinical data
- **AI Personal Nurse** — Medication schedule, prescription alarms, AI health tips

---

## Running Locally

```bash
pip install -r requirements.txt
python app.py
```

Open: `http://localhost:5000`

---

## Deploying to Vercel

```bash
npm install -g vercel
vercel --prod
```

---

## Test NIDs

| NID | Name | District |
|---|---|---|
| `1988102938475` | Mir Oliul Pasha Taj | Rajshahi |
| `1995827392819` | Sarah Jenkins | Dhaka |
| `1990472839401` | Michael Chen | Rajshahi |
| `2012582910294` | Tasnim Ara (Minor) | Dhaka |

> No prefix needed — just type the number.

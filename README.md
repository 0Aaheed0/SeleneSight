# 🌕 SeleneSight — Lunar Mission Intelligence

**See the Moon. Plan the Mission.**

SeleneSight is an interactive lunar mission analysis platform being developed for the **NASA Space Apps Challenge 2026 — CLPS Lunar Mission Browser**.

Our goal is to help users explore and compare potential lunar landing sites by visualizing sunlight conditions and direct-to-Earth communication opportunities over time.

By combining lunar terrain data, scientific calculations, and interactive visualizations, SeleneSight aims to make complex lunar mission-planning information easier to understand and compare.

> **Project status:** In development  
> **Challenge:** CLPS Lunar Mission Browser  
> **Event:** NASA Space Apps Challenge 2026

---

## 🚀 The Problem

Planning lunar surface missions requires understanding the environmental conditions at potential landing locations.

Two important considerations are:

- **Solar illumination:** How much sunlight reaches a location and how illumination changes over time.
- **Earth visibility:** When Earth is visible above the local horizon, allowing a potential direct communication link.

Lunar terrain, including crater walls and ridges, can affect both conditions. Comparing locations and dates can therefore be challenging without an accessible visualization and analysis tool.

## 💡 Our Solution

SeleneSight aims to provide an interactive environment where users can explore lunar locations, analyze their environmental conditions, and compare potential mission sites.

Instead of simply displaying lunar maps and raw data, we want to help users understand the trade-offs between sunlight availability and communication opportunities.

### ✨ Planned Features

- 🗺️ **Interactive Lunar Explorer** — Explore the lunar south-polar region and select candidate locations.
- ☀️ **Sunlight Analysis** — Visualize solar elevation and illumination conditions over a selected time interval.
- 📡 **Earth Visibility Analysis** — Examine Earth's elevation relative to the local horizon and identify potential communication windows.
- 📊 **Site Comparison Dashboard** — Compare multiple candidate locations using charts and summary metrics.
- 🔄 **Mission Window Analysis** — Identify periods when sunlight and Earth visibility overlap.
- 🧠 **Explainable Site Recommendations** — Explore site trade-offs based on configurable mission priorities.
- 📄 **Mission Report Export** — Generate a shareable summary of selected locations, analysis results, and data sources.

*Features will be implemented progressively. All scientific outputs will be identified according to their data source, calculation method, and validation status.*

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React | Frontend application |
| TypeScript | Type-safe frontend development |
| Vite | Development server and build tooling |
| Tailwind CSS | Responsive interface styling |
| Python | Scientific calculations and data processing |
| FastAPI | Backend API |
| NumPy | Numerical computation |
| SpiceyPy / SPICE | Planetary geometry and ephemeris calculations, where applicable |
| Recharts | Interactive data visualizations |
| CesiumJS / Three.js | Lunar visualization, depending on data and integration feasibility |
| Git & GitHub | Version control and team collaboration |

The final stack may be adjusted as the scientific and visualization requirements become clearer.

## 🛰️ Data Sources

We intend to use authoritative scientific resources where applicable:

- **NASA Scientific Visualization Studio:** Lunar south-pole illumination and shadow resources.
- **NASA/JPL NAIF SPICE:** Planetary geometry, ephemerides, and coordinate transformations.
- **Lunar Orbiter Laser Altimeter (LOLA):** Lunar elevation and terrain data.
- **NASA/JPL Horizons:** Independent ephemeris and geometry cross-checks where supported.

Resources:

- [NASA Space Apps Challenge](https://www.spaceappschallenge.org/)
- [NASA Scientific Visualization Studio](https://svs.gsfc.nasa.gov/)
- [NASA/JPL NAIF](https://naif.jpl.nasa.gov/naif/)
- [Planetary Geodesy Data Archive](https://pgda.gsfc.nasa.gov/)
- [JPL Horizons API](https://ssd-api.jpl.nasa.gov/doc/horizons.html)

All data sources, assumptions, coordinate systems, and calculation limitations will be documented as the project develops.

## 🏗️ Project Architecture

Our planned architecture separates the user interface from the scientific analysis pipeline.

```text
SeleneSight
│
├── Frontend
│   ├── Lunar Explorer
│   ├── Date & Location Controls
│   ├── Sunlight Visualization
│   ├── Earth Visibility Visualization
│   └── Site Comparison Dashboard
│
├── Backend
│   ├── API Endpoints
│   ├── Scientific Calculations
│   ├── Data Processing
│   └── Comparison & Recommendation Logic
│
└── Scientific Data
    ├── Lunar Terrain
    ├── Ephemerides
    └── Candidate Locations
```

## 📁 Repository Structure

Our proposed repository layout:

```text
selenesight/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── charts/
│   │   ├── services/
│   │   └── types/
│   └── package.json
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── api/
│   │   ├── services/
│   │   └── models/
│   └── requirements.txt
│
├── data/
│   ├── sample/
│   └── README.md
│
├── docs/
│   ├── architecture.md
│   ├── methodology.md
│   └── data-sources.md
│
├── .gitignore
├── CONTRIBUTING.md
└── README.md
```

This structure is a starting point and may evolve as implementation progresses.

## 💻 Getting Started

### Prerequisites

Install the following tools before contributing:

- Git
- Node.js and npm
- Python 3.11 or a compatible version
- A code editor such as Visual Studio Code

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/selenesight.git
cd selenesight
```

Replace `YOUR-USERNAME` with the GitHub account or organization that owns the repository.

### 2. Run the Frontend

```bash
cd frontend
npm install
npm run dev
```

Open the local URL displayed by Vite in your terminal.

### 3. Run the Backend

Open another terminal:

```bash
cd backend
python -m venv .venv
```

Activate the virtual environment.

**Windows:**

```powershell
.venv\Scripts\activate
```

**macOS / Linux:**

```bash
source .venv/bin/activate
```

Install dependencies and start the API:

```bash
pip install -r requirements.txt
uvicorn app.main:app --reload
```

The API will usually be available at `http://127.0.0.1:8000`. Interactive API documentation will be available at `/docs` if enabled by the application.

*These commands assume the corresponding files and application entry points have been created.*

## 🤝 Team Collaboration

We welcome contributions from our project team across frontend development, scientific computing, UI/UX design, data analysis, testing, and documentation.

### Workflow

1. Pull the latest changes from `main`.
2. Create a branch for your task.
3. Implement and test your changes.
4. Commit with a descriptive message.
5. Push your branch and open a Pull Request.
6. Review and test changes before merging into `main`.

### Branch Naming

```text
feature/lunar-explorer
feature/sunlight-analysis
feature/earth-visibility
feature/site-comparison
fix/api-integration
docs/project-methodology
```

### Commit Message Examples

```text
feat: add lunar site selection
feat: implement sunlight chart
fix: correct coordinate conversion
docs: document scientific data sources
```

**Team rule:** Avoid committing directly to `main` for ordinary feature development. Use Pull Requests so teammates can review changes and catch integration issues.

## 🔬 Scientific Integrity

SeleneSight is intended as a research and decision-support prototype, not a certified lunar landing system.

We aim to:

- Prefer traceable scientific data over unsupported assumptions.
- Clearly label simulated, sample, and calculated values.
- Document units, reference frames, time systems, and coordinate conventions.
- Validate calculations against appropriate independent references.
- Explain uncertainty and known limitations.
- Avoid presenting preliminary site rankings as definitive mission recommendations.

Sunlight and Earth visibility alone do not establish that a location is safe for landing.

## 🎯 Project Goals

- Make lunar mission conditions easier to explore and compare.
- Visualize sunlight and direct-to-Earth communication opportunities.
- Demonstrate how scientific data can support mission planning.
- Build an accessible, interactive and well-documented prototype.
- Contribute an innovative solution to the NASA Space Apps Challenge.

## 🌌 Our Vision

We believe that complex lunar mission data should be easier to explore, understand, and communicate.

With SeleneSight, we aim to turn lunar environmental data into meaningful visual insights that help people reason about mission-planning trade-offs.

**Explore the Moon. Understand the conditions. Plan with insight.**

---

*Built with curiosity and collaboration for the NASA Space Apps Challenge 2026.*



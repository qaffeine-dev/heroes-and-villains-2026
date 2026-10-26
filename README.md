# Heroes & Villains Showcase — Lineup & Rigging Scheduler

An interactive production scheduler and rigging changeover optimizer for the **Revel: Heroes & Villains** aerial and pole showcase.

## Features

- **Interactive Drag-and-Drop Lineup Reordering:** Easily organize running orders for:
  - Saturday Early Show (3:00 PM)
  - Saturday Late Show (7:00 PM)
  - Sunday Early Show (3:00 PM)
  - Sunday Late Show (7:00 PM)
- **Automated Rigging Engine:**
  - Evaluates the 3 stage rigging points (**Front | Mid | Back**) for each act.
  - Dynamically recalculates where **⚠️ Rigging Changeovers** (Aerial/Floor ↔ Pole) occur as acts are moved.
  - Resolves flexible apparatus points (`Any`) to minimize physical changes.
- **Performer & Cameo Conflict Detection:**
  - Enforces the **1-act buffer rule** for performers who cameo or hold props in other acts (e.g., Andy Pham, Cat Tang, Angel Bonbright, Brian Forbes, Jenn Lee Tanaka).
  - Highlights performer availability mismatches in real time.
- **Show Configurations / Presets:**
  - **Config 1:** Sat Early, Sat Late, Sun Late (3 shows)
  - **Config 2:** Sat Late, Sun Early, Sun Late (3 shows)
  - **Config 3:** All 4 shows

## Local Quickstart

Simply open `index.html` in any web browser:

```bash
# On macOS
open index.html
```

Or start a local development server:

```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

## How GitHub Hosts This Project

This project is a standalone web application designed to run on **GitHub Pages**:

1. Create a repository on GitHub (e.g. `heroes-and-villains-lineup`).
2. Push this directory to your GitHub repository.
3. In GitHub, go to **Settings > Pages**, set the source to `main` branch / root `/`, and click **Save**.
4. GitHub will publish a live URL (e.g. `https://<your-username>.github.io/heroes-and-villains-lineup/`) accessible anywhere on mobile or desktop!

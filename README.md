# Heroes & Villains 2026 — Showcase Lineup & Rigging Scheduler (`heroes-and-villains-2026`)

An interactive production scheduler, conflict validator, and rigging changeover optimizer for the **Revel: Heroes & Villains 2026** aerial and pole showcase (November 14–15, 2026).

- **Live App (GitHub Pages):** [https://qaffeine-dev.github.io/heroes-and-villains-2026/](https://qaffeine-dev.github.io/heroes-and-villains-2026/)
- **Repository:** [https://github.com/qaffeine-dev/heroes-and-villains-2026](https://github.com/qaffeine-dev/heroes-and-villains-2026)

---

## Key Features

### 1. Multi-Show & Single-Show Interactive Scheduling
- **4 Weekend Show Tabs:**
  - **Sat Early (3:00 PM)** — Nov 14
  - **Sat Late (7:00 PM)** — Nov 14
  - **Sun Early (3:00 PM)** — Nov 15
  - **Sun Late (7:00 PM)** — Nov 15
- **📊 All Active Shows (Side-by-Side View):**
  - Compare all 4 shows side by side in **Read-Only** or **Editable** mode.
  - Drag and drop acts within a show or across different shows, add/remove **🎲 Games** breaks, toggle **⏸️ Intermission**, and view aggregate weekend stats (total acts, Solo/Group split, total rigging changeovers, and conflict summaries).
- **🎭 Dress Rehearsal (All 29 Acts — Continuous Single-Day Tab):**
  - Independent single-day continuous lineup containing all **29 acts** (`?tab=dress_rehearsal`).
  - Mirrors the act blocks and rigging transitions of **QT - Flow #2** (`5` total rigging changeovers, `0` performer/cameo buffer conflicts) so the rigging crew and performers can rehearse the exact show flow without affecting the 4-show weekend counts or availability checks.
  - Includes a **↺ Reset QT - Flow #2 Order** button to restore the default 29-act rehearsal order at any time.

### 2. Automated 3-Point Rigging Engine & Manual Shift Controls
- Evaluates the 3 binary stage rigging points (**Front | Mid | Back**) for each act (`Aerial/Floor`, `Pole`, or flexible `Any`).
- Dynamically computes **⚙️ Initial Setup** and **⚠️ Rigging Change** banners as acts are reordered.
- **Interactive Rigging Shift Controls:**
  - When an adjacent act has a flexible `Any` rigging point on the changing line(s), **▲ Move Before Act X** / **▼ Move After Act Y** buttons appear directly on the Rigging Change banner so stage crew can choose whether a changeover happens before or after that act.
  - Clicking any `Any` point badge on an act card toggles its resolved state (`Pole` ↔ `Aerial/Floor`).
- **⚡ Min Rigging Optimizer:**
  - One-click optimizer (`optimizeCurrentPresetRigging()`) that reorders each show to minimize rigging changeovers while preserving opener, continuation, 3-pole grouping, and 1-act performer buffer rules.

### 3. Real-Time Production Conflict & Preference Validation
- **Hard Production Conflicts (⚠️ Red Alerts):**
  - **Performer & Cameo Availability:** Checks both primary performers and cameos/human props (including cameo-specific unavailability such as Elly Z on Sat Early for Act 24).
  - **1-Act Buffer Rule:** Flags back-to-back appearances (`|slot1 - slot2| < 2`) across all performers, cameos, and human props.
  - **Continuation Pairing:** Enforces that **Act 21 (Mama Morton — Selina)** is immediately followed by **Act 15 (Prison Break)** without an intervening break.
  - **Opener Rule:** Enforces that **Act 9 (Team Rocket)** is placed at Slot `#1` whenever scheduled.
  - **Max Shows Limit:** Flags any act scheduled in more than its requested maximum number of weekend shows (`1/1` or `2/2`).
- **Day Preference Flags (🗓️ Purple Notices):**
  - Highlights when an act requesting **1 Show/Day (Separate Days)** is scheduled for 2 shows on the same day, or when an act requesting **2 Shows Same Day** is split across Saturday and Sunday.
- **Hover Availability Cards:**
  - Hovering over any act in the lineup, bench, or side-by-side view displays a floating summary card with performer/cameo details, apparatus, rigging needs, and availability across all 4 shows.

### 4. Built-In Presets, Locking & Shareable Read-Only Links
- **Built-In 4-Show Presets:**
  - **`QT - Flow #2`** — Primary 4-show production schedule (`49` total performances across 4 shows, `15` rigging changes, `2` Games breaks + `1` Intermission per show, `0` hard conflicts).
  - **`QT - Energy Flow`** — Energy-paced 4-show schedule (🔒 locked by default).
  - **`QT - Energy Flow (Min Rigging)`** — Rigging-minimized variant of `QT - Energy Flow`.
  - **`Min Rigging (Honors Prefs)`** & **`QT - Min Rig Honor Prefs`** — Minimum-rigging 4-show schedule (`11` total rigging changes, `0` hard conflicts, `0` day-preference violations).
  - **`Min Rigging (Ignores Prefs)`** — Absolute minimum rigging changes across 4 shows (`10` total rigging changes, `0` hard conflicts).
  - **`Config 3 (All 4 Shows)`** — Baseline 4-show configuration.
- **Preset Locking (`🔒` / `UNLOCK`):**
  - Any preset can be locked (`🔒`) to prevent accidental edits. To unlock a locked preset for editing, type `UNLOCK` into the confirmation prompt.
- **Shareable Read-Only Links (`🔗`):**
  - Clicking **🔗** on any preset encodes the full 4-show lineup, Dress Rehearsal lineup, and custom rigging overrides into a self-contained URL (`?ro=1&p=...`) that opens in **Read-Only Shared View** on any desktop or mobile device.
- **☀️ Light Mode / 🌙 Dark Mode & 🗜️ Compact View:**
  - Switch between Dark Mode and Light Mode (persisted in `localStorage`) or toggle Compact View to fit full show lineups on a single screen.

---

## Local Quickstart

Open [`index.html`](./index.html) directly in any browser:

```bash
# On macOS
open index.html
```

Or serve locally via Python:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

---

## Deployment (`heroes-and-villains-2026`)

This project is deployed as a static single-file web application on **GitHub Pages** from the `main` branch of [`qaffeine-dev/heroes-and-villains-2026`](https://github.com/qaffeine-dev/heroes-and-villains-2026):

```bash
git add index.html README.md
git commit -m "Update scheduler and documentation"
git push origin main
```

# Satellite Orbit Explorer 🛰️

> Built during **Space Career Week 2026** at **GNSS Academy**.

An educational, end-to-end Python simulator that ingests real orbital data, propagates spacecraft trajectories using analytical two-body mechanics, characterizes orbital regimes, and exports interactive 3D visualizations for Google Earth.

---

## 🚀 Key Features
- **OMM JSON Ingestion:** Parses modern CelesTrak Orbit Mean-Elements Message (OMM) JSON files with native ISO-8601 timestamps and 6-digit NORAD IDs.
- **Analytical Two-Body Propagation:** Implements Kepler's Laws, a high-precision Newton-Raphson Kepler Equation solver, IAU-1982 Greenwich Mean Sidereal Time (GMST) Earth rotation transforms, and Vis-Viva velocity profiling.
- **Multi-Regime Analysis:** Compares four distinct orbital classes:
  - **LEO (Sun-Synchronous):** PULSAR-0 (~1.58 hr period, 97.48° inclination)
  - **MEO (Navigation):** GSAT0225 / Galileo 29 (~14.08 hr period, 55.22° inclination)
  - **GEO (Geostationary):** SES-5 (~23.93 hr period, fixed longitude box at 5.0° East)
  - **IGSO (Inclined Geosynchronous):** QZS-2 / Michibiki-2 (~23.94 hr period, asymmetric figure-8 ground track over East Asia)
- **Geospatial & Report Exports:** Generates 2D equirectangular ground track charts, velocity time-series profile curves, static 3D ECEF KML orbits, time-animated KML tracks with date-line wrap protection, and a compiled simulation report.

---

## 📊 Output Artifacts (`/output/`)
The simulation generates and bundles the following assets:
1. `ground_tracks.png` — 2D equirectangular ground track visualization over world coastlines.
2. `velocity_timeseries.png` — Vertically stacked speed profile wave curves across the 24-hour window.
3. `orbit_tracks_ecef.kmit` — Static 3D orbits rendered at calculated geodetic altitudes.
4. `orbit_animation.kml` — Time-animated ground tracks with the Google Earth `gx` extension.
5. `simulation_report.txt` — Compiled Keplerian elements and propagation summary statistics.

---

## 🛠️ Tech Stack & Requirements
- **Language:** Python 3.x
- **Libraries:** `matplotlib`, `requests`, `xml.etree.ElementTree`, `pathlib`, `datetime`

---

## 🏃‍♂️ How to Run
1. Open the notebook in Google Colab using the badge above (or clone this repository).
2. Ensure `orbit_workshop_inputs.zip` (containing `orbital_elements.json`, `data_manifest.json`, and `world_map.txt`) is placed in your input directory.
3. Run the cells sequentially from **Stage 1 to Stage 8**.

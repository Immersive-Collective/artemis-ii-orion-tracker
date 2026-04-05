# Artemis / Orion Tracker

<img width="1838" height="1377" alt="Screenshot 2026-04-05 at 01 56 24" src="https://github.com/user-attachments/assets/f7698f13-9f60-4177-87b8-dd1febd8a2b5" />

Fullscreen Three.js tracker for visualizing NASA Artemis / Orion mission data in a single self-contained web app.

It combines:

- **Projected mission trajectory** from an OEM ephemeris file
- **Live Orion telemetry** from the public AROW-style text feed
- **Earth, Moon, Sun, Milky Way, and Orion model rendering**
- **Camera presets, timeline scrubbing, GUI tuning, and persistence**

---

## What this project is

This project is a browser-based mission viewer built as a single `index.html` app.

The scene renders:

- Earth with day/night shading and cloud layer
- Moon with texture
- Sun with texture
- Orion spacecraft as a GLB model
- Projected Orion path
- Predicted Moon path
- Optional Milky Way skybox
- Optional labels and simplified solar-system context

The UI overlays provide:

- mission status HUD
- camera preset buttons
- projected timeline scrubber
- projected distance / velocity / Moon-distance mini charts
- legend
- top-right `lil-gui` settings panel

---

## Main features

### Data

- Loads **OEM ephemeris** from:
  - `./Artemis_II_OEM_2026_04_03_to_EI.asc`
- Polls **live Orion telemetry** from a public text endpoint
- Interpolates projected state vectors over time
- Computes predicted Moon position for the same timeline

### Scene

- Three.js fullscreen scene
- Earth day/night terminator shader
- Earth clouds layer
- Moon texture
- Sun texture
- Optional Milky Way skybox
- Orion GLB model with Draco support
- Projected Orion and Moon trajectory rendering
- Divider dots along trajectories

### Interaction

- Camera presets:
  - Fit
  - Sun
  - Earth
  - Moon
  - Orion live
  - Orion projected
- Click objects to travel to them
- Timeline scrubber for projected mission position
- Live/projection display mode switching
- Transform controls for Orion model alignment
- Keyboard shortcuts for transform mode switching

### UI / settings

- `lil-gui` settings panel
- Toggle labels for main bodies
- Optional bright star labels
- Optional simplified solar-system markers
- Chart cursor showing current position in the mission timeline
- Overlay panels styled for fullscreen use

### Persistence

- Settings saved in `localStorage`
- Camera state saved in `localStorage`
- Settings and snapshots saved in `IndexedDB`
- Import / export JSON config files

---

## Controls

### Mouse

- Orbit / pan / zoom with `OrbitControls`
- Click Sun / Earth / Moon / Orion to move camera to that object
- Click outside Orion to detach transform controls

### Keyboard

- `R` → transform mode: rotate
- `S` → transform mode: scale
- `B` → toggle Orion transform controls on / off

### Top toolbar

- `Fit`
- `Sun`
- `Earth`
- `Moon`
- `Orion live`
- `Orion projected`
- `Hide trails`
- `Save config`
- `Export config`
- `Import config`
- `Reset`

---

## Project structure

```text
.
├── index.html
├── Artemis_II_OEM_2026_04_03_to_EI.asc
└── assets/
    ├── earth/
    │   └── webp/
    │       ├── 2k_earth_daymap.webp
    │       ├── 2k_earth_nightmap.webp
    │       └── 2k_earth_clouds.webp
    ├── moon/
    │   └── webp/
    │       └── 2k_moon.webp
    ├── sun/
    │   └── 2k_sun.jpg
    ├── milkyway/
    │   └── 8k_stars_milky_way.jpg
    └── orion/
        └── orion-1.glb
```

---

## Dependencies

Loaded via import map / CDN:

- `three`
- `three/addons/controls/OrbitControls.js`
- `three/addons/controls/TransformControls.js`
- `three/addons/loaders/GLTFLoader.js`
- `three/addons/loaders/DRACOLoader.js`
- `lil-gui`

No build step is required.

---

## Running locally

Because the app loads local textures, models, and OEM data with `fetch`, run it through a local web server.

Examples:

### Python

```bash
python3 -m http.server 8000
```

### Node

```bash
npx serve .
```

Then open:

```text
http://localhost:8000/
```

---

## Configuration

Settings include, among others:

- background colors
- panel opacity
- stars density / brightness / size
- Milky Way visibility / exposure / rotation
- trail colors / widths / opacity
- Orion live/projected visibility mode
- camera travel look target
- timeline scrub state
- Orion transform target / mode
- Orion local rotation / offset / scale
- labels and simplified planet visibility

All settings are persisted and can be exported to a timestamped JSON file.

---

## Notes

- In this project, **Orion** refers to the **spacecraft**, not the astronomical constellation.
- The simplified planets are added as **visual context**, not a precision solar-system ephemeris.
- The projected path comes from the OEM file, while the live state is validated before being accepted into the scene.

---

## Roadmap ideas

- more precise planetary ephemerides
- selectable body-centered reference frames
- better star map alignment tools
- mission event markers along the timeline
- playback / pause / speed controls
- screenshot and recording export

---

## License

Add your preferred license here.

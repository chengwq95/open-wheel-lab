# Open Wheel Lab

An interactive guide to Formula 1 cars for people who have never watched a race. Turn the 2026 car around in 3D, take it apart, see how the shape changed since the 1950s, ride a lap of four circuits and try a pit stop. Every technical word comes with a one-line plain explanation.

**Live:** https://open-wheel-lab.pages.dev/ · [opensirius.com](https://opensirius.com/)

---

## Explore

```
Car → Air → Rules → Eras → Circuits → Power → Teams → Compare → Pit stop
```

## Features

- **Interactive 3D car**: rotate and zoom the 2026 car, switch between inspection views, tap any of 14 parts to learn what it does, or take the whole car apart.
- **Make it yours**: try different paint finishes and tyre compounds, switch the wings between Corner and Straight mode, or sit in the driver's seat.
- **Twelve era study models** from 1955 to 2026, each with a spec card, size overlays against the 2026 outline, and a timeline of rule changes and safety milestones.
- **Aerodynamics explained**: wings, the floor, downforce and drag, with diagrams you can play with.
- **Four circuit laps**: Monza, Monaco, Silverstone and Sepang.
  - Watch speed, gear, battery level and wing mode change through the lap.
  - Monza, Monaco and Silverstone use speeds derived from real 2026 qualifying laps.
- **Power unit**: follow energy through the 2026 hybrid (engine, electric motor and battery) and compare peak power across the eras.
- **Eleven 2026 teams**: base, power unit, car, drivers and titles, filterable by power-unit supplier.
- **Head to head**: put the F1 car against a family car, a supercar, an airliner and a fighter jet on acceleration, top speed, braking, cornering, power-to-weight and weight. You can also run an animated launch to 200 km/h.
- **Pit stop game**: lift the car, change four wheels and release it safely, with timing, penalties and feedback. Then compare your stop with a real 2.2-second one.
- **Learning tools**: an exhibit guide, a glossary, a short quiz at the end of each chapter, and a full **Sources** list.
- **English / Chinese** interface switch and **light / dark** themes.
- Works on desktop and phone.

## What to try

1. **Take the 2026 car apart** to see where each system sits and what it does.
2. **Pick an older era** and lay it over the 2026 outline to see how size and shape changed.
3. **Ride a lap of Monaco, then Monza**: one wants grip, the other wants speed.
4. **Run the launch comparison** to see why a supercar can beat an F1 car to 100 km/h but not to 200.
5. **Try a pit stop** and see how close you can get to two seconds.

## Notes built into the exhibits

- The cars are **educational study models**, not engineering drawings. Shapes nobody has measured, and internal parts, are simplified or estimated.
- Lap figures and animations are derived or simulated illustrations, not official telemetry.
- Figures link to the page's **Sources** section. Disputed or unconfirmed values are marked **UNVERIFIED**.
- Team and driver details were last checked in October 2026. The page keeps no race calendar; it links to [formula1.com](https://www.formula1.com/) for the latest schedule and results.

## How to use

No install, no build step. The whole site is one HTML file: open `site/index.html` in any browser, or visit the live site. Drag to turn the car, scroll or pinch to zoom, and tap a part to learn more. Use the chapter links to jump between exhibits.

## Project layout

```
site/          The website (this folder is what gets published)
  index.html   The whole site in one file
  og.jpg       Preview image for social media links
  assets/      three.js files and era poster images
md/            Research notes behind the site: facts, sources and open questions
html/          The same research notes, styled for reading in a browser
json/          Lap data for the circuit exhibit
```

## Deploy

The site is hosted on Cloudflare Pages, connected to this repository:

1. Build command: `exit 0` (there is nothing to build)
2. Build output directory: `site`
3. Production branch: `main`. Every push to `main` goes live in 1–2 minutes

## Credits

- 3D rendering by [three.js](https://threejs.org/) (MIT licence, see `site/assets/THREE-LICENSE.txt`).
- Fonts: Archivo, IBM Plex Sans, JetBrains Mono and Noto Sans SC from Google Fonts.
- Facts and figures are credited one by one in the site's Sources section.

---

This is an unofficial, non-commercial educational fan project, with no affiliation to Formula 1, the FIA or any team. Team names are used as plain text only; no logos or liveries are shown.

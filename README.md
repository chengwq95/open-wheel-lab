# Open Wheel Lab

**An interactive guide to how a Formula 1 car works, written for people who have never watched a race.**

Turn the 2026 car around in 3D, take it apart piece by piece, see how the shape changed over seventy years, ride a lap of four circuits and try to beat the pit crew. Every technical word comes with a one-line plain explanation. Available in **English and Chinese**.

**Visit:** [open-wheel-lab.pages.dev](https://open-wheel-lab.pages.dev/) · [opensirius.com](https://opensirius.com/)

> 一个给 F1 新手的互动网站：360° 看 2026 年赛车、拆开零件、对比不同年代的车型、跑一圈赛道、挑战换胎。中英文双语，手机和电脑都能用。

---

## The tour

The page is laid out as a museum walk, one exhibit after another:

| # | Exhibit | What you can do |
|---|---|---|
| 01 | **The car** | Rotate and zoom the 2026 car, tap any of 14 parts to learn what it does, take the whole car apart, change the paint and tyres, switch the wings between Corner and Straight mode, or sit in the driver's seat. |
| 02 | **Air** | See how wings, the floor, downforce and drag work, with diagrams you can play with. |
| 03 | **Rules** | Why the 2026 cars are smaller and lighter, and what the new rules changed. |
| 04 | **Eras** | Twelve study models from 1955 to 2026, with spec cards, size overlays and side-by-side views, plus a timeline of milestones and safety changes. |
| 05 | **Circuits** | Ride one lap at Monza, Monaco, Silverstone or Sepang and watch speed, gear, battery and wing mode change. |
| 06 | **Power** | Follow energy through the hybrid power unit: engine, electric motor and battery. |
| 07 | **Teams** | All eleven 2026 teams, filterable by power-unit supplier. |
| 08 | **Compare** | Put the F1 car against a family car, a supercar, an airliner and a fighter jet, and run an animated launch race. |
| 09 | **Pit stop** | Lift the car, change four wheels and release it safely — against the clock, with penalties for mistakes. |

Also built in: a glossary, short quizzes at the end of each chapter, a full **Sources** list, and **light / dark** themes.

## Good first things to try

1. **Take the 2026 car apart** and see where each system lives.
2. **Pick an old era** and lay it over the 2026 outline to see how much bigger cars got.
3. **Ride a lap of Monaco, then Monza** — one wants grip, the other wants speed.
4. **Run the launch comparison** to see why a supercar can beat an F1 car to 100 km/h but not to 200.
5. **Try the pit stop** and see how close you get to two seconds.

## How accurate is it?

- The cars are **educational study models**, not engineering drawings. Shapes nobody has measured, and internal parts, are simplified or estimated.
- Lap speeds and animations are **illustrations** worked out from public timing, not official telemetry. Monza, Monaco and Silverstone are based on real 2026 qualifying laps.
- Figures link to the page's **Sources** section. Anything disputed or not yet confirmed is marked **UNVERIFIED**.
- Season details (teams and drivers) were last checked in **October 2026**. For live results and the calendar, see [formula1.com](https://www.formula1.com/).

## What's in this repository

```
site/      The website itself — this folder is what goes live
  index.html   The whole site in one file
  og.jpg       Preview image for social media links
  assets/      3D library files and era poster images
md/        Research notes behind the site (facts, sources, open questions)
html/      The same research notes, formatted for reading in a browser
json/      Lap data used by the circuit exhibit
```

The site has no build step: open `site/index.html` in a browser to view it locally. It is hosted on Cloudflare Pages, and every change to the `main` branch goes live automatically.

## Credits

- 3D rendering by [three.js](https://threejs.org/) (MIT licence — see `site/assets/THREE-LICENSE.txt`).
- Fonts from Google Fonts: Archivo, IBM Plex Sans, JetBrains Mono and Noto Sans SC.
- Facts and figures are credited one by one in the site's Sources section.

---

Open Wheel Lab is an unofficial, non-commercial fan project made for learning. It is not affiliated with Formula 1, the FIA or any team. Team names are used as plain text only; no logos or liveries are shown.

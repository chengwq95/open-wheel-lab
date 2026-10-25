# Open Wheel Research: Handoff

Last updated: 15 Oct 2026 (MYT). Written for whoever (a person or another AI assistant) picks this project up next.

## 1. Project in one paragraph

An interactive HTML website about Formula 1 cars, with 3D visualisation in Three.js, for a general audience who may never have watched F1. Every technical term needs a one-sentence plain-English explanation, with everyday comparisons where helpful. The current 2026-regulation car is the main subject, with extras: eras, circuits, teams, a comparison tool and a pit stop game. The site must run on mid-range laptops and phones, and be safe to publish (no team logos or liveries, correct licences and credits).

## 2. Folder layout

```
open-wheel-lab/
  site/                          The published website (Cloudflare Pages serves this folder)
    index.html                   The whole site in one file (about 460 KB)
    og.jpg                       Social preview image
    assets/                      Three.js, OrbitControls, RoomEnvironment, era poster images
  md/
    HANDOFF.md                   This file
    car_overview_and_history.md  Parts 1-4: car dimensions, exploded-view parts, history, engines
    era_3d_models.md             Free 3D models per era (licences, polygon counts, sizes)
    tracks_teams_pitstop_features.md  Circuits, teams, comparison tool, pit stop game, era spec cards
  html/
    car_overview_and_history.html           Styled copy of the .md of the same name
    tracks_teams_pitstop_features.html      Styled copy of the .md of the same name
  json/
    lap_keyframes.json           Per-corner lap data for the circuit animation
```

The .md files are the source of truth. The .html files are the same content with styling. Each .md ends with its own source list and "Gaps" section. Open those before relying on any figure.

## 3. What is in each research file

### car_overview_and_history.md
- **Part 1, car overview.** 2026 dimensions table (wheelbase 3,400 mm, width 1,900 mm, minimum weight 768 kg), visual differences from 2022-2025 cars, and 3D model resources.
- **Part 2, exploded view.** Per component: location, function, materials, size or weight, fun fact. Components are monocoque, front wing, rear wing and active aero, floor, sidepods and cooling, power unit, gearbox, suspension, brakes, tyres, halo, steering wheel. It also has a suggested separation order and a movement direction for each part.
- **Part 3, history.** 1950 to today by era, with milestones, safety incidents and rule changes, and typical car shape per era.
- **Part 4, engines.** Comparison table from early naturally aspirated engines to the 2026 power units, the 2026 manufacturer and team list, and a step-by-step energy recovery explanation for an animated diagram.

### era_3d_models.md
One table per era (1950s through 2026) of free Sketchfab models. All picks are CC-BY 4.0, so the author must be credited on the site. Each row has link, author, polygon count, GLB size, whether parts are separate, and livery notes. All page URLs returned HTTP 200 when checked on 15 Oct 2026.

Best picks per era:

| Era | Pick | Faces | GLB size |
|---|---|---|---|
| 1950s | Mercedes-Benz W196 (The_Nuke_Remolacha). Weakest era: heavy, needs decimating or a hand-built cigar body | 377k | 84 MB |
| 1960s | 1967 Ferrari 312 (Tyler_Dave) | 78k | 7 MB |
| Late 60s / 70s | 1972 Lotus 72D (Tyler_Dave). JPS tobacco livery, must be removed | 33k | 3 MB |
| Ground effect | 1978 Brabham BT46B fan car (Tyler_Dave) | 126k | 15 MB |
| Turbo | 1983 Brabham BT52 | 151k | 17 MB |
| 1990s | 1990 Benetton B190 (Tyler_Dave) | 67k | 8 MB |
| 2000s V10 | McLaren MP4/19B low-poly (luis.adrian.designs3D) | 41k | 2 MB |
| 2009-2013 V8 | Red Bull RB6 (CasacadeOperations) | 53k | 3 MB |
| 2014-2021 hybrid | 2016 McLaren MP4/31 (Tyler_Dave) | 31k | 3 MB |
| 2022-2025 | F1 2022 Generic V3 (DaniFold, re-uploaded from TheoDevF1). No livery, but 313k faces. Credit both authors and confirm the original is also CC-BY | 313k | 11 MB |
| 2026 | "My take on the 2026 F1 regulations" (MaG80), a fan concept | 206k | 8 MB |

Alternates and the generic fallback are in the file. The Grab3D "Race Car" (CC0, about 1.2 MB, 19.4k triangles, separate wheels and steering wheel) from the first research round is the best lightweight stylised option.

### tracks_teams_pitstop_features.md
1. **Tracks.** 2026 calendar of 23 rounds. Showcase laps for Monza, Monaco and Silverstone. Free geometry sources with licences (bacinger/f1-circuits GeoJSON under MIT is recommended, OpenStreetMap needs ODbL attribution, FastF1 data has terms noted in the file). Includes a GeoJSON to Three.js path recipe with code.
2. **Teams.** 11 teams for 2026 (including Cadillac and Audi): base, power unit supplier, drivers, car name, founding year, championships, plus short summaries.
3. **Comparison tool.** F1 car vs family car (Corolla Hybrid) vs supercar (Ferrari SF90) vs airliner (A320neo) vs fighter jet (F-16): acceleration, top speed, braking, g-forces, power-to-weight.
4. **Pit stop game.** Crew roles (22), step-by-step timeline of a 2.2 s stop, record 1.80 s (McLaren, Qatar 2023), pit lane limit 80 km/h, penalties and tyre rules, suggested scoring windows.
5. **Era timeline slider.** 13 spec cards matching the models in era_3d_models.md.

### json/lap_keyframes.json
Derived, rounded per-corner data for one 2026 qualifying lap each at Monza (Verstappen), Monaco (Antonelli pole) and Silverstone (Leclerc): distance along the lap in metres, position from 0 to 1, entry and apex speed, gear, braking point, and Straight Mode (active aero low-drag) zones. Not official F1 data.

## 4. The website: site/index.html

A single self-contained HTML file. By its markup it already has these sections: machine (3D exhibit), air (aerodynamics), rules, eras, timeline, circuits, power, teams, compare, pitstop, sources. It loads Three.js r128 plus OrbitControls and RoomEnvironment from public CDNs (jsDelivr and cdnjs) and Google Fonts. I found no embedded 3D model data in it, so the cars appear to be built in code. I only skimmed this file when writing the handoff; the research above was not produced from it, so check the prototype against the research files before shipping.

## 5. Things to know before using the data

**Accuracy and sourcing**
- Every figure in the .md files has a source link. Anything unconfirmed or disputed is marked **UNVERIFIED** with the competing values and sources. Search the files for "UNVERIFIED" and decide per item.
- Known UNVERIFIED or weak items: Williams championship count (Formula1.com says 8, Autosport says 9); MP4/4 power (Honda 685 hp vs McLaren "over 700"); tyre diameter changes; energy recovery amounts (MJ); 200-0 km/h braking distances; 2026 cornering g.
- Corner speeds, gears and braking points in the JSON, and the F1 0-100 and 0-200 km/h times, are my own calculations from F1 timing data, not official figures. Labelled "our calculation" in the doc.
- Alpine's power unit status was flagged UNVERIFIED in the first doc. Alpine uses Mercedes power units for 2026 as far as I know, but confirm.
- The 2026 season is in progress (17 of 23 rounds done at last check; Austin, 23-25 Oct, is next). The calendar changed: Bahrain and Saudi Arabia were cancelled, the Bahrain GP moved to Sepang, and Madrid hosts the Spanish GP. Re-check anything season-dependent (standings, results, win counts) before publishing.
- Gaps: weights for the W196, Lotus 72D, BT46B and BT52; top speeds for most cars before 2004; airliner take-off speed; end points of two Silverstone Straight Mode zones (my estimates); Toyota's role at Haas.

**Legal and publishing**
- **Licences:** all picked 3D models are CC-BY 4.0. Put a visible credit (title, author, link, licence) for each model used, and mention if you modified it.
- **Trademarks:** CC-BY covers the modeller's work only. Real team liveries, sponsor logos and the F1 name or logo are third-party trademarks. Retexture to a neutral livery, remove decals (tobacco logos such as Gold Leaf, JPS, Rothmans especially), and remove the Ayrton Senna figure from the Williams FW16 model if used. Use team names in text only, with a clear "unofficial fan site" notice.
- **Timing data:** Formula 1 owns it. Ship only small rounded figures, credit "F1 live timing via FastF1", and stay non-commercial unless F1 gives permission.
- **Track data:** bacinger GeoJSON is MIT; OpenStreetMap needs ODbL attribution.

## 6. Performance guidance (phones and mid-range laptops)
- Target 30-80k triangles per car, and load one car at a time.
- Compress with gltf-transform: `gltf-transform optimize in.glb out.glb --compress draco --texture-compress webp`. Decimate heavy models first (W196, Lotus 49C, 2022 Generic V3).
- If using Draco or WebP in Three.js, add DRACOLoader and make sure the decoder files are served.
- Check in Blender or gltf.report whether each model has separate meshes. The research marks this "likely" or "check", not confirmed. The exploded view needs separate components, so for it you will probably have to build simplified parts using the FIA drawings listed in car_overview_and_history.md.

## 7. Suggested next steps
1. Confirm the licence and original author for each model chosen, then download and inspect them (mesh separation, polygon count, textures).
2. Build or adapt the 2026 exploded-view model; use the order and direction table in Part 2 of car_overview_and_history.md.
3. Wire lap_keyframes.json to circuit paths built from the GeoJSON recipe.
4. Resolve or label the UNVERIFIED items on the page itself.
5. Add a credits and sources page (the prototype already has a "sources" section) with model credits, data credits and an unofficial-site notice.
6. Test on a real mid-range phone for frame rate and load time before adding more eras.

## 8. Notes on working style (from the user)
- The user writes mostly in Chinese; research documents are kept in English so they can be reused directly in the site.
- Keep explanations simple and accurate; metric first, imperial in brackets.
- File naming: lowercase with underscores, no leading numbers; files sorted by type into md, html and json folders.

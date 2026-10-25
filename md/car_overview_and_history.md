# Formula 1 Cars Research Brief

**Purpose:** Reference material for an interactive Three.js website about Formula 1 cars, aimed at a general audience (readers who have never watched F1).  
**Research date:** 14 October 2026 (Asia/Kuala_Lumpur, MYT).  
**Units:** Metric first; imperial in brackets where helpful.  
**Method:** Figures taken from FIA technical materials, Formula1.com, manufacturer/team sites, Pirelli, and selected technical press. Every numeric claim has a source link. Conflicting or soft figures are marked **UNVERIFIED**.

---

## Part 1 — Car overview (2026 regulations)

### What is a Formula 1 car?

A Formula 1 (F1) car is a single-seat racing car built to a strict rule book written by the FIA (Fédération Internationale de l’Automobile — the sport’s governing body). Teams design their own chassis (the main body and structure), while a small number of manufacturers supply the **power unit** (the engine plus electric hybrid system). Tyres come from one supplier, Pirelli. The cars race on purpose-built circuits and some street courses around the world.

### Key dimensions (2026-regulation car)

| Parameter | 2026 value | Everyday comparison / note | Source |
|---|---|---|---|
| Maximum wheelbase | **3,400 mm** (≈ 11.2 ft) | Distance between front and rear axle centres; about 200 mm shorter than 2022–2025 | [FIA 2026 announcement](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [FIA Technical Regulations §C2.3.3](https://api.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_c_technical_-_iss_20_-_2026-08-05.pdf) |
| Maximum width (body) | **1,900 mm** (≈ 6.2 ft) | No bodywork more than 950 mm from the car centreline (tyres/rims excepted) | Same FIA sources |
| Maximum floor width | Reduced by **150 mm** vs previous generation | Helps make the car narrower and less “barge-like” | [FIA announcement](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond) |
| Minimum weight | **768 kg** (≈ 1,693 lb) | About 722 kg car + driver + 46 kg estimated tyre mass; down from 800 kg in 2025 | [FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [Formula1.com](https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP) |
| Wheel rim diameter | **18 inch** | Same rim size as 2022–2025 | [FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [Pirelli](https://press.pirelli.com/pirelli-reveals-2026-f1-tyres-a-fresh-logo-design-and-new-compounds/) |
| Front tyre | **280 mm** wide × **705 mm** overall diameter | ≈ 11.0 in wide × 27.8 in tall; 25 mm narrower than previous | [Mercedes / Pirelli summary](https://www.mercedesamgf1.com/news/what-are-the-tyre-options-for-the-2026-italian-gp); [Pirelli press](https://press.pirelli.com/pirelli-reveals-2026-f1-tyres-a-fresh-logo-design-and-new-compounds/) |
| Rear tyre | **375 mm** wide × **710 mm** overall diameter | ≈ 14.8 in wide × 28.0 in tall; 30 mm narrower than previous | Same |
| Overall car length | **No single FIA maximum published** | Teams size the nose and rear body within other limits (wheelbase, cockpit, bulkheads). Typical modern F1 cars are roughly **5.2–5.6 m** long | **UNVERIFIED** as a hard limit — see FIA §C2 geometry (wheelbase/cockpit) rather than a length cap: [PDF](https://api.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_c_technical_-_iss_20_-_2026-08-05.pdf) |
| Ride height (racing) | **No single published “race ride height”** | Rules define a “Legality Setup” and a wooden/composite **plank** under the floor that limits how low the car can run; 2026 floors are partly flatter so cars need less extreme low setups | [FIA Technical Regulations](https://www.fia.com/sites/default/files/fia_2026_formula_1_technical_regulations_issue_8_-_2024-06-24.pdf); [Formula1.com aero explain](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB) |

**UNVERIFIED — tyre overall diameter change:** Pirelli states overall diameter is **15 mm less at the front and 10 mm less at the rear** versus the previous generation ([Pirelli](https://press.pirelli.com/pirelli-reveals-2026-f1-tyres-a-fresh-logo-design-and-new-compounds/)). A Formula1.com aero article instead says diameter shrinks **15 mm front and 30 mm rear** ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB)). Prefer Pirelli + Mercedes absolute sizes (705 / 710 mm) for the website.

**UNVERIFIED — weight baseline wording:** FIA (June 2024) described 768 kg as “down 30 kg on counterparts from 2022.” Formula1.com (2026) describes the drop as from **800 kg in 2025** to 768 kg. Both can be true across different reference years; cite the year you mean.

### Main visual differences vs 2022–2025 cars

1. **Smaller and lighter.** Shorter wheelbase (−200 mm), narrower body (−100 mm), slimmer tyres, lower minimum weight. The “nimble car” idea is to make cars easier to place in corners and leave more track space for side-by-side racing ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [F1.com](https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP)).

2. **Active aerodynamics instead of DRS-only.** Both front and rear wings have moveable flaps. In **Corner Mode** (also called Z-mode in earlier FIA wording) flaps give high **downforce** (air pushing the car into the track for grip). In **Straight Mode** (X-mode) flaps open like a Venetian blind to cut **drag** (air resistance) so the car goes faster in a straight line. Unlike old **DRS** (Drag Reduction System — a rear-wing flap only the chasing car could open when close enough), Straight Mode is available to every car in designated zones ([FIA](https://www.fia.com/news/f1s-new-era-everything-you-need-know-about-how-fia-making-formula-1-more-competitive-more); [F1.com aero](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB)).

3. **Flatter floor; Venturi tunnels gone.** The deep underfloor tunnels of 2022–2025 (a return of “ground effect”) are removed. The floor is flatter with a larger **diffuser** (the upswept rear underbody that slows and expands airflow). Ground-effect suction is much weaker ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB)).

4. **Simpler rear wing, no beam wing.** The small wing under the main rear wing (beam wing) is banned; endplates are simpler; front wing is narrower with a two-element active flap ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

5. **Wheel covers removed; bargeboards return.** Front wheel arches used in the previous generation are gone. Small **bargeboards** (vertical panels) help pull dirty air from the front wheels inward so the car behind has cleaner air ([F1.com](https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP)).

6. **Power unit looks similar but is electrically much stronger.** Still a 1.6-litre V6 turbo hybrid, but without the MGU-H and with roughly a 50/50 combustion/electric power split (see Part 4).

**Fun fact:** The FIA says the 2026 rules cut downforce by about **30%** and drag by about **55%** versus the previous concept — less “stuck to the road,” more efficient in a straight line ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

### 3D model resources for Three.js

**Goal:** glTF/GLB, ideally separate meshes for an exploded view, public-website-friendly licence (CC0 or CC-BY), **no real team liveries, sponsor logos, or trademarks**.

#### Recommended ready-to-use assets

| Model | Format | Polys / size | Licence | Separate parts? | Author / notes | Download |
|---|---|---|---|---|---|---|
| **Race Car** (stylised open-wheel, apricot body, halo, no sponsors) | GLB, FBX, BLEND, USDZ, OBJ | **19,440** triangles; GLB **≈ 1.1–1.2 MB**; 2K textures | **CC0 1.0** (public domain; commercial OK, no attribution required) | Wheels separate (roll + steer); steering wheel separate; body as cohesive stylised mesh — good starter, not a full mechanical explode | Grab3D / Cozy Boats & Aircraft Kit; published 26 Sep 2026; dims ≈ 1.92 × 5.28 × 1.02 m | Page: [grab3d.com/models/vehicles/race-car](https://grab3d.com/models/vehicles/race-car/) · GLB: [grab3d.com/dl/race-car/race-car.glb](https://grab3d.com/dl/race-car/race-car.glb) · [CC0](https://creativecommons.org/publicdomain/zero/1.0/) |
| **Generic Formula Car (better version)** | Sketchfab downloadable (glTF/GLB via Sketchfab) | **16,564** triangles; 8,630 verts | **CC BY 4.0** (credit author; commercial OK) | Generic formula look; verify mesh groups after import | CarlosCG31 | [Sketchfab](https://sketchfab.com/3d-models/generic-formula-car-better-version-46e0805e009a42f297405d943d6ce22e) · [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| **Formula F211** | Sketchfab downloadable | **36,892** faces | **CC BY 4.0** | Stylised 2011-era formula car; useful for history gallery, not 2026 accuracy | CarlosCG31 | [Sketchfab](https://sketchfab.com/3d-models/formula-f211-cada3b67c43744adadee21adcabc4fc4) |

**Link check (14 Oct 2026 MYT):** Grab3D page and GLB returned HTTP 200 (GLB download size ≈ 1,180,436 bytes). Sketchfab pages returned HTTP 200. CC0/CC-BY licence URLs returned HTTP 200.

#### Not suitable (for this brief)

- **Team-liveried models** (Ferrari, McLaren, Alpine, Aston Martin, etc.) even if CC-BY — trademark/livery risk for a public site.
- **CC BY-NC / NC-SA** models — non-commercial clauses block many public websites.
- **AI “exploded chassis” demos** on generative platforms without a clear reusable licence.
- **3dassets.dev** listed a CC0 open-wheel car on jacks (≈ 4.3k tris, 0.2 MB GLB) during research indexing, but the asset page/CDN returned **HTTP 503 / failed** when verified on 14 Oct 2026 — do not rely on it until the host is stable.

#### Poly Pizza

Search for open-wheel / formula assets on [Poly Pizza](https://poly.pizza) did not surface a clearly licensed generic F1-style car suitable for this project (mostly closed-wheel sports cars). Treat as a secondary hunt later.

#### If you need a true exploded view

No freely licensed, production-quality **component-separated** 2026 F1 car was found. Practical path for Three.js:

1. Start from the **Grab3D CC0** car for overall silhouette, wheels, halo, and steering wheel.
2. Model simplified separate parts (wing, floor, sidepods, monocoque, PU block, gearbox, suspension, brakes, tyres, halo) using official geometry envelopes.
3. Reference drawings (build simplified meshes; do not copy team CAD or liveries):
   - [FIA 2026 Technical Regulations — Section C (Iss. 20)](https://api.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_c_technical_-_iss_20_-_2026-08-05.pdf) — reference volumes, dimensions, legality setup.
   - [FIA 2026 Technical Regulations (Issue 8 overview PDF)](https://www.fia.com/sites/default/files/fia_2026_formula_1_technical_regulations_issue_8_-_2024-06-24.pdf)
   - FIA / Formula 1 public show-car photography and cutaway explainers on Formula1.com (aero and power-unit articles linked throughout this brief).

**Fun fact for the website UI:** A lightweight GLB under ~2 MB loads fast on phones — the Grab3D car already fits that budget.

---

## Part 2 — Exploded view components

Each entry: plain-language name, where it sits, what it does, materials, approx size/weight, fun fact. Sizes/weights that are team-secret or era-dependent are marked **UNVERIFIED**.

### Survival cell / monocoque

**Monocoque** means the outer shell is also the structure — like an eggshell that is both container and strength. In F1 it is the **survival cell**: the carbon-fibre “tub” that surrounds the driver from the pedals to behind the seat.  
It sits in the middle of the car; the nose, sidepods, floor, engine and gearbox bolt to it.  
Modern cells use carbon-fibre composite skins with honeycomb cores (often aluminium honeycomb). Approximate mass of the bare tub is often quoted around **30–40 kg**, but exact figures are team-confidential — **UNVERIFIED** for 2026.  
Lotus introduced a stressed aluminium monocoque (Lotus 25, 1962); McLaren’s MP4/1 (1981) popularised full carbon-fibre cells ([The Engineer F1@75](https://www.theengineer.co.uk/content/in-depth/milestone-breakthroughs-from-75-years-of-f1-innovation)).  
**Fun fact:** Crash tests get tougher each rules cycle — 2026 raises roll-hoop loads and adds a two-stage nose impact structure ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

### Front wing

A multi-element wing hanging under the nose. It creates downforce at the front and carefully steers airflow around the front tyres toward the floor and sidepods.  
2026: narrower (−100 mm), simpler, with a **two-element active flap** that drops in Straight Mode ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).  
Materials: carbon-fibre composite. Width approaches the front track but is regulated; weight is a few kilograms as a complete assembly — **UNVERIFIED** exact kg.  
**Fun fact:** Teams used to adjust front-wing angle only in the garage or pit stop; now the car can change flap angle on the move in legal zones ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB)).

### Rear wing & active aero (replacing DRS)

The tall wing at the back. In Corner Mode it makes strong rear downforce; in Straight Mode its top elements open to cut drag.  
2026 uses a **three-element active rear wing**; the old beam wing underneath is gone ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).  
**How this replaces DRS:** From 2011–2025, DRS let only a chasing car (usually within 1 second) open a rear flap in special zones. Active aero Straight Mode is available to **all** cars in designated straight zones; a separate **Overtake Mode** (extra battery energy when within ~1 second at a detection point) takes over the “help the car behind” role ([F1.com](https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP); [F1.com PU](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).  
Materials: carbon fibre; actuators and sensors inside the endplates/wing body.  
**Fun fact:** Think of Straight Mode as the car temporarily “closing its parachute” so it can sprint down the straight, then opening the parachute again for the next corner.

### Floor & Venturi tunnels

The underside of the car. In 2022–2025, deep **Venturi tunnels** sped up air under the car so pressure dropped and the car was sucked down (**ground effect** — using the road surface like the other half of a wing).  
In 2026 those tunnels are removed; the floor is flatter with a larger rear **diffuser**. Some underbody performance remains, but it is less dominant ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB)).  
A sacrificial **plank** under the floor wears if the car scrapes; too much wear fails scrutineering.  
Materials: carbon sandwich; plank often wood/composite per regulations. Overall floor is roughly car-width × wheelbase-scale — largest aero part by area.  
**Fun fact:** Ground effect was invented for F1 by Lotus in the late 1970s, banned in the 1980s, brought back in 2022, then dialled back again for 2026 ([F1.com history](https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i)).

### Sidepods & cooling

The bodywork beside the cockpit. They house radiators and coolers for the engine, turbo, oil, and hybrid electronics, and shape airflow toward the rear wing and floor.  
Intakes scoop air; outlets dump hot air. Packaging is a big performance differentiator between teams.  
Materials: carbon bodywork over metal heat exchangers. Size: roughly the volume of two large suitcases split left/right — **UNVERIFIED** exact litres.  
**Fun fact:** Sidepod shapes became famous in 2022 (including Mercedes’ extreme “zero sidepod” look); 2026 rules again reshape what teams are allowed to do with wheel wake and in-wash boards ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

### Power unit (ICE, MGU-K, energy store, control electronics)

**Power unit (PU)** = everything that makes propulsion power, not just the petrol engine.  
- **ICE** — Internal Combustion Engine: the 1.6-litre turbocharged V6 that burns fuel.  
- **MGU-K** — Motor Generator Unit–Kinetic: an electric motor/generator on the drivetrain that recovers energy when slowing and can drive the wheels when boosting.  
- **Energy store (ES)** — the battery pack that holds recovered electricity.  
- **Control electronics (CE)** — the computers and power electronics that manage hybrid energy.  
- *(2014–2025 also had an **MGU-H** harvesting turbo/exhaust heat; removed for 2026.)*  

Location: behind the driver, ahead of the gearbox, with radiators in the sidepods and the battery typically low in the chassis.  
2026 headline numbers: ICE ≈ **400 kW**, MGU-K **350 kW**, target ≈ **50/50** split, total peak still **700+ kW** class ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [Mercedes](https://www.mercedesamgf1.com/facts-and-stats-power-unit-regulation-changes); [F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).  
Previous-generation energy store minimum mass was **20 kg** (Mercedes W15/W16 tech sheets) — treat 2026 battery mass as **UNVERIFIED** until a 2026 homologation figure is published for your site.  
**Fun fact:** Removing the complex MGU-H helped attract new manufacturers (Audi, Red Bull Ford, Honda return as full works) ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).

### Gearbox

Sits behind the engine and drives the rear wheels. Modern F1 uses a **semi-automatic sequential** gearbox: the driver pulls paddles on the steering wheel; electro-hydraulic actuators change gears in milliseconds without a traditional H-pattern stick. Eight forward gears + reverse have been standard in the hybrid era ([F1.com regulation history context](https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i); industry explainers).  
The case is often carbon and/or titanium/aluminium; it also acts as a stressed member carrying rear suspension. Complete gearbox mass is typically tens of kilograms — historic carbon cases were reported far lighter than magnesium; treat modern total ≈ **under ~40 kg** as **UNVERIFIED** order-of-magnitude ([historical technical press](https://www.autosport.com/f1/news/f1-2014-tech-gearboxes-under-pressure-5103000/5103000/)).  
**Fun fact:** Ferrari’s 640 (1989) brought paddle-shift semi-auto gearboxes to F1; every car uses the idea today ([The Engineer](https://www.theengineer.co.uk/content/in-depth/milestone-breakthroughs-from-75-years-of-f1-innovation)).

### Suspension (push-rod / pull-rod)

Connects wheels to the chassis so the car can absorb bumps while keeping the aero platform stable.  
**Wishbones** (A-shaped arms) locate each wheel. A **push-rod** is a rod that is compressed when the wheel rises, pushing on an inboard rocker that works the spring/damper. A **pull-rod** is tugged when the wheel rises, pulling a lower rocker. Neither is “always better” — teams pick based on aero packaging ([F1.com explainer](https://www.formula1.com/en/latest/article/explainer-whats-the-difference-between-pull-rod-and-push-rod-suspension.1I3wL4LEL0nQZbKZbx1Dhz); [The Race](https://www.the-race.com/formula-1/mark-hughes-mclarens-unconventional-2022-suspension-explained/)).  
Materials: carbon wishbones, steel/titanium rods, inboard torsion bars and dampers.  
**Fun fact:** In the early 1990s, **active suspension** (computers constantly adjusting ride height) made Williams almost unbeatable — then it was banned ([F1.com](https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i)).

### Brakes (carbon-carbon, brake-by-wire)

F1 uses **carbon-carbon** discs and pads: carbon fibres in a carbon matrix. They work best when very hot (hundreds of °C) and are much lighter than road-car iron discs. A full corner assembly is only on the order of a few kilograms — **UNVERIFIED** exact 2026 masses ([Racecar Engineering / Brembo technical explainers](https://www.racecar-engineering.com/tech-explained/f1-2014-explained-brake-systems/)).  
**Brake-by-wire** on the rear: when the MGU-K harvests energy under braking, computers blend regenerative braking with the hydraulic rear brakes so the driver still feels a predictable pedal ([Autosport](https://www.autosport.com/f1/news/demystifying-formula-1-cars-brake-by-wire-systems/10754436/)). Front brakes remain primarily hydraulic.  
**Fun fact:** Carbon brakes can exceed **1,000 °C** — glowing discs in night races are real, not camera effects ([Brembo](https://www.brembo.com/en/motorsport/formula1/ventilation-holes)).

### Tyres (slicks, intermediates, full wets)

Pirelli supplies every team. Dry tyres are **slicks** — smooth tread for maximum contact on dry asphalt. **Intermediates** (green sidewall marking) have shallow grooves for light rain. **Full wets** (blue) have deep grooves for heavy rain. Dry compounds are labelled Hard (white), Medium (yellow), Soft (red) from a C1–C5 range ([Pirelli](https://press.pirelli.com/pirelli-reveals-2026-f1-tyres-a-fresh-logo-design-and-new-compounds/); [Mercedes race preview](https://www.mercedesamgf1.com/news/what-are-the-tyre-options-for-the-2026-italian-gp)).  
2026 sizes: fronts 280×705 mm, rears 375×710 mm on 18-inch rims (see Part 1). Four tyres ≈ **46 kg** estimated in the FIA minimum-weight split ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).  
**Fun fact:** Slicks returned in 2009 after a decade of grooved dry tyres that had been introduced to slow the cars ([F1.com](https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i)).

### Halo

A titanium “halo” bar above the cockpit that protects the driver’s head from debris and from other cars.  
Structure: Grade 5 titanium (Ti-6Al-4V), about **7 kg**, covered in carbon fairings for aero. Mandatory in F1 since **2018**. Tests include large static loads (order of 125 kN in homologation tests described by manufacturers/FIA coverage) ([Racecar Engineering](https://www.racecar-engineering.com/tech-explained/tech-explained-formula-1-halo/); [FIA safety legacy](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).  
**Fun fact:** Drivers once disliked how it looked; it has since been credited with protecting drivers in several serious accidents (Spa 2018, Bahrain 2020, Silverstone 2022 among widely cited cases) ([Racecar Engineering](https://www.racecar-engineering.com/tech-explained/tech-explained-formula-1-halo/); [FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).

### Steering wheel (main controls)

A detachable, roughly rectangular controller packed with buttons, rotary dials, paddles and a small screen. It is not like a road-car wheel — it is closer to an aircraft sidestick’s button layout.  
Typical controls (labels vary by team; 2026 renames some hybrid modes):  
- **Paddles:** gear up/down; clutch paddle(s) for race starts.  
- **Pit limiter:** caps speed in the pit lane.  
- **Radio / drink / differential / brake-balance** dials.  
- **ERS / Boost:** deploy battery power (2026 “Boost”).  
- **Overtake / Straight Mode related controls** as mapped for 2026 (Straight Mode is often automatic in zones; Overtake Mode is proximity-based) ([F1.com PU article](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).  
- Older wheels had a dedicated **DRS** button; that system is gone for 2026.  
Materials: carbon shell, magnesium/aluminium internals; mass roughly **1–2 kg** class — **UNVERIFIED** exact.  
**Fun fact:** Drivers can swap a spare wheel in seconds if theirs fails — the whole unit unplugs from a quick-release hub.

### Suggested exploded-view separation order

Animate parts outward so nearer parts leave before deeper ones. Directions assume car nose = +Z, up = +Y, right = +X (Three.js common after axis remap).

| Order | Part | Move direction | Distance hint | Why |
|---|---|---|---|---|
| 1 | Front & rear wings | Front wing −Z; rear wing +Z; slight +Y | 0.6–1.2 m | Clear aero “bookends” first |
| 2 | Wheels + tyres | ±X outward | 0.8–1.2 m | Reveal brakes/uprights |
| 3 | Brake discs/calipers | ±X then slight −Y | 0.3–0.5 m | Sit inside wheels |
| 4 | Halo | +Y | 0.5–0.8 m | Clears cockpit |
| 5 | Steering wheel | +Y then −Z (toward camera if cockpit view) | 0.4 m | Detaches from column |
| 6 | Sidepods / engine cover | ±X and +Y | 0.5–1.0 m | Opens flanks |
| 7 | Floor / diffuser | −Y | 0.6–1.0 m | Big underbody plate |
| 8 | Suspension (wishbones, rods) | ±X / ±Z along natural axes | 0.3–0.6 m | After wheels/floor |
| 9 | Radiators / coolers | ±X | 0.4–0.7 m | Inside sidepod volume |
| 10 | Power unit (ICE + turbo + MGU-K) | +Y then +Z slightly | 0.5–0.8 m | Heart of the car |
| 11 | Energy store + CE | −Y (if under seat/tank area) or +Y | 0.3–0.6 m | Avoid overlapping PU |
| 12 | Gearbox | +Z | 0.4–0.7 m | Behind PU |
| 13 | Survival cell (last) | stays / slight +Y | 0–0.3 m | Core reference stays centred |

---

## Part 3 — History (1950–today)

### Timeline by era

| Era | Rule changes & innovations | Notable cars (name + year) | Safety improvements | Typical car shape (simple) |
|---|---|---|---|---|
| **1950–1957** Front-engined classics | First World Championship (1950); varied engine formulae; exotic alcohol fuels early on | Alfa Romeo 158/159 (1950–51); Mercedes W196 (1954) | Very limited by modern standards; fatalities not rare | Long nose, engine ahead of driver, skinny tyres, no wings — like a cigar on wheels |
| **1958–1965** Mid-engine revolution | Mid/rear engine becomes dominant; 1.5 L formula (1961); first Constructors’ Cup (1958) | Cooper T51 (1959); Lotus 25 monocoque (1962) | Gradual chassis strength; still open and fragile | Engine behind driver; stubbier; still no wings |
| **1966–1976** Power, wings, DFV | 3.0 L formula; Cosworth DFV (1967); wings arrive (1968); sponsorship liveries (1968) | Lotus 49 (1967–68); Lotus 72 (1970) | Fire risks drive fuel-cell rules; roll structures improve | Wedge shapes appear; high strut wings then lower body wings |
| **1977–1982** Ground effect + early turbos | Lotus ground-effect tunnels/skirts; Renault turbo (1977); sliding skirts battles | Lotus 78/79 (1977–78); Renault RS01 (1977) | Circuit and car rules scramble to contain cornering speeds | Sidepod skirts seal the floor; very low “wing cars” |
| **1983–1988** Flat bottoms & turbo peak | Flat-bottom ban on tunnels (1983); turbo power peaks then boost/fuel limits; carbon tubs spread | Brabham BT52 (1983); McLaren MP4/4 (1988) | Stronger crash structures; feet behind front axle line (late 80s) | Arrow-shaped flat-bottom cars; huge rear wings; turbo plenums |
| **1989–1993** NA engines & electronics | Turbos banned (1989); semi-auto gearboxes; active suspension / traction aids peak | Ferrari 640 (1989); Williams FW14B (1992) | Higher standards continue; electronics change driving | High-nose experiments; slick tyres; clean “tech” look |
| **1994–1997** Post-Imola reset | Driver aids banned (1994); capacity cut to 3.0 L (1995); major safety programme | Benetton B194 (1994); Williams FW16/18 era | After Imola 1994: tracks altered, plank, higher cockpits, later wheel tethers | Narrower performance; raised cockpit sides appear mid-decade |
| **1998–2008** Grooves, V10 peak, manufacturer boom | Narrow track + grooved tyres (1998); V10 then V8 (2006); tyre wars | McLaren MP4-13 (1998); Ferrari F2002/F2004 | HANS (2003); stronger side structures | Grooved slick-looking tyres; dense aero bits grow through 2000s |
| **2009–2013** Aero strip + KERS | Cleaner bodywork (2009); optional KERS; DRS (2011); Pirelli sole tyre (2011) | Brawn BGP 001 (2009); Red Bull RB6–RB9 | Visor Zylon; continued crash-test rises | Low wide front wing, high rear wing; fewer winglets (then creativity returns) |
| **2014–2021** First turbo-hybrid era | 1.6 V6 turbo hybrid with MGU-K + MGU-H; fuel-flow limits | Mercedes W05–W11 era; Red Bull RB16B (2021) | Halo research → Halo 2018; biometric gloves | Loud hybrid whoosh; complex “bargeboard forests”; halo from 2018 |
| **2022–2025** Ground effect returns | Venturi floors; 18-inch wheels; simplified over-body; cost cap | Red Bull RB18/RB19; later McLaren challengers | Stronger roll-hoop rules after 2022 Silverstone lessons | Chunky sidepods, covered wheels early on, low “skiff” floors |
| **2026–** Nimble hybrid + active aero | Smaller/lighter car; active front+rear wings; no MGU-H; ~50/50 hybrid; 100% advanced sustainable fuel; Overtake Mode | New-generation cars across 11 teams (incl. Cadillac) | Two-stage nose; roll hoop 16 g → 20 g; more intrusion protection | Shorter, narrower, moveable wings, flatter floor, no beam wing |

Sources woven above: [F1.com regulation changes](https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i), [The Engineer F1@75](https://www.theengineer.co.uk/content/in-depth/milestone-breakthroughs-from-75-years-of-f1-innovation), [FIA 2026](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond), [FIA Imola safety legacy](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing), [Lap Ledger eras digest](https://lapledger.org/reference/eras).

### Milestone highlights (for then-vs-now UI)

1. **Mid-engine layout (late 1950s)** — Engine moved behind the driver (Cooper). Better balance; every F1 car since follows this.  
2. **Wings (1968)** — Lotus and others add inverted aerofoils for downforce.  
3. **Ground effect 1970s–early 1980s** — Lotus 78/79 tunnels; banned via flat bottoms (1983).  
4. **Turbo era (1977–1988)** — Renault pioneers; qualifying boost reaches extreme power.  
5. **Active suspension (early 1990s)** — Williams FW14B; banned 1994.  
6. **Semi-auto gearboxes (1989 onward)** — Ferrari 640 paddles.  
7. **Hybrid era (KERS 2009; full PU 2014–2025)** — Electric boost becomes central.  
8. **Halo (2018)** — Titanium head protection.  
9. **Ground effect return (2022–2025)** then **2026 reset** — tunnels out; active aero and bigger electric share in.

### Safety incidents and rule changes (factual, respectful)

Racing is dangerous; the sport’s modern record is far safer because of lessons paid for by earlier generations. Summaries below avoid graphic detail.

- **Imola 1994 (San Marino GP):** Weekend tragedies involving Roland Ratzenberger and Ayrton Senna shocked the sport. The FIA accelerated circuit changes, car performance cuts (including floor plank), cockpit protection, and a long-term safety research culture ([FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).  
- **1990s–2000s incremental rules:** Higher cockpit sides, wheel tethers (from 1999, later multi-tether), extractable seats, stricter helmets, **HANS** head-and-neck support mandatory in F1 from 2003 ([FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).  
- **Felipe Massa (Hungary 2009) and related debris risks:** Led to stronger helmet/visor protection (Zylon panel era) ([FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).  
- **Jules Bianchi (Japan 2014):** Ultimately fatal injuries after a wet-weather accident involving a recovery vehicle. The **Virtual Safety Car** (2015) and further cockpit intrusion work followed; closed-cockpit research contributed to the Halo path ([FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing)).  
- **Halo era incidents (2018 onward):** Multiple crashes where the Halo was credited with reducing head injury risk (e.g. Spa 2018, Bahrain 2020, Silverstone 2022). Grosjean’s 2020 Bahrain barrier crash also triggered a broad safety review of barriers, clothing, and rescue ([FIA](https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing); [Racecar Engineering](https://www.racecar-engineering.com/tech-explained/tech-explained-formula-1-halo/)).  
- **2026:** Stronger roll-hoop test (16 g → 20 g), two-stage front impact structure, increased side intrusion protection ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

---

## Part 4 — Engines & power units

### Comparison across eras

| Years | Displacement | Cylinders & layout | Turbo? | Max RPM | Approx power | Hybrid components | Fuel rules | Notable manufacturers | Sound character |
|---|---|---|---|---|---|---|---|---|---|
| 1950–1951 | 1.5 L s/c or 4.5 L NA | Straight-8 / V12 etc. | Supercharged option | ~8,500 | ~350–425 hp | None | Exotic blends early | Alfa Romeo, Ferrari | Harsh, mechanical scream of early GP engines |
| 1954–1960 | 2.5 L NA | Various I4–V8 | No (s/c abandoned) | ~8,000 | ~250–290 hp | None | Pump-style fuels later mandated | Mercedes, Ferrari, Maserati | Lower, classic race growl |
| 1961–1965 | 1.5 L NA | V6/V8/flat-8… | No | up to ~12,000 | ~150–225 hp | None | Strict 1.5 L | Ferrari, Coventry Climax, BRM | High-rev buzz, less torque |
| 1966–1976 | 3.0 L NA (or 1.5 L FI) | V8/V12/flat-12 | Rare early FI | ~10–12.5k | ~400–500 hp | None | — | Cosworth DFV, Ferrari, Ford | The classic DFV howl |
| 1977–1988 turbo peak | 1.5 L turbo (or 3.0 NA) | I4/V6 turbos | **Yes** | ~11–12k | Race ~600–900; quali **1,000–1,400+ hp** **UNVERIFIED** exact peaks vary by source | None | Fuel/boost limits late 80s | Renault, BMW, Honda, Ferrari, Porsche TAG | Spooling whoosh + sharp hit on boost |
| 1989–1994 | 3.5 L NA | V8/V10/V12 | No | ~12–14.5k | ~600–780 hp | None | Turbos banned | Honda, Renault, Ferrari, Ford | Pure high-rev scream returns |
| 1995–2005 | 3.0 L NA | **V10** (mandated from 2000) | No | up to ~19,000 | ~700–980 hp | None | Capacity cut after 1994 | Ferrari, Mercedes Illmor, BMW, Renault, Cosworth | Ear-splitting V10 shriek (fan favourite) |
| 2006–2013 | 2.4 L NA | **V8** | No | 20k → 19k → **18,000** limit | ~720–780 hp | Optional **KERS** from 2009 (~60 kW) | Rev limits freeze development | Mercedes, Ferrari, Renault, Cosworth | Still loud, slightly deeper than V10 |
| 2014–2025 | 1.6 L | **V6** turbo hybrid | **Yes** | 15,000 limit (often ~12k in race maps) | ~850–1,050 hp combined | **MGU-K** (120 kW) + **MGU-H** + ES + CE | Fuel mass/flow caps; rising sustainable blend % late in era | Mercedes, Ferrari, Renault/Alpine, Honda | Quieter turbo growl + electric whine |
| **2026–** | 1.6 L | **V6** turbo hybrid | **Yes** | 15,000 class (regulatory limit family) | Combined still **700+ kW / ~1,000 hp** class; ICE ≈400 kW + MGU-K 350 kW | **MGU-K only** (no MGU-H); bigger ES deployment | **100% advanced sustainable fuel**; energy-based fuel flow (~75 kg/h class) | Mercedes, Ferrari, Honda, Audi, Red Bull Ford | Similar turbo note; more electric presence when harvesting/boosting |

Era table synthesised from: [Lap Ledger engine formulae](https://lapledger.org/reference/eras), [The Engineer](https://www.theengineer.co.uk/content/in-depth/milestone-breakthroughs-from-75-years-of-f1-innovation), [FIA 2026](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond), [Mercedes PU comparison](https://www.mercedesamgf1.com/facts-and-stats-power-unit-regulation-changes), [F1.com PU explain](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd). Qualifying turbo horsepower figures are historically contested — mark on-site as approximate.

**UNVERIFIED — energy recovery per lap (2026):** FIA launch material cited about **8.5 MJ** recuperable per lap; Mercedes comparison table lists **9 MJ** recovery vs 2 MJ previously ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [Mercedes](https://www.mercedesamgf1.com/facts-and-stats-power-unit-regulation-changes)). Show both if animating a number.

### 2026 power unit manufacturers and teams supplied

Five PU manufacturers supply the 2026 grid ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd); [Motorsport.com](https://www.motorsport.com/f1/news/every-f1-teams-engine-supplier-for-the-2026-season/10789027/); [Honda](https://global.honda/en/F1/features/f1-explained/06/)):

| Power unit | Teams supplied (2026) |
|---|---|
| **Mercedes** | Mercedes, McLaren, Williams, Alpine |
| **Ferrari** | Ferrari, Haas, Cadillac |
| **Honda** | Aston Martin |
| **Audi** | Audi (works, ex-Sauber) |
| **Red Bull Powertrains / Ford** | Red Bull, Racing Bulls |

**UNVERIFIED / historical note:** When the FIA showcased regulations in June 2024, it listed **six** committed manufacturers including **Alpine** as a PU maker ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)). By the 2026 season, Alpine races as a **Mercedes customer** instead ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)). Prefer the season supply table for the website; mention Alpine’s abandoned works PU only as history.

Cadillac uses Ferrari PUs initially; GM’s own PU is planned later (Honda/Motorsport reporting points to a post-2026 introduction — confirm before stating a year on-site) ([Honda](https://global.honda/en/F1/features/f1-explained/06/); [Motorsport.com](https://www.motorsport.com/f1/news/every-f1-teams-engine-supplier-for-the-2026-season/10789027/)).

### Energy recovery — plain-language steps (for an animated diagram)

**What “hybrid” means here:** The car has a petrol engine **and** an electric motor that can charge a battery and also push the car.

1. **Driver brakes or lifts.** The car must lose speed; that energy used to become heat in the brakes.  
2. **MGU-K acts as a generator.** Instead of wasting all that energy, the MGU-K turns motion into electricity (regenerative braking), while brake-by-wire keeps the pedal feel consistent.  
3. **Electricity flows into the energy store.** The battery (energy store) fills up within rules limits for the lap.  
4. **Extra harvesting tricks (2026).** Systems can also harvest on part-throttle, when the driver lifts early (“lift and coast”), or via limited “super clipping” near the end of a straight ([F1.com](https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP)).  
5. **Driver (or map) deploys Boost.** The MGU-K switches to motor mode and adds up to **350 kW** at the drivetrain — like a temporary second engine ([Mercedes](https://www.mercedesamgf1.com/facts-and-stats-power-unit-regulation-changes)).  
6. **Overtake Mode (if eligible).** When close enough at the detection point, the following car may get **+0.5 MJ** and a stronger deployment profile next lap — the sporting replacement for old DRS assistance ([F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).  
7. **What changed vs 2014–2025.** The old **MGU-H** also made electricity from turbo/exhaust heat. It is gone; almost all electrical strategy now centres on the bigger MGU-K and battery ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)).

**Everyday comparison:** Like a city bus that charges when slowing for a stop, then uses that charge to pull away — except an F1 MGU-K is many times more powerful and the strategy is fought over every corner.

### 2026 fuel in one paragraph

Cars must run **advanced sustainable fuel**: molecules from sources such as non-food biomass, municipal waste, or sustainable carbon capture — certified so no *new fossil* carbon enters the fuel. It is designed as a **drop-in** petrol substitute (works in a petrol engine without a special new combustion architecture) ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond); [F1.com](https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd)).

---

## Full source list

Primary / preferred:

1. https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond  
2. https://www.fia.com/news/f1s-new-era-everything-you-need-know-about-how-fia-making-formula-1-more-competitive-more  
3. https://api.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_c_technical_-_iss_20_-_2026-08-05.pdf  
4. https://www.fia.com/sites/default/files/fia_2026_formula_1_technical_regulations_issue_8_-_2024-06-24.pdf  
5. https://www.fia.com/news/legacy-safety-how-fia-responded-tragedy-imola-1994-and-launched-drive-safer-racing  
6. https://www.formula1.com/en/latest/article/from-smaller-cars-to-a-bigger-budget-cap-12-rule-changes-you-need-to-know-about-in.56uUTFhB0z5j3iZfhC0rGP  
7. https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-aerodynamics.7IAt0auc32UkCEFE5ypkTB  
8. https://www.formula1.com/en/latest/article/2026-regulations-explained-all-you-need-to-know-about-f1s-new-power-units.14jfv7a36905uDJDdNyfQd  
9. https://www.formula1.com/en/latest/article/the-key-regulation-changes-in-f1-history-and-the-teams-that-nailed-them.2iq8c5E6S1HOffT5PBLl6i  
10. https://www.formula1.com/en/latest/article/explainer-whats-the-difference-between-pull-rod-and-push-rod-suspension.1I3wL4LEL0nQZbKZbx1Dhz  
11. https://press.pirelli.com/pirelli-reveals-2026-f1-tyres-a-fresh-logo-design-and-new-compounds/  
12. https://www.mercedesamgf1.com/facts-and-stats-power-unit-regulation-changes  
13. https://www.mercedesamgf1.com/news/what-are-the-tyre-options-for-the-2026-italian-gp  
14. https://www.motorsport.com/f1/news/every-f1-teams-engine-supplier-for-the-2026-season/10789027/  
15. https://global.honda/en/F1/features/f1-explained/06/  
16. https://www.the-race.com/formula-1/mark-hughes-mclarens-unconventional-2022-suspension-explained/  
17. https://www.racecar-engineering.com/tech-explained/tech-explained-formula-1-halo/  
18. https://www.racecar-engineering.com/tech-explained/f1-2014-explained-brake-systems/  
19. https://www.autosport.com/f1/news/demystifying-formula-1-cars-brake-by-wire-systems/10754436/  
20. https://www.brembo.com/en/motorsport/formula1/ventilation-holes  
21. https://www.theengineer.co.uk/content/in-depth/milestone-breakthroughs-from-75-years-of-f1-innovation  
22. https://lapledger.org/reference/eras  
23. https://grab3d.com/models/vehicles/race-car/  
24. https://grab3d.com/dl/race-car/race-car.glb  
25. https://sketchfab.com/3d-models/generic-formula-car-better-version-46e0805e009a42f297405d943d6ce22e  
26. https://sketchfab.com/3d-models/formula-f211-cada3b67c43744adadee21adcabc4fc4  
27. https://creativecommons.org/publicdomain/zero/1.0/  
28. https://creativecommons.org/licenses/by/4.0/

Link resolution: URLs above returned HTTP 200 when checked on 14 Oct 2026 MYT (Grab3D GLB included). Do not cite 3dassets.dev until it serves reliably again.

---

## Gaps & open questions

1. **Overall length** — No single FIA maximum found; need team-by-team published lengths or a modelled envelope from Appendix reference volumes.  
2. **Race ride height** — Only legality/plank framework is public; live ride heights are setup secrets.  
3. **True exploded 2026 GLB** — No free CC0/CC-BY component-separated accurate 2026 car found; plan custom modelling.  
4. **Component masses** — Monocoque, gearbox, battery, wing assemblies: many public numbers are old or unofficial.  
5. **Energy recovery MJ** — FIA 8.5 MJ vs Mercedes 9 MJ messaging; confirm from latest Sporting/Technical issue before locking UI copy.  
6. **Rear tyre diameter delta** — Pirelli (−10 mm) vs one F1.com article (−30 mm); prefer Pirelli absolute 710 mm.  
7. **GM/Cadillac own PU year** — Reported as after initial Ferrari supply; verify exact season before stating.  
8. **Alpine PU history** — 2024 FIA “six manufacturers” list vs 2026 Mercedes customer reality.  
9. **Steering-wheel 2026 labels** — Team-specific; photograph a show car or official onboard for accurate button map.  
10. **Sound samples** — No licensed audio captured in this brief; needed for Part 4 “sound character” media.  
11. **Poly count of Sketchfab downloads after Draco/glTF export** — API face counts are guides; re-measure in Blender after download.  
12. **Trademark review** — Even generic models should avoid Ferrari/Honda/etc. badge shapes if the site is commercial.

---

*End of research brief. Prepared for Three.js educational use; not an official FIA document.*

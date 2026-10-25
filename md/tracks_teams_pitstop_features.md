# F1 Features Research: Tracks, Teams, Comparisons, Pit Stops and Eras

**Purpose:** Content and data for five interactive features on a Three.js website about Formula 1 (F1) cars, written for people who have never watched a race.
**Research date:** 15 October 2026 (Asia/Kuala_Lumpur, MYT). The 2026 season had run 17 of its 23 rounds on this date.
**Companion files:** [f1_research.md](f1_research.md) (car, parts, history, engines) and [f1_era_models.md](f1_era_models.md) (free 3D models by era). Lap data for the animation is in [f1_lap_keyframes.json](f1_lap_keyframes.json).
**Units:** Metric first, imperial in brackets.
**Rules used here:** every number has a source link next to it. When good sources disagree, the figure is marked **UNVERIFIED** and each value is listed with its source. Numbers we worked out ourselves (from telemetry or simple physics) are labelled **our calculation** so you can tell them apart from published figures.

---

## A few words you will meet everywhere

- **Grand Prix (GP):** French for "big prize". It means one race weekend in one place.
- **Circuit / track:** the closed road the cars race on. Some are purpose-built; some are city streets closed for the weekend (a **street circuit**).
- **Lap:** one full trip around the circuit.
- **Corner / turn (T1, T2...):** each bend has an official number, counted from the start line. "T4" means Turn 4.
- **Apex:** the inside point of a corner, where the car is closest to the inner edge and usually at its slowest.
- **Braking point:** the spot where the driver first hits the brake pedal before a corner.
- **Gear:** F1 cars have 8 forward gears. 1st is for the slowest hairpins, 8th for top speed.
- **Downforce:** air pushing the car down onto the road, like an upside-down aeroplane wing. More downforce means more grip in corners.
- **Drag:** air resistance that holds the car back on straights, like wind pushing on your hand out of a car window.
- **Active aero (2026):** the front and rear wings can change angle while driving. **Corner Mode** = wings closed for downforce. **Straight Mode** = wings opened flat to cut drag on straights.
- **Overtake Mode (2026):** an extra burst of electric energy for a driver who is within 1 second of the car ahead at a set point on the lap. It replaced the old DRS overtaking flap.
- **g (g-force):** a measure of push on your body. 1 g is your normal weight. 4 g feels like four times your weight pressing on you.
- **Telemetry:** live data the car sends back: speed, gear, throttle, brake and more.
- **Pole position:** first place on the starting grid, earned by being fastest in qualifying (the timed session before the race).

---

## 1. TRACKS

### 1.1 The 2026 calendar

The 2026 World Championship has **23 rounds**. Two April races (Bahrain and Saudi Arabia) were cancelled because of the war in the Middle East ([The Guardian](https://www.theguardian.com/sport/2026/mar/14/formula-one-cancel-bahrain-saudi-arabia-grand-prix-war-middle-east)). The Bahrain Grand Prix was later moved to Malaysia's Sepang circuit for 2 to 4 October, bringing the calendar back to 23 races ([FIA](https://www.fia.com/news/fia-and-fom-confirm-malaysia-will-join-2026-calendar-host-venue-bahrain-grand-prix); [Formula1.com](https://www.formula1.com/en/latest/article/formula-1-and-fia-confirm-malaysia-will-join-2026-calendar-as-host-venue-for-the-bahrain-grand-prix.6lL7vjFEM2VVynRHvg1TCf)). Madrid's new **Madring** street-style circuit hosts the Spanish GP. Barcelona keeps a separate "Barcelona-Catalunya GP" ([Formula1.com calendar](https://www.formula1.com/en/racing/2026)).

How to read the table:
- **Length, laps, lap record** come from each race's Formula1.com page (link in the last column). The **lap record** is the fastest lap ever set *during a race* on today's layout, not the faster one-lap qualifying times.
- **Corners** is the number of numbered turns in the official F1 timing data, read with the [FastF1](https://docs.fastf1.dev/) library (`Session.get_circuit_info()`, which uses the MultiViewer circuit API). For the six rounds not yet raced in 2026 we used each venue's 2025 data. We cross-checked the counts that Formula1.com states in text: Miami 19 ([F1.com](https://www.formula1.com/en/racing/2026/miami)), Las Vegas 17 ([F1.com](https://www.formula1.com/en/racing/2026/las-vegas)), Madring 22 ([F1.com](https://www.formula1.com/en/racing/2026/spain)) and Sepang 15 ([F1.com circuit guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-sepang-international-circuit.2KTLvyxBXmwVftSJxmYeZ2)). The Hungaroring has 14 numbered turns, and FastF1 also lists two extra lettered markers there. FastF1 could not load circuit info for Madrid or Sepang, so those two counts come from Formula1.com.
- Rounds 1 to 17 had been raced by 15 Oct 2026. Rounds 18 to 23 (Austin to Abu Dhabi) are still to come.

| Rd | Grand Prix | Circuit | Country | Length km (mi) | Laps | Corners | Lap record (holder, year) | Source |
|---|---|---|---|---|---|---|---|---|
| 1 | Australian GP | Albert Park Circuit, Melbourne | Australia | 5.278 (3.28 mi) | 58 | 14 | 1:19.813 (Charles Leclerc, 2024) | [F1.com](https://www.formula1.com/en/racing/2026/australia) |
| 2 | Chinese GP | Shanghai International Circuit | China | 5.451 (3.39 mi) | 56 | 16 | 1:32.238 (Michael Schumacher, 2004) | [F1.com](https://www.formula1.com/en/racing/2026/china) |
| 3 | Japanese GP | Suzuka Circuit | Japan | 5.807 (3.61 mi) | 53 | 18 | 1:30.965 (Kimi Antonelli, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/japan) |
| 4 | Miami GP | Miami International Autodrome | USA | 5.412 (3.36 mi) | 57 | 19 | 1:29.708 (Max Verstappen, 2023) | [F1.com](https://www.formula1.com/en/racing/2026/miami) |
| 5 | Canadian GP | Circuit Gilles-Villeneuve, Montréal | Canada | 4.361 (2.71 mi) | 70 | 14 | 1:13.078 (Valtteri Bottas, 2019) | [F1.com](https://www.formula1.com/en/racing/2026/canada) |
| 6 | Monaco GP | Circuit de Monaco | Monaco | 3.337 (2.07 mi) | 78 | 19 | 1:12.909 (Lewis Hamilton, 2021) | [F1.com](https://www.formula1.com/en/racing/2026/monaco) |
| 7 | Barcelona-Catalunya GP | Circuit de Barcelona-Catalunya | Spain | 4.657 (2.89 mi) | 66 | 14 | 1:15.743 (Oscar Piastri, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/barcelona-catalunya) |
| 8 | Austrian GP | Red Bull Ring, Spielberg | Austria | 4.326 (2.69 mi) | 71 | 10 | 1:07.924 (Oscar Piastri, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/austria) |
| 9 | British GP | Silverstone Circuit | United Kingdom | 5.891 (3.66 mi) | 52 | 18 | 1:27.097 (Max Verstappen, 2020) | [F1.com](https://www.formula1.com/en/racing/2026/great-britain) |
| 10 | Belgian GP | Circuit de Spa-Francorchamps | Belgium | 7.004 (4.35 mi) | 44 | 19 | 1:44.701 (Sergio Pérez, 2024) | [F1.com](https://www.formula1.com/en/racing/2026/belgium) |
| 11 | Hungarian GP | Hungaroring, Budapest | Hungary | 4.381 (2.72 mi) | 70 | 14 | 1:16.627 (Lewis Hamilton, 2020) | [F1.com](https://www.formula1.com/en/racing/2026/hungary) |
| 12 | Dutch GP | Circuit Zandvoort | Netherlands | 4.259 (2.65 mi) | 72 | 14 | 1:11.097 (Lewis Hamilton, 2021) | [F1.com](https://www.formula1.com/en/racing/2026/netherlands) |
| 13 | Italian GP | Autodromo Nazionale Monza | Italy | 5.793 (3.60 mi) | 53 | 11 | 1:20.901 (Lando Norris, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/italy) |
| 14 | Spanish GP | Madring, Madrid (new 2026) | Spain | 5.414 (3.36 mi) | 57 | 22 | 1:35.587 (George Russell, 2026) | [F1.com](https://www.formula1.com/en/racing/2026/spain) |
| 15 | Azerbaijan GP | Baku City Circuit | Azerbaijan | 6.003 (3.73 mi) | 51 | 20 | 1:43.009 (Charles Leclerc, 2019) | [F1.com](https://www.formula1.com/en/racing/2026/azerbaijan) |
| 16 | Bahrain GP *held in Malaysia* | Sepang International Circuit | Malaysia | 5.543 (3.44 mi) | 56 | 15 | 1:34.080 (Sebastian Vettel, 2017) | [F1.com](https://www.formula1.com/en/racing/2026/bahrain) |
| 17 | Singapore GP | Marina Bay Street Circuit | Singapore | 4.927 (3.06 mi) | 62 | 19 | 1:33.808 (Lewis Hamilton, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/singapore) |
| 18 | United States GP | Circuit of the Americas, Austin | USA | 5.513 (3.43 mi) | 56 | 20 | 1:36.169 (Charles Leclerc, 2019) | [F1.com](https://www.formula1.com/en/racing/2026/united-states) |
| 19 | Mexico City GP | Autódromo Hermanos Rodríguez | Mexico | 4.304 (2.67 mi) | 71 | 17 | 1:17.774 (Valtteri Bottas, 2021) | [F1.com](https://www.formula1.com/en/racing/2026/mexico) |
| 20 | São Paulo GP | Autódromo José Carlos Pace (Interlagos) | Brazil | 4.309 (2.68 mi) | 71 | 15 | 1:10.540 (Valtteri Bottas, 2018) | [F1.com](https://www.formula1.com/en/racing/2026/brazil) |
| 21 | Las Vegas GP | Las Vegas Strip Circuit | USA | 6.201 (3.85 mi) | 50 | 17 | 1:33.365 (Max Verstappen, 2025) | [F1.com](https://www.formula1.com/en/racing/2026/las-vegas) |
| 22 | Qatar GP | Lusail International Circuit | Qatar | 5.419 (3.37 mi) | 57 | 16 | 1:22.384 (Lando Norris, 2024) | [F1.com](https://www.formula1.com/en/racing/2026/qatar) |
| 23 | Abu Dhabi GP | Yas Marina Circuit | United Arab Emirates | 5.281 (3.28 mi) | 58 | 16 | 1:25.637 (Kevin Magnussen, 2024) | [F1.com](https://www.formula1.com/en/racing/2026/united-arab-emirates) |

Notes on the table:
- **Sepang's lap record** (Vettel 2017) is from the old Malaysian GP. Formula1.com still shows it on the 2026 "Bahrain GP in Malaysia" page ([F1.com](https://www.formula1.com/en/racing/2026/bahrain)).
- **Monaco race vs qualifying:** the race lap record is 1:12.909 (Hamilton, 2021), but pole in 2026 was faster, a 1:12.051 by Kimi Antonelli, because qualifying laps use fresh tyres and little fuel ([F1.com Monaco](https://www.formula1.com/en/racing/2026/monaco); 2026 qualifying times from F1 live timing via [FastF1](https://docs.fastf1.dev/)).
- **Monaco race distance** is only 260.286 km (161.7 mi). Every other race is about 305 to 310 km (190 to 193 mi) ([F1.com](https://www.formula1.com/en/racing/2026/monaco)).
- **Spa is the longest lap** at 7.004 km (4.35 mi), and **Monaco the shortest** at 3.337 km (2.07 mi) ([F1.com Belgium](https://www.formula1.com/en/racing/2026/belgium); [F1.com Monaco](https://www.formula1.com/en/racing/2026/monaco)).

### 1.2 Showcase circuits for the lap animation

We picked three tracks that feel very different, so visitors can compare them:

| Circuit | Personality | Everyday comparison |
|---|---|---|
| **Monza** (Italy) | Fastest track: long straights cut by tight chicanes. The cars spend most of the lap at full throttle. | A motorway with three speed bumps |
| **Monaco** | Slowest track: narrow city streets lined by metal barriers, with the slowest hairpin of the year. No Straight Mode at all in 2026. | Racing through a hillside old town |
| **Silverstone** (UK) | Fast, flowing bends taken flat out at close to 300 km/h (186 mph). Few heavy braking zones. | A roller-coaster with long sweeping curves |

**Where the numbers come from (read this first).** The corner speeds, gears and braking points below are **our calculation** from one 2026 qualifying lap per circuit. The data is F1 live timing loaded with FastF1 3.8.3 ([FastF1 docs](https://docs.fastf1.dev/)). Car data arrives about 4 times a second, so at 300 km/h (186 mph) there can be 20 to 25 m (65 to 80 ft) between samples. Read speeds as "about" (we rounded them to the nearest 5 km/h) and distances as plus or minus 25 m. Distances are metres from the start/finish timing line *along that lap*. The measured lap is about 1% shorter or longer than the official length, because cars cut corners and the GPS-style distance drifts a little. For animation, divide by the measured lap length to get a 0 to 1 position along the path (the `u` value in [f1_lap_keyframes.json](f1_lap_keyframes.json)).

**Straight Mode zones** come from the FIA's official 2026 circuit maps for each event (links per circuit). The FIA map gives where each zone **opens** (for example "70 m after T3"). The wings **close** automatically when the driver brakes or lifts off the throttle, and some zones also have a fixed "turn-off" distance ([F1.com key terms](https://www.formula1.com/en/latest/article/explained-the-new-key-terms-for-formula-1s-new-for-2026-rules.3T5BU6TC9quGcIpGzoWkY0)). In practice that is where our telemetry shows the braking point. In **low-grip conditions** (for example rain), the Race Director can allow only **partial** activation: the front wing opens but the rear wing stays in Corner Mode, and the zones start later ([FIA Sporting Regulations B7.1.1d and B7.1.2b, Issue 09](https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf)).

**Super clipping, a 2026 quirk worth animating.** On long straights the 2026 car can run short of battery energy. The power unit then starts recharging even at full throttle, and the car **slows slightly before the braking zone** ([F1.com key terms](https://www.formula1.com/en/latest/article/explained-the-new-key-terms-for-formula-1s-new-for-2026-rules.3T5BU6TC9quGcIpGzoWkY0)). You can see it in the data. At Monza, Verstappen peaked at 334 km/h (208 mph) about 350 m after the line, then dropped to about 326 km/h (203 mph) by the Turn 1 braking point while still at full throttle (**our calculation**, FastF1).

#### Monza: Autodromo Nazionale Monza ("Temple of Speed")

- Official length 5.793 km (3.60 mi), 53 laps, 11 turns ([F1.com](https://www.formula1.com/en/racing/2026/italy)).
- 2026 pole: Pierre Gasly (Alpine) 1:21.786. Gasly's lap has a short gap in its data around the Roggia chicane, so the table uses **Max Verstappen's clean 1:22.070** (Q3, 6th). Highest Q3 speed in the data: **342 km/h (213 mph)** on Gasly's pole lap (F1 live timing via [FastF1](https://docs.fastf1.dev/), **our calculation**).
- Brakes: Brembo rates Monza 3 out of 5 for braking difficulty, with 5 braking zones per lap ([Brembo Monza 2026](https://www.brembo.com/en/motorsport/formula1/2026/facts-monza-2026)).

| Turn | Common name | Entry speed km/h (mph), gear | Brake point (m from line) | Apex speed km/h (mph), gear | What happens |
|---|---|---|---|---|---|
| T1-T2 | Variante del Rettifilo (first chicane) | 325 (202), 8th | ~784 | 75-80 (47-50), 1st | Hardest stop of the lap: from about 320 to under 90 km/h |
| T3 | Curva Biassono / Curva Grande | flat out | none | ~300 (186), 8th | Long right-hander taken without lifting |
| T4-T5 | Variante della Roggia | 300 (186), 8th | ~2,009 | ~110 (68), 3rd | Second chicane |
| T6 | Lesmo 1 | 235 (146), 5th | ~2,430 | ~195 (121), 5th | Short brake, fast right |
| T7 | Lesmo 2 | 240 (149), 6th | ~2,772 | ~185 (115), 5th | Exit leads to the run under the old banking |
| T8-T9 | Variante Ascari | 310 (193), 8th | ~3,823 | ~185-195 (115-121), 5th | Fast left-right-left chicane |
| T10 | Ascari exit | flat out | none | ~235 (146), 6th | Back on power |
| T11 | Curva Alboreto (Parabolica) | 310 (193), 8th | ~5,035 | ~205 (127), 5th | Long right curve onto the main straight |

Source for every speed, gear and distance above: F1 live timing, 2026 Italian GP qualifying, Verstappen Q3 lap, via [FastF1](https://docs.fastf1.dev/), **our calculation**. Corner numbers: FastF1 circuit info, matching the [FIA 2026 Italian GP circuit map](https://www.fia.com/system/files/decision-document/2026_italian_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf). Corner names are the commonly used ones.

Top speeds on the straights (same lap, **our calculation**): main straight **334 km/h (208 mph)**; Curva Grande to Roggia **307 km/h (191 mph)**; Lesmo 2 to Ascari **319 km/h (198 mph)**; Ascari to Parabolica **321 km/h (199 mph)**.

Brembo's simulation of the hardest stop, Turn 1: **318 to 87 km/h (198 to 54 mph) in 3.22 s over 153 m (502 ft), at 3.8 g** ([Brembo Monza 2026](https://www.brembo.com/en/motorsport/formula1/2026/facts-monza-2026)). Brembo also says the 2026 cars brake more gently than the 2025 cars did. At the Roggia chicane, peak deceleration drops from 4.5 g to 3.7 g, and the braking distance grows from 107 m to 121 m (351 to 397 ft) (same source).

**Straight Mode at Monza: 4 zones** ([FIA 2026 Italian GP circuit map](https://www.fia.com/system/files/decision-document/2026_italian_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf); [F1.com Monza guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-autodromo-nazionale-monza.51PKqBRlxNs0fzLWQzsnd0)):

| Zone | Wings open (normal grip) | Low-grip start | Approx. open → close on the Verstappen lap (m) | Closes |
|---|---|---|---|---|
| A1 | 30 m after T11 / pit exit | 100 m after T11 | ~5,220 → ~784 (crosses the finish line) | Braking for T1 |
| A2 | 70 m after T3 | 110 m after T3 | ~1,533 → ~2,009 | Braking for T4 |
| A3 | 170 m after T7 | 230 m after T7 | ~3,010 → ~3,823 | Braking for T8 |
| A4 | 130 m after T10 | 180 m after T10 | ~4,225 → ~5,035 | Braking for T11 |

"Open" positions come from the FIA map. The lap-distance positions are **our calculation**: the FIA offset added to the FastF1 corner position on this lap. **Overtake Mode:** the detection line is just before Turn 11 and the activation line is on the exit of Turn 11, onto the main straight ([F1.com Monza guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-autodromo-nazionale-monza.51PKqBRlxNs0fzLWQzsnd0)).

#### Monaco: Circuit de Monaco

- Official length 3.337 km (2.07 mi), 78 laps, 19 turns ([F1.com](https://www.formula1.com/en/racing/2026/monaco)).
- 2026 pole: Kimi Antonelli (Mercedes) 1:12.051. That lap is used below. Top speed on the lap: **289 km/h (180 mph)** at the end of the tunnel (F1 live timing via [FastF1](https://docs.fastf1.dev/), **our calculation**).
- **No Straight Mode zones at all.** The wings stay in Corner Mode all weekend. The FIA's rules say a zone must last more than 3 seconds and sit where the tyres are not at their grip limit, and Monaco has no section that meets both ([F1.com](https://www.formula1.com/en/latest/article/explained-why-active-aero-will-not-be-used-at-the-monaco-grand-prix.4nLtpjM9ZTUbPBQLmeAbj4); [The Race](https://www.the-race.com/formula-1/why-f1-cars-wont-run-active-aero-in-monaco/)). The FIA also capped electric power at Monaco: the full 350 kW only up to 200 km/h (124 mph), falling to about 100 kW at 270 km/h (168 mph) and zero at 300 km/h (186 mph) ([Autosport](https://www.autosport.com/f1/news/how-the-fia-is-limiting-f1-cars-top-speed-with-new-engine-maps-at-monaco-gp/10825365/)).
- **Overtake Mode:** detection between T16 and T17, activation between T18 and T19 ([F1.com Monaco guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-circuit-de-monaco.vFsmfGHr6RWyLFtxi58wi)).

| Turn | Common name | Entry speed km/h (mph), gear | Brake point (m from line) | Apex speed km/h (mph), gear |
|---|---|---|---|---|
| T1 | Sainte Dévote | 275 (171), 6th | ~92 | ~110 (68), 2nd |
| T2 | Beau Rivage (uphill) | flat out | none | ~265 (165), 6th |
| T3 | Massenet | 270 (168), 6th | ~637 | ~155 (96), 3rd |
| T4 | Casino Square | (same braking zone) | | ~140 (87), 3rd |
| T5 | Mirabeau Haute | 220 (137), 5th | ~1,019 | ~75 (47), 1st |
| T6 | Grand Hotel hairpin | (short brake from ~150 km/h) | | **~45 (28), 1st, slowest corner of the season** |
| T7 | Mirabeau Bas | | | ~60 (37), 1st |
| T8 | Portier | | | ~80 (50), 1st |
| T9 | Tunnel | flat out | none | ~260 (162), 6th |
| T10-T11 | Nouvelle Chicane | 290 (180), 7th | ~1,951 | ~70 (43), 1st |
| T12 | Tabac | 240 (149), 5th | ~2,263 | ~170 (106), 4th |
| T13-T14 | Swimming Pool (first part) | lift, no brake | | ~225-230 (140-143), 5th |
| T15-T16 | Swimming Pool (second part) | 250 (155), 6th | ~2,569 | ~120 (75), 2nd |
| T17 | Kink before Rascasse | | | ~135 (84), 2nd |
| T18 | La Rascasse | 200 (124), 4th | ~2,769 | ~60 (37), 1st |
| T19 | Anthony Noghès | | | ~85 (53), 1st |

Source for every speed, gear and distance above: F1 live timing, 2026 Monaco GP qualifying, Antonelli pole lap, via [FastF1](https://docs.fastf1.dev/), **our calculation**. Blank entry cells mean the driver was still slowing from the previous braking zone.

Top speeds (same lap): start/finish straight **~272 to 276 km/h (169 to 171 mph)** before Sainte Dévote; tunnel exit **289 km/h (180 mph)**. Brembo's hardest stop is Sainte Dévote: **276 to 132 km/h (171 to 82 mph) in 1.67 s over 91 m (299 ft), at 4 g**. The chicane after the tunnel now needs 136 m (446 ft) of braking, up from 91 m in 2025 ([Brembo Monaco 2026](https://www.brembo.com/en/motorsport/formula1/2026/facts-monaco-2026)).

#### Silverstone: Silverstone Circuit (home of the first ever World Championship race, 1950)

- Official length 5.891 km (3.66 mi), 52 laps, 18 turns ([F1.com](https://www.formula1.com/en/racing/2026/great-britain)).
- 2026 pole: Antonelli 1:28.111. The table uses **Charles Leclerc's 1:28.286** (2nd), which has the cleanest data. Top speed on that lap: **316 km/h (196 mph)** on the run to Copse (F1 live timing via [FastF1](https://docs.fastf1.dev/), **our calculation**).
- Brembo rates Silverstone 1 out of 5 for braking: only 3 real braking zones, just over 6.5 seconds of braking per lap ([Brembo UK 2026](https://www.brembo.com/en/motorsport/formula1/2026/facts-uk-2026)).

| Turn | Common name | Entry speed km/h (mph), gear | Brake point (m from line) | Apex speed km/h (mph), gear |
|---|---|---|---|---|
| T1 | Abbey | flat out | none | ~295 (183), 8th |
| T2 | Farm | flat out | none | ~280 (174), 7th |
| T3 | Village | 245 (152), 7th | ~807 | ~115 (71), 2nd |
| T4 | The Loop | (same braking zone) | | ~85 (53), 2nd, slowest point of the lap |
| T5 | Aintree | flat out | none | ~215 (134), 5th |
| T6 | Brooklands | 265 (165), 8th | ~1,888 | ~170 (106), 4th |
| T7 | Luffield | 190 (118), 4th | ~2,074 | ~110 (68), 2nd |
| T8 | Woodcote | flat out | none | ~280 (174), 7th |
| T9 | Copse | flat out | none | ~290 (180), 7th |
| T10-T11 | Maggotts / Becketts | flat out | none | ~270-285 (168-177), 7th |
| T12-T13 | Becketts | 270 (168), 7th, lift then a dab of brake | ~3,922 | ~210-255 (130-158), 5th-6th |
| T14 | Chapel | flat out | none | ~230 (143), 5th |
| T15 | Stowe | 290 (180), 8th | ~4,924 | ~225 (140), 6th |
| T16-T17 | Vale / Club | 270 (168), 6th | ~5,411 | ~110 (68), 2nd |
| T18 | Club exit | flat out | none | ~185 (115), 4th |

Source for every speed, gear and distance above: F1 live timing, 2026 British GP qualifying, Leclerc Q3 lap, via [FastF1](https://docs.fastf1.dev/), **our calculation**. Corner names are the commonly used ones. Silverstone's naming of the Maggotts/Becketts/Chapel turns varies between sources, so treat T10 to T14 names as approximate.

Top speeds (same lap): Hamilton Straight **314 km/h (195 mph)**; Wellington Straight **305 km/h (190 mph)**; Woodcote to Copse **316 km/h (196 mph)**; Hangar Straight **302 km/h (188 mph)**. Brembo's hardest stop is Turn 16 (Vale): **268 to 116 km/h (167 to 72 mph) in 2.45 s over 125 m (410 ft), at 3.1 g**. At Turn 3 the peak deceleration fell from 4.5 g in 2025 to 2.9 g in 2026 ([Brembo UK 2026](https://www.brembo.com/en/motorsport/formula1/2026/facts-uk-2026)).

**Straight Mode at Silverstone: 4 zones** ([FIA 2026 British GP circuit map](https://www.fia.com/system/files/decision-document/2026_british_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf); [F1.com Silverstone guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-silverstone-2026.5Sl0O8g393enBWVIkjRzOr)):

| Zone | Where | Wings open (normal grip) | Low-grip start | Approx. open → close on the Leclerc lap (m) |
|---|---|---|---|---|
| A1 | Hamilton Straight (start/finish) | 65 m after T18 | 115 m after T18 | ~5,756 → before T1 (end not given on the FIA map; ~290 is our estimate) |
| A2 | Wellington Straight | 55 m after T5 | 115 m after T5 | ~1,280 → ~1,888 (braking for T6) |
| A3 | Luffield to Woodcote/Copse | 155 m after T7 | **not used in low grip** | ~2,337 → before T9 (end ~2,900 is our estimate) |
| A4 | Hangar Straight | 65 m after T14 | 125 m after T14 | ~4,193 → ~4,924 (braking for T15) |

Williams' technical brief confirms the third zone, near Woodcote, is switched off in the wet ([Williams](https://www.williamsf1.com/articles/5df640e6-d376-4422-9de6-000d972c8053/technical-brief-great-britain)). **Overtake Mode:** detection just after the exit of T17, activation just before T18 ([F1.com Silverstone guide](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-silverstone-2026.5Sl0O8g393enBWVIkjRzOr); [FIA map](https://www.fia.com/system/files/decision-document/2026_british_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf)).

**How many Straight Mode zones elsewhere?** PlanetF1 counted the zones round by round: Australia 5, China 4, Japan 2, Miami 3, Canada 3, Monaco 0, Barcelona 4, Austria 4, Britain 4, Belgium 5, Hungary 4, Netherlands 2, Italy 4 ([PlanetF1](https://www.planetf1.com/news/italian-grand-prix-2026-fia)). **UNVERIFIED for Canada:** PlanetF1 says 3 zones, while Formula1.com lists four Canadian zones (start/finish; T7 to T8; T9 to T10; T11 to T13) ([F1.com](https://www.formula1.com/en/latest/article/explained-why-active-aero-will-not-be-used-at-the-monaco-grand-prix.4nLtpjM9ZTUbPBQLmeAbj4)). Prefer the FIA event map for any circuit you add.

**Animation tips:**
- Drive the car along the path using the measured speed between keyframes, so that time = distance ÷ speed. Don't move it at a constant rate.
- Show the wings flipping flat at each "open" point and snapping back at the braking point. At Monaco, show a "Corner Mode locked" badge instead.
- Shake the camera or show a g-meter at the big braking zones (Monza T1, Monaco T10, Silverstone T16).
- Colour the track by speed (blue for slow, red for fast). It makes Monaco versus Monza obvious at a glance.

### 1.3 Free track shapes you can use on a public website

| Source | What you get | Licence and what you must do | Good for | Watch out for |
|---|---|---|---|---|
| **bacinger/f1-circuits** ([GitHub](https://github.com/bacinger/f1-circuits)) | One GeoJSON `LineString` per circuit (longitude/latitude), plus name, length, opening year, first GP and altitude. Includes 2026 venues such as Madring (`es-2026.geojson`), Sepang (`my-1999.geojson`) and Las Vegas (`us-2023.geojson`). Monza has 125 points. | **MIT licence**: free to use, change and ship, including commercially. You must keep the copyright and licence notice ("Copyright (c) 2019-2025 Tomislav Bacinger") ([LICENSE](https://github.com/bacinger/f1-circuits/blob/master/LICENSE.md)). | Fast, light 2D outlines for every track | The README says the shapes were first traced from a Google My Maps layer ([README](https://github.com/bacinger/f1-circuits)). The precision is "good outline", not survey grade. Height is one altitude value per track, so the outline is flat. |
| **OpenStreetMap** (OSM) ([copyright page](https://www.openstreetmap.org/copyright)) | Real mapped geometry. Race tracks are usually tagged `highway=raceway`. You can download them with the Overpass API. | **ODbL 1.0** ([licence](https://opendatacommons.org/licenses/odbl/1-0/)). Show "© OpenStreetMap contributors" with a link to the copyright page. If you publish an altered **database** (for example a cleaned GeoJSON file that your site serves to browsers), that file must also be shared under ODbL. A picture or 3D scene made from it is a "produced work" and only needs the attribution. | Accurate shapes, pit lanes, run-off areas, nearby buildings | Ways may be split into pieces and include extra layouts, so you have to join and clean them |
| **FastF1** ([docs](https://docs.fastf1.dev/), MIT code on [GitHub](https://github.com/theOehrly/Fast-F1)) | Python library. Gives car position (X, Y, Z), speed, gear, throttle, brake and lap times from F1's live timing, plus corner numbers and positions (`get_circuit_info()`). | The **code** is MIT. The **data** is not FastF1's: FastF1 says it is unofficial and not associated with Formula 1 ([FastF1 docs](https://docs.fastf1.dev/)). Formula 1 says it owns rights in "Results and Timing data", and allows only limited, justified, **non-commercial** educational use ([F1 Guidelines](https://www.formula1.com/en/information/guidelines.4EOKE9RRqevL4niTK9kWyt)). | Real speed traces, corner markers, even 3D elevation from Z | Do not redistribute raw telemetry files. Ship small, rounded, derived numbers (like our keyframes JSON), credit "Data: F1 live timing via FastF1", and ask F1 (brandprotection@f1.com) before any commercial use. |
| **Sketchfab 3D track models** (CC-BY 4.0) | Ready-made 3D tracks, for example "Autodromo Nazionale Monza Circuit 2020 layout" (1.19M faces), "Monza Circuit 1998 layout" (152k), "Silverstone Circuit 2024 layout" (1.20M), "Silverstone Circuit 1999 layout" (92k), "Circuit de Spa-Francorchamps 2022 layout" (1.19M), all by Tyler_Dave; "Monaco GP racetrack" by narlankaaditya (19k faces, low poly); "Circuit de Monaco F1" by neosearch (4k faces) ([Monza 2020](https://sketchfab.com/3d-models/autodromo-nazionale-monza-circuit-2020-layout-25ed955115094de382935aa6d1a1e9c6), [Monza 1998](https://sketchfab.com/3d-models/monza-circuit-1998-layout-01ee75b53e6d4e2895b6f69ea9cb4f5c), [Silverstone 2024](https://sketchfab.com/3d-models/silverstone-circuit-2024-layout-bbaf4b12d5244c76998fd44f771fc0b3), [Silverstone 1999](https://sketchfab.com/3d-models/silverstone-circuit-1999-layout-cad872e65ded4292a2061a7cc3b48d78), [Spa 2022](https://sketchfab.com/3d-models/circuit-de-spa-francorchamps-2022-layout-ac681fbf548144498c130c3aa0adeb54), [Monaco low poly](https://sketchfab.com/3d-models/monaco-gp-racetrack-ebb9b9a0c19e4801815b19c55d14dea3), [Monaco 4k](https://sketchfab.com/3d-models/circuit-de-monaco-f1-77a7a29b4f5b4380970828e3f724e62f)). | **CC-BY 4.0** on all of these (checked through the Sketchfab API on 15 Oct 2026): credit the author and link the model ([licence](https://creativecommons.org/licenses/by/4.0/)). We found no CC0 F1 tracks. | Hero shots and fly-overs | Million-face models are too heavy for phones, so decimate them. Some track models may be ported from games: CC-BY only covers what the uploader owns, so read each description. Old layouts (1998/1999) differ from today's. Remove any sponsor boards in the textures. |

**Recommendation:** use **bacinger GeoJSON** for the 2D/3D lap path on all 23 tracks (simple MIT licence). Add **FastF1-derived keyframes** (rounded) for speed, gear and brake, and **OSM** if you want accurate surroundings. Keep a credits page listing the MIT notice, "© OpenStreetMap contributors", "Data: F1 live timing via FastF1 (unofficial)", and any CC-BY authors.

### 1.4 Turning GeoJSON into a Three.js path (step by step)

1. **Load** the file, for example `it-1922.geojson` (Monza), and take `features[0].geometry.coordinates`. That is a list of `[longitude, latitude]` pairs.
2. **Project to metres.** Longitude/latitude are angles, not distances. Pick the track's centre (lon0, lat0) and convert each point with a simple flat-Earth projection. It is accurate to well under 1% across a 5 km track: `x = (lon - lon0) × 111,320 × cos(lat0)` and `z = -(lat - lat0) × 110,540`. In Three.js, Y is up, so north becomes negative Z.
3. **Close and smooth.** Remove a repeated last point if it equals the first, then build a `THREE.CatmullRomCurve3(points, true)`. A Catmull-Rom curve is a smooth curve that passes through every point; `true` makes it a closed loop.
4. **Scale to the official length.** `curve.getLength()` gives the drawn length. Multiply all points by `officialLength / drawnLength` (for example 5,793 m for Monza), so distances in your telemetry line up.
5. **Find the start line and direction.** Rotate the point list so index 0 sits at the start/finish line, and reverse it if the cars run the other way. Check this against the FIA circuit map or a FastF1 lap.
6. **Draw the road.** Either a `TubeGeometry` (quick and round) or, better, a flat ribbon: for each sample along the curve, offset left and right by half the track width (about 12 to 15 m; this width is **our estimate**, not an official figure) using the curve's normal.
7. **Move the car.** `curve.getPointAt(u)` gives position and `curve.getTangentAt(u)` gives heading for any `u` from 0 to 1. Use `getPointAt`, not `getPoint`, because it spaces points evenly by distance. Convert distance to `u` with `u = distance / lapLength`, and advance `distance` each frame by `speed × deltaTime` using the speed keyframes.
8. **Add markers** (braking boards, Straight Mode start/end, corner numbers) at their `u` values from [f1_lap_keyframes.json](f1_lap_keyframes.json).

```js
import * as THREE from 'three';

const R_LAT = 110540, R_LON = 111320;           // metres per degree
async function loadTrack(url, officialLengthM) {
  const gj = await (await fetch(url)).json();
  let coords = gj.features[0].geometry.coordinates;   // [lon, lat]
  const lon0 = coords.reduce((s, c) => s + c[0], 0) / coords.length;
  const lat0 = coords.reduce((s, c) => s + c[1], 0) / coords.length;
  const k = Math.cos(lat0 * Math.PI / 180);
  let pts = coords.map(([lon, lat]) =>
    new THREE.Vector3((lon - lon0) * R_LON * k, 0, -(lat - lat0) * R_LAT));
  if (pts[0].distanceTo(pts[pts.length - 1]) < 1) pts.pop();  // drop duplicate end
  let curve = new THREE.CatmullRomCurve3(pts, true, 'centripetal');
  const s = officialLengthM / curve.getLength();             // match official length
  pts = pts.map(p => p.multiplyScalar(s));
  curve = new THREE.CatmullRomCurve3(pts, true, 'centripetal');
  return curve;
}

// per frame: distance += speed_ms * dt; u = (distance % L) / L;
// car.position.copy(curve.getPointAt(u));
// car.lookAt(car.position.clone().add(curve.getTangentAt(u)));
```

The `'centripetal'` option avoids loops and overshoots at tight hairpins such as Monaco's Turn 6 ([Three.js CatmullRomCurve3 docs](https://threejs.org/docs/#api/en/extras/curves/CatmullRomCurve3); [Curve.getPointAt docs](https://threejs.org/docs/#api/en/extras/core/Curve)).

**Hills (optional):** bacinger gives only one altitude per track. For real elevation, sample FastF1's `Z` position along a lap and map it onto the curve by distance (a derived use, see the licence notes above), or sample a free elevation model. Exaggerating heights about 2 to 3 times makes Spa's Eau Rouge and Monaco's climb readable on screen.

---

## 2. TEAMS 2026

Eleven teams and 22 drivers race in 2026. That is one more team than in 2025, because **Cadillac** joined, and **Audi** took over the Sauber team ([F1.com teams](https://www.formula1.com/en/teams)). A few words first:

- **Constructor / team:** the company that designs and builds the car (the **chassis**, meaning the car's main body and frame).
- **Power unit (PU):** F1's word for the engine package: a 1.6-litre turbo petrol engine plus an electric motor and battery. Some teams build their own; others buy them from a supplier, like a small airline buying jet engines from Rolls-Royce.
- **Base / factory:** where the car is designed and built. Most teams are in England's "Motorsport Valley" around Oxford.
- **Constructors' championship:** the yearly title for the best *team* (points from both cars added together). It is separate from the drivers' championship.

The table uses each team's Formula1.com profile page (linked) for base, power unit, chassis name, first entry year and championship count. "First entry" is the first year *this team, under any name*, raced in F1. "Titles" are constructors' championships as Formula1.com counts them, before the end of 2026.

| Team (2026 name in short) | Base | Power unit | 2026 car | First entry | Constructors' titles | Drivers | Source |
|---|---|---|---|---|---|---|---|
| Mercedes | Brackley, UK | Mercedes | W17 | 1970 | 8 | George Russell, Kimi Antonelli | [F1.com](https://www.formula1.com/en/teams/mercedes) |
| Ferrari | Maranello, Italy | Ferrari | SF-26 | 1950 | 16 | Charles Leclerc, Lewis Hamilton | [F1.com](https://www.formula1.com/en/teams/ferrari) |
| McLaren | Woking, UK | Mercedes | MCL40 | 1966 | 10 | Lando Norris, Oscar Piastri | [F1.com](https://www.formula1.com/en/teams/mclaren) |
| Red Bull Racing | Milton Keynes, UK | Red Bull Ford | RB22 | 1997 | 6 | Max Verstappen, Isack Hadjar | [F1.com](https://www.formula1.com/en/teams/red-bull-racing) |
| Racing Bulls | Faenza, Italy | Red Bull Ford | VCARB 03 | 1985 | 0 | Liam Lawson, Arvid Lindblad | [F1.com](https://www.formula1.com/en/teams/racing-bulls) |
| Alpine | Enstone, UK | Mercedes | A526 | 1986 | 2 | Pierre Gasly, Franco Colapinto | [F1.com](https://www.formula1.com/en/teams/alpine) |
| Haas | Kannapolis, USA | Ferrari | VF-26 | 2016 | 0 | Esteban Ocon, Oliver Bearman | [F1.com](https://www.formula1.com/en/teams/haas) |
| Audi | Hinwil, Switzerland | Audi | R26 | 2026 | 0 | Nico Hülkenberg, Gabriel Bortoleto | [F1.com](https://www.formula1.com/en/teams/audi) |
| Williams | Grove, UK | Mercedes | FW48 | 1978 | **8 or 9, UNVERIFIED** (see note) | Carlos Sainz, Alex Albon | [F1.com](https://www.formula1.com/en/teams/williams) |
| Aston Martin | Silverstone, UK | Honda | AMR26 | 2018 | 0 | Fernando Alonso, Lance Stroll | [F1.com](https://www.formula1.com/en/teams/aston-martin) |
| Cadillac | Silverstone, UK | Ferrari | MAC-26 | 2026 | 0 | Sergio Pérez, Valtteri Bottas | [F1.com](https://www.formula1.com/en/teams/cadillac) |

**Notes and conflicts:**
- **Williams titles: UNVERIFIED.** Formula1.com's Williams page says **8** ([F1.com](https://www.formula1.com/en/teams/williams)). Autosport's list of the most successful teams gives Williams **9** ([Autosport](https://www.autosport.com/f1/news/most-successful-f1-teams-which-team-has-the-most-constructors-titles-5367606/5367606/)). The commonly cited title years are 1980, 1981, 1986, 1987, 1992, 1993, 1994, 1996 and 1997, which is nine. Use "9" with a note, or quote both.
- **Team "family trees" make "first entry" and title counts confusing.** Formula1.com counts each team's history on its own line. Alpine's 2 titles are the Renault wins of 2005 and 2006; the 1995 Benetton title from the same Enstone factory is not counted. Aston Martin's line starts in 2018 (the Racing Point era), though the factory goes back to Jordan in 1991. Audi takes over Sauber's Hinwil factory but is listed as a new 2026 entry. Mercedes' 1970 date is the Tyrrell/BAR/Honda/Brawn factory line at Brackley. Red Bull's 1997 is the Stewart line. Racing Bulls' 1985 is the Minardi line. All from the linked F1.com pages.
- **2026 results so far** (17 of 23 rounds, [F1.com calendar](https://www.formula1.com/en/racing/2026)): Mercedes has won 11 races (Antonelli 8, Russell 3). The rest: Hamilton (Ferrari) won Barcelona, Leclerc (Ferrari) Britain, Norris (McLaren) Hungary and the Netherlands, and Verstappen (Red Bull) Malaysia and Singapore.
- **The reigning champions** going into 2026 were McLaren (constructors', second year in a row) and Lando Norris (drivers', 2025) ([Brembo 2025 season numbers](https://www.brembo.com/en/motorsport/formula1/2025-numbers)).

### Team summaries (for the team cards)

Leadership names are from each team's F1.com page (link in the table above).

- **Mercedes:** The silver team from Brackley, run by Toto Wolff. It dominated the first hybrid era with eight straight constructors' titles from 2014 to 2021. It started 2026 as the team to beat, winning 11 of the first 17 races. Its Italian teenager, Kimi Antonelli, leads the championship.
- **Ferrari:** The only team that has raced in every season since 1950, and the most successful, with 16 constructors' titles. Its red cars are built in Maranello, Italy. Team boss Fred Vasseur pairs Charles Leclerc with seven-time champion Lewis Hamilton, who joined in 2025.
- **McLaren:** Founded by New Zealander Bruce McLaren and based in Woking, England. It won the 2024 and 2025 constructors' titles, and Lando Norris won the 2025 drivers' crown. Team principal Andrea Stella runs it. Since 2026 it uses Mercedes power units.
- **Red Bull Racing:** An energy-drink-owned team from Milton Keynes. It won four titles in a row with Sebastian Vettel (2010–13) and four more drivers' titles with Max Verstappen (2021–24). For 2026 it builds its own power unit for the first time, with Ford as a partner. Laurent Mekies leads the team.
- **Racing Bulls:** Red Bull's second team, based in Faenza, Italy. It began life as Minardi in 1985 and has been a training ground for young drivers such as Vettel and Verstappen. In 2026 it fields Liam Lawson and rookie Arvid Lindblad. Alan Permane is team principal.
- **Alpine:** Renault's sports brand, racing from the Enstone factory that won titles as Benetton in 1995 and as Renault in 2005–06. From 2026 it buys Mercedes power units instead of building Renault engines. Flavio Briatore is executive adviser and Steve Nielsen managing director. Pierre Gasly took a surprise pole at Monza in 2026.
- **Haas:** The only American-owned team before Cadillac, founded by Gene Haas, with its base in Kannapolis, North Carolina, and a UK office. It buys many parts and its power unit from Ferrari. Ayao Komatsu is team chief. Its 2026 entry name carries Toyota's TGR (Toyota Gazoo Racing) branding, reflecting a technical partnership.
- **Audi:** The German car maker's first season as a works F1 team, building both chassis and power unit. It took over the long-running Sauber team in Hinwil, Switzerland. Mattia Binotto, Ferrari's former boss, heads the project and is also team principal.
- **Williams:** A family-founded team from Grove, England, started by Sir Frank Williams and Patrick Head. It was the powerhouse of the 1980s and 1990s, with world champions such as Nigel Mansell and Damon Hill. Team principal James Vowles is rebuilding it around Carlos Sainz and Alex Albon.
- **Aston Martin:** The British sports-car brand's team, based at a new factory next to the Silverstone circuit. Legendary designer Adrian Newey joined in 2025 and leads the team, and Honda became its works power-unit partner in 2026. Fernando Alonso, a two-time champion, races alongside Lance Stroll.
- **Cadillac:** The 11th team and the first new team since Haas in 2016, backed by General Motors and TWG Motorsports ([F1.com Cadillac](https://www.formula1.com/en/teams/cadillac)). It races with Ferrari power units until a GM unit is ready. Graeme Lowdon was its first team principal; F1.com now lists Marcin Budkowski as team chief. Veterans Sergio Pérez and Valtteri Bottas give it experience. Its best result so far in 2026 is 13th ([F1.com Cadillac](https://www.formula1.com/en/teams/cadillac)).

Toyota's exact role at Haas is not detailed on the F1.com page and is listed under Gaps.

### Trademark and image caution (important)

- **Use names in plain text only.** "Ferrari", "Mercedes", "Red Bull", "Formula 1", "F1", "Grand Prix" event names and team names are registered trademarks. Formula 1 lets others use its word marks **only to describe or inform**, not as decoration or branding. Logos must not be used without a licence ([F1 Guidelines](https://www.formula1.com/en/information/guidelines.4EOKE9RRqevL4niTK9kWyt)).
- **No logos, badges, team liveries or sponsor decals** on your 3D cars or anywhere else. Paint every model in neutral colours, or your own colour scheme, and remove sponsor textures from downloaded models. A **livery** is a team's paint scheme and sponsor artwork, and it is protected as part of the team's brand.
- **No official photos or video** without a licence. Formula 1 and team images are copyrighted.
- **Say clearly that the site is unofficial**, for example: "This is an unofficial educational fan site. It is not associated with Formula 1, the FIA or any team. F1, FORMULA 1 and related marks are trade marks of Formula One Licensing B.V." ([F1 Guidelines](https://www.formula1.com/en/information/guidelines.4EOKE9RRqevL4niTK9kWyt)).
- Team colours can be hinted at with a single swatch next to the name, as a reader aid. That is a judgement call, not a legal guarantee. Get legal advice for any commercial launch, and contact brandprotection@f1.com about licensing.

---

## 3. COMPARISON TOOL: F1 car vs family car vs supercar vs aircraft

**What the metrics mean:**
- **0-100 km/h (0-62 mph):** time to accelerate from standstill to town-motorway speed.
- **0-200 km/h (0-124 mph):** the same, to roughly the top speed of a small family car.
- **Top speed:** the fastest the vehicle can go.
- **200-0 km/h braking:** the time and distance to stop from 200 km/h.
- **Peak braking g:** how hard the stop pushes the body forward. A normal hard stop in a family car is just under 1 g.
- **Peak cornering g:** the sideways push in a fast bend.
- **Power-to-weight:** engine power divided by weight. Higher means quicker. For jets we give **thrust-to-weight** instead, because jet engines produce push, not wheel power.
- **Weight:** as published. Each row says whether the driver or fuel is included.

**Chosen examples:**
- **F1 car:** 2026 rules.
- **Family car:** 2023 Toyota Corolla Hybrid, one of the world's best-selling cars, tested by Car and Driver.
- **Supercar:** Ferrari SF90 Stradale, a 1,000 cv plug-in hybrid. "cv" is the Italian horsepower unit, about 0.986 hp.
- **Airliner:** Airbus A320neo, a typical short-haul jet.
- **Fighter jet:** Lockheed Martin F-16 Fighting Falcon.

| Metric | F1 car (2026) | Family car (Toyota Corolla Hybrid SE AWD, 2023) | Supercar (Ferrari SF90 Stradale) | Airliner (Airbus A320neo) | Fighter jet (F-16) |
|---|---|---|---|---|---|
| **0-100 km/h** | **~2.3 to 2.9 s**, our calculation from 12 race starts in 2026 telemetry ([FastF1](https://docs.fastf1.dev/)). No official figure. | 0-60 mph (97 km/h) in **9.0 s** ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **2.5 s** ([Ferrari](https://www.ferrari.com/en-EN/auto/sf90-stradale); [Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | not published | not published |
| **0-200 km/h** | **~4.5 to 5.4 s**, our calculation, same race starts ([FastF1](https://docs.fastf1.dev/)). For reference, the 2025 Aston Martin AMR25 is listed at **0-160 km/h (99 mph) in 3.7 s** ([Aston Martin F1](https://www.astonmartinf1.com/en-GB/AMR25)). | Cannot reach 200 km/h. 0-100 mph (161 km/h) takes **38.7 s** ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **6.7 s** ([Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | not published | not published |
| **Top speed** | **342 km/h (213 mph)** in 2026 qualifying at Monza; **358 km/h (222 mph)** fastest 2026 speed trap, Ocon, Barcelona race, with a slipstream (F1 timing via [FastF1](https://docs.fastf1.dev/)). All-time race record **372.5 km/h (231 mph)**, Bottas, Mexico 2016 ([Williams](https://www.williamsf1.com/articles/253b1dc5-aee9-4d3b-b720-8e30f3a83093/how-fast-can-an-f1-car-go)) | **172 km/h (107 mph)**, electronically limited ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **340 km/h (211 mph)** ([Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | Max operating **Mach 0.82** ([Airbus](https://aircraft.airbus.com/en/aircraft/a320-family/a320neo)), about **870 km/h (541 mph)** at 11 km (36,000 ft) altitude (our conversion) | **Mach 2 class, about 2,414 km/h (1,500 mph)** at altitude ([US Air Force](https://www.af.mil/About-Us/Fact-Sheets/Display/Article/104505/f-16-fighting-falcon/)) |
| **200-0 km/h braking** | **~1.9 to 2.3 s, ~50 to 65 m (165 to 215 ft), UNVERIFIED** (our estimate from 2.5 to 3 g average deceleration; no published figure). Real example: Monza T1, 318 to 87 km/h in 3.22 s and 153 m ([Brembo](https://www.brembo.com/en/motorsport/formula1/2026/facts-monza-2026)) | n/a (top speed 172 km/h). 70-0 mph (113 km/h) takes **55 m (181 ft)** ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **~118 m (387 ft), UNVERIFIED** (our scaling of Ferrari's 100-0 figure of under 29.5 m (97 ft)) ([Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | not comparable | not comparable |
| **Peak braking g** | **About 4 g in 2026**: Brembo figures of 3.7 to 4 g at Monza and Monaco ([Brembo Monza](https://www.brembo.com/en/motorsport/formula1/2026/facts-monza-2026); [Brembo Monaco](https://www.brembo.com/en/motorsport/formula1/2026/facts-monaco-2026)); our telemetry estimate is 4.1 to 4.3 g. 2025 cars peaked at **5.1 g** in Canada ([Brembo 2025](https://www.brembo.com/en/motorsport/formula1/2025-numbers)) | **~0.9 g** average in the 70-0 mph test (our calculation from [Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **~1.3 g** average 100-0 (our calculation from the [Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | not comparable | not comparable |
| **Peak cornering g** | **Up to 5 g or more** for the high-downforce 2024 cars (Suzuka Turn 1, Eau Rouge, Maggotts) ([Mercedes](https://www.mercedesamgf1.com/news/g-force-and-formula-one-explained)). **2026: UNVERIFIED**, lower because the 2026 cars have less downforce, but no published number | **0.80 g** on the skidpad (a circular test pad) ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | not published by Ferrari | Normal flight load limit **+2.5 g** for this class of airliner ([US 14 CFR 25.337](https://www.law.cornell.edu/cfr/text/14/25.337)). Passengers normally feel far less. | **+9 g** ([US Air Force](https://www.af.mil/About-Us/Fact-Sheets/Display/Article/104505/f-16-fighting-falcon/)) |
| **Power-to-weight** | **~0.98 kW per kg**: about 400 kW engine + 350 kW electric ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)) divided by 768 kg (our calculation) | **~0.07 kW/kg**: 100 kW (134 hp) ÷ 1,460 kg (our calculation from [Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **~0.47 kW/kg**: 735 kW (1,000 cv) ÷ 1,570 kg dry (our calculation from the [Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | not comparable (thrust) | Thrust-to-weight **about 1 : 1**: 27,000 lb (120 kN) thrust vs about 26,700 lb (12.1 t) without-fuel weight plus full internal fuel (our calculation from the [US Air Force](https://www.af.mil/About-Us/Fact-Sheets/Display/Article/104505/f-16-fighting-falcon/)) |
| **Weight** | **768 kg (1,693 lb)** minimum, including driver, without fuel ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)) | **1,460 kg (3,218 lb)** as tested ([Car and Driver](https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/)) | **1,570 kg (3,461 lb)** dry ([Ferrari spec sheet](https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf)) | **79 t (174,165 lb)** maximum take-off weight ([Airbus](https://aircraft.airbus.com/en/aircraft/a320-family/a320neo)) | **8,936 kg (19,700 lb)** without fuel; 16,875 kg (37,500 lb) maximum take-off ([US Air Force](https://www.af.mil/About-Us/Fact-Sheets/Display/Article/104505/f-16-fighting-falcon/)) |

**How we got the F1 acceleration numbers.**
- We took 12 race-start launches in 2026: Monza, Silverstone, Spa and Austria, cars at the front of the grid. The speed traces come from F1 live timing via [FastF1](https://docs.fastf1.dev/).
- The race starts are with full fuel (cars weigh roughly 100 kg more). The traces are sampled about 4 times a second and include wheelspin, so a best-case car could be quicker.
- Show the result as a range, "about 2.5 seconds", not a single exact time.
- There is **no official 2026 0-100 figure** from the FIA or the teams.

**Why the F1 car loses to the supercar 0-100 but crushes it after.** Both get about 2.5 s to 100 km/h, because below that speed **traction** is the limit (how much grip the rear tyres have before they spin), not power. The supercar has four-wheel drive. Above 100 km/h the F1 car's double power-to-weight wins easily: about 5 s to 200 km/h against 6.7 s.

**Fun comparisons for captions:**
- **Braking:** at 4 g, a 75 kg (165 lb) driver's head and body press forward as if they weighed 300 kg (660 lb) (our calculation). The F1 car stops harder than any road car and harder than a jet airliner ever manoeuvres.
- **Cornering:** at about 5 g the driver's head and helmet, about 7 kg (15 lb) together (our estimate), feel like 35 kg (77 lb) pulling sideways.
- **Speed:** the 2026 F1 car's 358 km/h (222 mph) is faster than the take-off speed of most airliners. The usual figure is around 250 to 290 km/h (155 to 180 mph), but that is **UNVERIFIED**: we found no official A320neo figure.

---

## 4. PIT STOP GAME

### 4.1 What is a pit stop?

A **pit stop** is when a driver leaves the track, drives down the **pit lane** (a road beside the main straight, lined with team garages), stops in front of the garage in a marked **pit box**, gets four new tyres, and drives off again. Refuelling is only allowed inside the team garages, not at a pit stop, so a normal stop is only about tyres, and sometimes a front-wing adjustment or a new nose ([FIA Sporting Regulations B1.5.9](https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf)). Think of a supermarket car wash done by 20 people in two seconds.

### 4.2 The crew

Mercedes describes a crew of **up to 22 people** ([Mercedes](https://www.mercedesamgf1.com/news/box-box-pitstop-explained)). Formula1.com describes the same roles ([F1.com](https://www.formula1.com/en/latest/article/anatomy-of-a-pit-stop-how-do-f1-teams-service-their-cars-in-less-than-two.5p9LNdd8XJdvP4mRsXoGsB)).

| Role | How many | What they do |
|---|---|---|
| Wheel gun operators | 4 (one per wheel) | Use an air-powered wrench (the **wheel gun**) to undo and tighten the single central wheel nut |
| Wheel-off crew | 4 | Pull the old wheel away |
| Wheel-on crew | 4 | Push the new wheel on |
| Front jack | 1 (plus 1 spare) | Lifts the front with a long lever jack as the nose arrives |
| Rear jack | 1 (plus 1 spare) | Lifts the rear |
| Stabilisers | 2 | Hold the car steady at the sides while it is in the air |
| Front-wing adjusters | 2 | Change the front-wing angle with a tool if the engineers ask |
| Controller / chief mechanic | 1 | Watches every corner and runs the release light (red/green) that tells the driver to go |
| Reviewer / spare | 1 | Checks the stop and acts as a backup |

Total: 12 tyre crew (3 per wheel) + 4 jack people + 2 stabilisers + 2 wing adjusters + 1 controller + 1 reviewer = **22** ([Mercedes](https://www.mercedesamgf1.com/news/box-box-pitstop-explained)). For a simpler game, use 12 wheel crew + 2 jacks + 1 controller = 15 playable roles.

### 4.3 Step by step, with timings for a 2.2-second stop

From Formula1.com's breakdown of a typical stop ([F1.com](https://www.formula1.com/en/latest/article/anatomy-of-a-pit-stop-how-do-f1-teams-service-their-cars-in-less-than-two.5p9LNdd8XJdvP4mRsXoGsB)). Time 0 is when the car stops.

| Time (s) | Step |
|---|---|
| -15 to -20 | Crew walk out and take their places; new tyres are laid by each corner |
| -0.1 | The nose touches the front jack while still rolling |
| 0.0 | Car stops on its marks |
| 0.3 | Front jack lifts the car |
| 0.4 | Rear jack lifts the car; guns start undoing the nuts |
| ~0.6 | Old wheels come off |
| 1.2 | New wheels are on |
| 1.4 | Guns are back on the nuts, tightening |
| 1.9 | All guns off; each gun operator signals "done" |
| 2.1 | Car is dropped back to the ground |
| 2.2 | Release light turns green; the driver pulls away |

Mercedes gives similar phases: jacking and nut-off about 0.4 s, wheel swap about 1 s, gun-on about 0.3 s, drop under 0.1 s, and **the driver's own reaction to the green light about 0.3 s** ([Mercedes](https://www.mercedesamgf1.com/news/box-box-pitstop-explained)).

### 4.4 Key numbers

| Item | Value | Source |
|---|---|---|
| A good stop | 2.0 to 2.5 s (stationary time) | [F1.com](https://www.formula1.com/en/latest/article/anatomy-of-a-pit-stop-how-do-f1-teams-service-their-cars-in-less-than-two.5p9LNdd8XJdvP4mRsXoGsB); 2026 winners below |
| **World record** | **1.80 s**, McLaren (Lando Norris), Qatar GP, 8 Oct 2023 | [Guinness World Records](https://www.guinnessworldrecords.com/world-records/108666-fastest-formula-one-pit-stop) |
| Fastest stop of 2026 so far | **1.99 s**, Racing Bulls, Hungarian GP | [F1.com DHL Fastest Pit Stop](https://www.formula1.com/en/results/2026/awards/fastest-pit-stops) |
| Pit lane speed limit | **80 km/h (50 mph)**. The Race Director can change it for safety at a given track | [FIA Sporting Regs B1.6.3a](https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf) |
| Speeding penalty | In practice: a fine of €100 per km/h over the limit, up to €1,000. In the race: a time penalty, drive-through or stop-and-go | [FIA Sporting Regs B1.6.3](https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf) |
| Total time lost in the pit lane | Monza ~26 s, Monaco ~24 s, Silverstone ~29.5 s (2026 median, pit entry to exit lines, including the stop) | Our calculation from 2026 race timing via [FastF1](https://docs.fastf1.dev/) |

**2026 DHL fastest stop per race** (stationary time; [F1.com](https://www.formula1.com/en/results/2026/awards/fastest-pit-stops)): Australia Mercedes 2.17 s; China Ferrari 2.29; Japan Ferrari 2.00; Miami Racing Bulls 2.08; Canada Racing Bulls 2.20; Monaco Mercedes 2.17; Barcelona McLaren 2.13; Austria Racing Bulls 2.03; Britain Mercedes 2.18; Belgium Ferrari 2.30; Hungary Racing Bulls 1.99; Netherlands Audi 2.30; Italy Audi 2.44; Spain (Madrid) Mercedes 2.14; Azerbaijan Mercedes 2.33; Bahrain GP (Malaysia) Red Bull 2.09; Singapore Red Bull 2.20.

The 2026 stops are slower than the 1.80 s record. One possible reason is that teams build in more safety margin, but we found no source that confirms the cause.

### 4.5 Rules the game can teach

All from the [FIA 2026 Sporting Regulations, Issue 09](https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf).

- **Unsafe release (B1.6.2):** the team must not send the car out if it could hit another car or a crew member, or with a wheel not properly fitted. A car counts as "released" once its rear axle passes where its front axle stopped. If a car is released in an unsafe condition, for example with a loose wheel, in the race it gets a **stop-and-go penalty** (it must come back, stop for the set time, and leave). In qualifying or practice it gets a **grid drop** for the race. The game can flash "UNSAFE RELEASE!" if the player hits Go before all four guns signal done, or as another car passes.
- **Two dry compounds (B6.3.6):** in a dry race each driver must use **at least two different dry tyre compounds** (for example Medium and Hard). That means at least one stop, unless the driver uses intermediate or wet tyres. Breaking this rule means **disqualification**. A **compound** is the rubber recipe: softer is grippier but wears faster, like a sticky eraser versus a hard one.
- **No powered jacks (B1.6.1d):** the lifting devices must be human-powered.
- **Helmets and eye protection (B1.6.2d):** everyone working on the car at a stop must wear a motorcycle-standard helmet and eye protection.
- **Monaco:** the special two-stop rule used at Monaco in 2025 was scrapped for 2026 ([Motorsport.com](https://www.motorsport.com/f1/news/monaco-scraps-mandatory-two-stop-rule-for-2026-/10801049/)).

### 4.6 Suggested game timing (based on the figures above)

| Player action | Target window | Scoring idea |
|---|---|---|
| Car stopping on its marks (driver brakes at the box) | Stop within ±0.3 m of the line | Missing the mark adds +0.5 s (crew must shuffle) |
| Front and rear jack lift | Press within 0.3 s of the car stopping | Each 0.1 s late adds 0.1 s |
| Nut off (×4 guns) | 0.2 to 0.4 s after jack-up | A "cross-thread" mini-fail on a mistimed press adds +1 to 3 s (a slow wheel, like a real problem stop) |
| Wheel off/on (×4 corners) | Complete by 1.2 s | |
| Nut on (×4) | 1.2 to 1.9 s | Missing it causes a loose wheel. Releasing anyway counts as an unsafe release: penalty screen |
| Drop and green light | Drop at ~2.1 s; green at ~2.2 s | Green while another car passes counts as an unsafe release |
| Driver reaction | ~0.3 s | Display only |

**Score bands:**
- Under 1.80 s: "Beat the world record!" (1.80 s per [Guinness](https://www.guinnessworldrecords.com/world-records/108666-fastest-formula-one-pit-stop))
- 1.80 to 2.2 s: "Race-winning stop"
- 2.2 to 3.0 s: "Solid"
- Over 3 s: "Slow stop: you lost a place"

Add the pit lane time (for example 24 s at Monaco, 26 s at Monza, 29.5 s at Silverstone) to explain why one stop costs a whole lot more than 2 seconds.

---

## 5. ERA TIMELINE SLIDER: spec cards

Each card matches a model picked in [f1_era_models.md](f1_era_models.md).
- **hp** = horsepower. 1 hp ≈ 0.746 kW. Ferrari's "cv" ≈ 0.986 hp.
- Weights before 1995 or so are usually the car *without* the driver. Modern weights include the driver. The cards say which.
- **Top speed** is the hardest number to source for old cars: makers rarely published it, and it changed with gearing at each track. Where no good source exists we say so, rather than repeat internet guesses.
- The **"naturally aspirated"** engine on many cards breathes normal air with no turbo. A **turbo** uses exhaust gas to spin a fan that forces extra air in. A **hybrid** adds an electric motor and battery.

| Era | Card car (model in f1_era_models.md) | Year | Engine | Power | Weight | Top speed | Sources |
|---|---|---|---|---|---|---|---|
| 1950s | Mercedes-Benz W196 R | 1954 | 2.5 L straight-8, naturally aspirated, direct fuel injection | **257 hp (189 kW)** at 8,250 rpm (1954); **290 hp (213 kW)** for 1955 | Gap (not found in an official source) | Gap | [Mercedes-Benz archive 1954](https://mercedes-benz-publicarchive.com/marsClassic/en/instance/ko/Mercedes-Benz-W-196-R-streamlined-racing-car-1954.xhtml?oid=6873); [archive 1955](https://mercedes-benz-publicarchive.com/marsClassic/en/instance/ko/Mercedes-Benz-W-196-R-racing-car-1955.xhtml?oid=6876) |
| 1960s | Ferrari 312 F1-67 (model: "1967 Ferrari 312") | 1967 | 3.0 L (2,989.56 cc) 60° V12, naturally aspirated | **390 hp (287 kW)** at 10,000 rpm | **548 kg (1,208 lb)** with fluids, no driver | Gap | [Ferrari](https://www.ferrari.com/en-EN/formula1/312-f1-67) |
| 1970s | Lotus 72D | 1972 | Cosworth DFV 3.0 L V8, naturally aspirated | **UNVERIFIED:** 405 hp at 9,000 rpm at the DFV's 1967 debut ([Grand Prix Engines](https://www.grandprixengines.co.uk/cosworthstory.pdf)); 440 to 465 hp for the Lotus 72 years ([Wikipedia, citing StatsF1](https://en.wikipedia.org/wiki/Lotus_72)) | Gap | Gap | as listed |
| 1970s (alt) | Ferrari 312T (model: "1976 Ferrari 312T") | 1975 spec | 3.0 L (2,991.8 cc) flat-12, naturally aspirated | **495 hp (364 kW)** at 12,200 rpm | **575 kg (1,268 lb)** | Gap | [Ferrari](https://www.ferrari.com/en-EN/formula1/312-t). Note: Ferrari raced the updated 312 T2 for most of 1976, so label the card "312T (1975)" or "312T family" |
| Late 1970s | Brabham BT46B "fan car" | 1978 | Alfa Romeo 3.0 L flat-12, naturally aspirated | **~520 hp (388 kW)**, secondary source ([Wikipedia, citing StatsF1](https://en.wikipedia.org/wiki/Brabham_BT46)). The rear fan took about 30 hp ([The Race](https://www.the-race.com/formula-1/nine-things-you-may-not-know-about-brabhams-iconic-f1-fan-car/)) | Gap | Gap | as listed. Raced once (1978 Swedish GP) and won ([The Race](https://www.the-race.com/formula-1/nine-things-you-may-not-know-about-brabhams-iconic-f1-fan-car/)) |
| 1980s turbo | Brabham BT52 | 1983 | BMW M12/13 1.5 L 4-cylinder turbo | **~640 hp (477 kW)** in race trim at 2.9 bar boost. BMW says later versions reached up to about 1,400 hp in qualifying | Gap | Gap | [BMW Group press PDF](https://www.press.bmwgroup.com/global/article/attachment/T0299937EN/436963) |
| 1980s turbo (alt) | McLaren MP4/4 (low-poly model) | 1988 | Honda RA168E 1.5 L 80° V6 twin-turbo | **UNVERIFIED:** 685 hp at 12,300 rpm ([Honda](https://global.honda/en/F1/machine/1988_McLarenHondaMP44/)); "at times in excess of 700 bhp" ([McLaren heritage](https://www.mclaren.com/racing/heritage/formula-1/cars/1988-formula-1-mclaren-mp4-4/)); 675 hp ([Wikipedia, citing StatsF1](https://en.wikipedia.org/wiki/McLaren_MP4/4)) | **540 kg (1,190 lb)** without driver ([Honda](https://global.honda/en/F1/machine/1988_McLarenHondaMP44/)) | Gap | as listed. |
| 1990s | Benetton B190 | 1990 | Ford HB 3.5 L V8, naturally aspirated | **~650 hp (485 kW)** at 13,000 rpm, secondary source ([Wikipedia, citing StatsF1](https://en.wikipedia.org/wiki/Benetton_B190)) | **500 kg (1,102 lb)**, UNVERIFIED (same secondary source) | Gap | as listed |
| 2000s | Ferrari F2004 | 2004 | 3.0 L (2,997 cc) 90° V10, naturally aspirated | **865 hp (636 kW)** at 18,300 rpm | **605 kg (1,334 lb)** with driver, water and oil | Gap for the car. For era context, Juan Pablo Montoya reached **372.6 km/h (231.5 mph)** at a 2005 Monza test, and Räikkönen 370.1 km/h (230 mph) in the 2005 Italian GP ([Williams](https://www.williamsf1.com/articles/253b1dc5-aee9-4d3b-b720-8e30f3a83093/how-fast-can-an-f1-car-go)) | [Ferrari](https://www.ferrari.com/en-EN/formula1/f2004) |
| 2009-2013 | Red Bull RB6 | 2010 | Renault RS27 2.4 L V8, naturally aspirated, rev limit 18,000 rpm | **~750 hp (559 kW)** at 18,000 rpm | **620 kg (1,367 lb)** minimum with driver (2010 rule) | Gap | Power: [Renault](https://www.renault.com.gh/discover/MoteurRS272012.html). Weight: [Motorsport.com](https://www.motorsport.com/f1/news/how-much-does-an-f1-car-weigh-in-2023/10437685/) |
| 2014-2021 hybrid | McLaren MP4-31 | 2016 | Honda RA616H 1.6 L V6 turbo hybrid (with MGU-K and MGU-H, two electric motor-generators) | Not published by Honda or McLaren. Gap | **702 kg (1,548 lb)** with driver ([Honda](https://global.honda/en/F1/machine/2016_McLarenHondaMP431/)) | Era context: **372.5 km/h (231 mph)**, Bottas, Williams, Mexico 2016, the official race record ([Williams](https://www.williamsf1.com/articles/253b1dc5-aee9-4d3b-b720-8e30f3a83093/how-fast-can-an-f1-car-go)) | as listed |
| 2022-2025 ground effect | Generic 2022 car ("F1 2022 Generic V3") | 2022-25 | 1.6 L V6 turbo hybrid | **~1,000 hp (746 kW)** class (Aston Martin's figure for its 2025 car) | **798 kg (1,759 lb)** with driver (2022 to 2025; F1.com gives 800 kg for 2025) | Gap (varies by track) | [Aston Martin F1 AMR25](https://www.astonmartinf1.com/en-GB/AMR25); [Motorsport.com](https://www.motorsport.com/f1/news/how-much-does-an-f1-car-weigh-in-2023/10437685/) |
| 2026 active aero | Fan concept ("My take on the 2026 F1 regulations") | 2026 | 1.6 L V6 turbo + one electric motor (MGU-K, no MGU-H), 100% sustainable fuel | **~400 kW engine + 350 kW electric ≈ 750 kW (~1,000 hp)** peak | **768 kg (1,693 lb)** minimum with driver | **342 km/h (213 mph)** in Monza qualifying; **358 km/h (222 mph)** top 2026 speed trap (our calculation from F1 timing via [FastF1](https://docs.fastf1.dev/)) | [FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond) |

**Weight through the years** (minimum weight including driver, per [Motorsport.com](https://www.motorsport.com/f1/news/how-much-does-an-f1-car-weigh-in-2023/10437685/)): 2008 585 kg, 2009 605, 2010 620, 2011 to 2012 640, 2013 642, 2014 691, 2015 to 2016 702, 2017 728, 2018 734, 2019 743, 2020 746, 2021 752, 2022 798. The 2026 car is 768 kg ([FIA](https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond)). This makes a good animated bar on the slider: cars got heavier with hybrid batteries and safety structures, then lighter again in 2026.

**Slider caption ideas:**
- 1954: "A front-engined car on skinny tyres, about a quarter of today's power."
- 1967: "The engine moved behind the driver, and wings were about to appear."
- 1978: "A giant fan sucked the car to the ground. It won its only race and was withdrawn."
- 1983/1988: "Tiny 1.5-litre turbo engines with huge power."
- 2004: "Screaming V10s at 18,000+ rpm."
- 2014: "Hybrids arrive."
- 2022: "Ground effect returns."
- 2026: "Wings that move by themselves and half the power from electricity."

How the 1983/1988 numbers compare to a family car: about 640 to 700 hp from an engine the size of a 1.5-litre city car's (our comparison).

---

## Sources

**Official: FIA and Formula 1**
- FIA 2026 Sporting Regulations, Section B, Issue 09 (1 Oct 2026): https://www.fia.com/system/files/documents/fia_2026_f1_regulations_-_section_b_sporting_-_iss_09_-_2026-10-01.pdf
- FIA 2026 regulations overview: https://www.fia.com/news/new-era-competition-fia-showcases-future-focused-formula-1-regulations-2026-and-beyond
- FIA Malaysia calendar announcement: https://www.fia.com/news/fia-and-fom-confirm-malaysia-will-join-2026-calendar-host-venue-bahrain-grand-prix
- FIA 2026 Italian GP circuit map: https://www.fia.com/system/files/decision-document/2026_italian_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf
- FIA 2026 British GP circuit map: https://www.fia.com/system/files/decision-document/2026_british_grand_prix_-_competition_notes_-_circuit_map_pit_lane_drawing_emergency_exits_map_and_red_zone.pdf
- Formula1.com 2026 calendar and race pages: https://www.formula1.com/en/racing/2026 (each race at /en/racing/2026/{race})
- Formula1.com team pages: https://www.formula1.com/en/teams (each team at /en/teams/{team})
- Formula1.com 2026 key terms: https://www.formula1.com/en/latest/article/explained-the-new-key-terms-for-formula-1s-new-for-2026-rules.3T5BU6TC9quGcIpGzoWkY0
- Formula1.com, why there is no active aero at Monaco: https://www.formula1.com/en/latest/article/explained-why-active-aero-will-not-be-used-at-the-monaco-grand-prix.4nLtpjM9ZTUbPBQLmeAbj4
- Formula1.com circuit guides: [Monza](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-autodromo-nazionale-monza.51PKqBRlxNs0fzLWQzsnd0), [Monaco](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-circuit-de-monaco.vFsmfGHr6RWyLFtxi58wi), [Silverstone](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-silverstone-2026.5Sl0O8g393enBWVIkjRzOr), [Sepang](https://www.formula1.com/en/latest/article/circuit-guide-everything-you-need-to-know-about-the-sepang-international-circuit.2KTLvyxBXmwVftSJxmYeZ2)
- Formula1.com Malaysia announcement: https://www.formula1.com/en/latest/article/formula-1-and-fia-confirm-malaysia-will-join-2026-calendar-as-host-venue-for-the-bahrain-grand-prix.6lL7vjFEM2VVynRHvg1TCf
- Formula1.com pit stop anatomy: https://www.formula1.com/en/latest/article/anatomy-of-a-pit-stop-how-do-f1-teams-service-their-cars-in-less-than-two.5p9LNdd8XJdvP4mRsXoGsB
- Formula1.com DHL Fastest Pit Stop 2026: https://www.formula1.com/en/results/2026/awards/fastest-pit-stops
- Formula 1 Guidelines (trademarks and data use): https://www.formula1.com/en/information/guidelines.4EOKE9RRqevL4niTK9kWyt

**Teams and manufacturers**
- Mercedes, pit stops explained: https://www.mercedesamgf1.com/news/box-box-pitstop-explained
- Mercedes, g-force explained: https://www.mercedesamgf1.com/news/g-force-and-formula-one-explained
- Williams, "How fast can an F1 car go?": https://www.williamsf1.com/articles/253b1dc5-aee9-4d3b-b720-8e30f3a83093/how-fast-can-an-f1-car-go
- Williams, Technical Brief: Great Britain: https://www.williamsf1.com/articles/5df640e6-d376-4422-9de6-000d972c8053/technical-brief-great-britain
- Aston Martin F1, AMR25: https://www.astonmartinf1.com/en-GB/AMR25
- Brembo 2026 braking facts: [Monza](https://www.brembo.com/en/motorsport/formula1/2026/facts-monza-2026), [Monaco](https://www.brembo.com/en/motorsport/formula1/2026/facts-monaco-2026), [UK](https://www.brembo.com/en/motorsport/formula1/2026/facts-uk-2026); 2025 numbers: https://www.brembo.com/en/motorsport/formula1/2025-numbers
- Ferrari heritage pages: [312 F1-67](https://www.ferrari.com/en-EN/formula1/312-f1-67), [312 T](https://www.ferrari.com/en-EN/formula1/312-t), [F2004](https://www.ferrari.com/en-EN/formula1/f2004); SF90 Stradale: https://www.ferrari.com/en-EN/auto/sf90-stradale
- Ferrari SF90 Stradale technical specifications (official sheet, hosted by the Malaysian importer): https://autointernational.com.my/WebNews/News/Year%202020/Ferrari%20SF90%20Stradale%20launch%20-%2023%20Sept%2020/TECHNICAL%20SPECIFICATIONS.pdf
- Mercedes-Benz archive W196: [1954](https://mercedes-benz-publicarchive.com/marsClassic/en/instance/ko/Mercedes-Benz-W-196-R-streamlined-racing-car-1954.xhtml?oid=6873), [1955](https://mercedes-benz-publicarchive.com/marsClassic/en/instance/ko/Mercedes-Benz-W-196-R-racing-car-1955.xhtml?oid=6876)
- BMW Group press, BT52 engine: https://www.press.bmwgroup.com/global/article/attachment/T0299937EN/436963
- Honda F1 machine pages: [MP4/4](https://global.honda/en/F1/machine/1988_McLarenHondaMP44/), [MP4-31](https://global.honda/en/F1/machine/2016_McLarenHondaMP431/)
- McLaren heritage MP4/4: https://www.mclaren.com/racing/heritage/formula-1/cars/1988-formula-1-mclaren-mp4-4/
- Renault RS27 engine: https://www.renault.com.gh/discover/MoteurRS272012.html
- Airbus A320neo: https://aircraft.airbus.com/en/aircraft/a320-family/a320neo
- US Air Force F-16 fact sheet: https://www.af.mil/About-Us/Fact-Sheets/Display/Article/104505/f-16-fighting-falcon/

**Media and reference**
- The Race: [Monaco active aero](https://www.the-race.com/formula-1/why-f1-cars-wont-run-active-aero-in-monaco/); [Brabham fan car](https://www.the-race.com/formula-1/nine-things-you-may-not-know-about-brabhams-iconic-f1-fan-car/)
- Motorsport.com: [Monaco without active aero](https://www.motorsport.com/f1/news/f1-monaco-grand-prix-without-active-aerodynamics-no-reversible-wings-but-will-there-be-any-surprises/10825064/); [Monaco two-stop rule scrapped](https://www.motorsport.com/f1/news/monaco-scraps-mandatory-two-stop-rule-for-2026-/10801049/); [F1 car weights by year](https://www.motorsport.com/f1/news/how-much-does-an-f1-car-weigh-in-2023/10437685/)
- Autosport: [Monaco engine maps](https://www.autosport.com/f1/news/how-the-fia-is-limiting-f1-cars-top-speed-with-new-engine-maps-at-monaco-gp/10825365/); [most successful teams](https://www.autosport.com/f1/news/most-successful-f1-teams-which-team-has-the-most-constructors-titles-5367606/5367606/)
- PlanetF1, Straight Mode zone count: https://www.planetf1.com/news/italian-grand-prix-2026-fia
- The Guardian, Bahrain/Saudi cancellations: https://www.theguardian.com/sport/2026/mar/14/formula-one-cancel-bahrain-saudi-arabia-grand-prix-war-middle-east
- Car and Driver, Corolla Hybrid test: https://www.caranddriver.com/reviews/a41626448/2023-toyota-corolla-hybrid-se-awd-by-the-numbers/
- Guinness World Records, fastest pit stop: https://www.guinnessworldrecords.com/world-records/108666-fastest-formula-one-pit-stop
- US 14 CFR 25.337 (airliner load limits): https://www.law.cornell.edu/cfr/text/14/25.337
- Grand Prix Engines (Cosworth story): https://www.grandprixengines.co.uk/cosworthstory.pdf
- Wikipedia (secondary, used only where marked): [Lotus 72](https://en.wikipedia.org/wiki/Lotus_72), [Brabham BT46](https://en.wikipedia.org/wiki/Brabham_BT46), [Benetton B190](https://en.wikipedia.org/wiki/Benetton_B190), [McLaren MP4/4](https://en.wikipedia.org/wiki/McLaren_MP4/4)

**Data and geometry**
- FastF1 (MIT; unofficial F1 live timing access): https://docs.fastf1.dev/ and https://github.com/theOehrly/Fast-F1
- bacinger/f1-circuits (MIT): https://github.com/bacinger/f1-circuits (licence: https://github.com/bacinger/f1-circuits/blob/master/LICENSE.md)
- OpenStreetMap copyright and ODbL: https://www.openstreetmap.org/copyright and https://opendatacommons.org/licenses/odbl/1-0/
- Sketchfab track models (CC-BY 4.0), linked in section 1.3; licence: https://creativecommons.org/licenses/by/4.0/
- Three.js docs: https://threejs.org/docs/#api/en/extras/curves/CatmullRomCurve3 and https://threejs.org/docs/#api/en/extras/core/Curve

All 107 links were checked on 15 Oct 2026 (MYT) and resolve. Sketchfab and the US Air Force site block simple scripts, so those were confirmed through the Sketchfab API and a browser-style fetch.

---

## Gaps and cautions

1. **Lap-animation numbers are our calculations**, not official. They come from about-4-per-second F1 timing (via FastF1) and are rounded. Braking points are ±25 m and apex speeds ±5 to 10 km/h. Formula 1 owns the timing data: keep the use educational and non-commercial, and ask F1 before any commercial launch.
2. **Straight Mode zone end points** are not printed on the FIA maps. We took the end as the braking point. The Silverstone A1 and A3 end points are our estimates. Zones can change between events and between years, so re-check the FIA event map for each race.
3. **Canada Straight Mode zone count conflicts** (PlanetF1 3 vs Formula1.com 4). UNVERIFIED.
4. **Williams constructors' titles:** F1.com 8 vs Autosport 9. UNVERIFIED.
5. **No official 2026 0-100 / 0-200 km/h figures.** Ours are from race starts with full fuel. **No official 200-0 km/h braking figures** for F1 or the SF90; our estimates are marked UNVERIFIED.
6. **2026 cornering g** has no published figure yet (the 2024 cars reached about 5 g).
7. **Airliner take-off speed and acceleration**: no official A320neo figure found.
8. **Era cards:** top speeds are mostly missing for the older cars. Weights are missing for the W196, Lotus 72D, BT46B and BT52. Secondary sources (Wikipedia/StatsF1) were used for the Lotus 72, BT46B, B190 and as a third MP4/4 value; all are marked. MP4-31 power was never published.
9. **Corner counts** for the six remaining rounds use 2025 timing data. Madring and Sepang counts come from F1.com text, not timing data.
10. **Team details:** Toyota's exact role at Haas is not explained on its F1.com page. Team chiefs can change mid-season, so re-check before launch.
11. **3D track models:** all CC-BY, but some may be ported from games. Check each model's description and remove sponsor textures. No CC0 tracks were found.
12. **bacinger GeoJSON** was originally traced from a Google My Maps layer. It is fine for outlines, but it is not survey grade, and it has no per-point elevation.
13. **The 2026 season is in progress** (17 of 23 rounds done on 15 Oct 2026). Results, fastest pit stops and team titles will change.

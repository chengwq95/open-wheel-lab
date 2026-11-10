# Inside the Machine: How an F1 Car Works

You are a motorsport engineering research assistant. I am building an interactive HTML website about Formula 1 cars, with 3D visualization built in Three.js. The site is for a general audience, so explanations must be accurate but easy for non-experts to understand. Please research and organize the material below so I can use it directly in development.

## Audience & writing style

- Write in clear, simple English. Assume the reader has never watched F1.
- For every technical term, give a one-sentence plain-language explanation (e.g. "Downforce: air pushing the car down onto the track, like an upside-down airplane wing").
- Where helpful, include an everyday comparison (e.g. "the brakes reach temperatures hotter than a pizza oven").
- Keep each component or era summary to 2–4 short sentences, plus an optional "Fun fact."

## Part 1: Car overview (for the 3D model)

1. Focus on the current 2026-regulation car. List key dimensions: length, width, wheelbase, minimum weight, tyre/wheel size, and ride height (if available).
2. Summarize the main visual differences from the 2022–2025 cars (smaller and lighter, active aerodynamics, etc.).
3. Find 3D model resources suitable for Three.js:
   - Prefer glTF/GLB format.
   - Prefer models where components are separate meshes (so they can be animated apart in an exploded view).
   - Note polygon count and file size if listed (the site should run on mid-range laptops and phones).
   - Record the license (CC0, CC-BY, etc.), author, and download link. Only include models whose license allows use on a public website.
   - Exclude models with real team liveries, sponsor logos, or trademarks.
4. If no suitable full model exists, list good references (official technical drawings, blueprints, or diagrams) that could help me build a simplified model myself.

## Part 2: Exploded view / teardown

For each component below, provide: name, location on the car, what it does (in plain language), main materials, approximate size or weight, and one fun fact.

- Survival cell / monocoque
- Front wing
- Rear wing and active aerodynamics system (and how it replaces DRS)
- Floor and Venturi tunnels (ground effect)
- Sidepods and cooling system
- Power unit: internal combustion engine, MGU-K, energy store (battery), control electronics
- Gearbox
- Suspension (push-rod / pull-rod)
- Brakes (carbon-carbon discs, brake-by-wire)
- Tyres (slick compounds, intermediates, full wets)
- Halo
- Steering wheel (main buttons and what they do)

Also suggest:

- A logical order for separating parts in an exploded-view animation.
- The direction each part should move (up, forward, sideways, etc.) so the animation looks clear and parts don't overlap.

## Part 3: History

1. A timeline from 1950 to today, grouped by era. For each era: major rule changes, signature innovations, notable cars (name and year only), and key safety improvements.
2. Highlight these milestones: mid-engine layout, wings, ground effect (1970s–80s and its 2022 return), the turbo era, active suspension, semi-automatic gearboxes, the hybrid era, introduction of the Halo, and the 2026 regulations.
3. Major safety incidents and the rule changes they led to. Keep the tone factual and respectful.
4. For each era, describe the typical car shape in simple terms (useful for a "then vs now" comparison feature).

## Part 4: Engines / power units

Create a comparison table with these columns:

| Years | Displacement | Cylinders & layout | Turbo? | Max RPM | Approx. horsepower | Hybrid components | Fuel rules | Notable manufacturers | Sound character |
|---|---|---|---|---|---|---|---|---|---|

Cover at least: early naturally aspirated engines, the 1980s turbo era, V10, V8, the 2014–2025 V6 turbo-hybrid (including MGU-H), and the 2026 regulations (MGU-H removed, roughly 50/50 combustion-electric power split, 100% sustainable fuel).

Also:

- List the 2026 power unit manufacturers and which teams they supply.
- Explain in plain language how energy recovery works (braking → battery → extra power), suitable for an animated diagram.

## Sources & accuracy

1. Cite a source link for every figure. Prioritize the FIA technical regulations, Formula1.com, official team/manufacturer sites, and respected technical media (e.g. The Race, Motorsport.com technical articles).
2. If a figure cannot be confirmed or sources disagree, mark it "UNVERIFIED" and list the different values with their sources.
3. Use metric units, with imperial in brackets where useful (e.g. 340 km/h (211 mph)).
4. Summarize in your own words; do not copy long passages from sources.

## Output format

- Organize the output into the four parts above, using headings.
- Use tables where data is comparable (dimensions, engines, timeline).
- End with a full source list and a short "Gaps & open questions" section noting anything you couldn't find.

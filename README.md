# Open Wheel Lab

An interactive guide to Formula 1 cars for people who are curious about the sport. Turn a car around in 3D, take it apart, explore how its shape changed, ride a circuit lap and try a pit stop challenge. Available in **English and Chinese**.

**Live:** [open-wheel-lab.pages.dev](https://open-wheel-lab.pages.dev/) · [opensirius.com](https://opensirius.com/)

## Features

- **3D car exhibit:** rotate and zoom, select components, switch views and explore an exploded view.
- **Aerodynamics and 2026 rules:** plain-language explanations of wings, downforce, drag and active aero.
- **Historical garage:** representative cars across eras, with model previews and specification cards.
- **Circuit laps:** Monza, Monaco, Silverstone and Sepang, with speed, gear, battery and wing-mode displays.
- **Power and teams:** power-unit explanations and team reference cards.
- **Comparison tools:** compare cars and other vehicles, including an animated acceleration demonstration.
- **Pit stop challenge:** an interactive timing game with feedback.
- **Learning tools:** a glossary, quizzes, sources, language switching and light/dark themes.

The 3D cars are educational study models. Internal mechanics, shapes and lap animations include simplified or estimated elements; see the explanations and citations on the site.

## Run locally

No build step or package installation is required. Use Python 3 to serve the published website:

```sh
python3 -m http.server 8000 --directory site
```

Open [localhost:8000](http://localhost:8000/). Stop the server with `Ctrl+C`.

`site/` contains the ready-to-publish website, including local Three.js libraries, previews and the social sharing image. The page includes CDN fallbacks and uses Google Fonts, so this is not a fully offline package.

## Repository layout

```text
site/                    Published website; Pages serves this directory
  index.html             Website entry point
  og.jpg                 Social sharing image
  assets/                Three.js, controls, environment helper and car previews
open-wheel-lab.html       Standalone prototype entry point
assets/                  Assets used by the prototype
md/                      Research notes, sources and project handoff
html/                    Styled research documents
json/                    Supporting circuit-lap data
promo/                   Promotional drafts and screenshots
README.md                Project overview and publishing instructions
```

The repository retains the supplied research and promotional files. Only `site/` is deployed to the public website. Edit `site/index.html` and its assets for live-site changes; the root prototype is retained separately.

## Cloudflare Pages

This repository is connected to the existing **open-wheel-lab** Pages project. Its Pages address and custom domains remain attached to that project.

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | None |
| Build command | `exit 0` |
| Build output directory | `site` |
| Root directory | Repository root |

Commits to `main` trigger production builds once Git integration is connected. Check the deployment result in the [Cloudflare dashboard](https://dash.cloudflare.com/0f39473a951f5f8e54437832b535da23/pages/view/open-wheel-lab).

Before publishing, open the local site and check the 3D views, historical-car switching, circuit controls, language switch and pit stop game. Keep every referenced file inside `site/`.

## Sources and third-party material

This is an unofficial educational fan project, with no affiliation to Formula 1, the FIA or any team. Names and trademarks belong to their respective owners.

- Site citations appear in the **Sources** section; research notes also contain source lists and uncertainty notes. Season-specific information should be checked before reuse.
- Three.js and its bundled helpers retain their MIT licence notice in [`site/assets/THREE-LICENSE.txt`](site/assets/THREE-LICENSE.txt) and [`assets/THREE-LICENSE.txt`](assets/THREE-LICENSE.txt).
- Circuit shapes are credited on the site to the MIT-licensed `bacinger/f1-circuits` dataset. Lap figures and simulations are described on the site; they are not official telemetry.
- Research links to external 3D models do not mean those models are bundled or licensed with this repository. Check each original licence before downloading or reusing it.

No blanket licence is added for the project's original content. Third-party licences continue to apply to their respective files.

# Free F1 / open-wheel 3D models by era (researched 2026-10-15)

Method: Sketchfab API (downloadable=true), with every pick checked against /v3/models/{uid}. All page URLs returned HTTP 200. Faces = triangles reported by Sketchfab. GLB size = Sketchfab's auto-converted glTF archive (MB, rounded down; 0 = under 1 MB). Every Sketchfab download includes an auto-converted glTF/GLB. **All picks are CC-BY 4.0**, so credit the author and link the model on the site. The "Separate parts?" column was **not verified**. Sketchfab models usually have several meshes/materials (body, wheels, wings). Open the GLB in gltf.report or Blender to confirm.
**Trademarks:** CC-BY covers the author's copyright only. Real car designs, team liveries, sponsor logos and the F1 name/logo are third-party trademarks. For a general public site, retexture to a neutral livery and remove decals (tobacco/alcohol logos especially).
Excluded: CC-BY-NC/ND and Sketchfab "Free Standard" items (e.g. Lotus 72D by 7093, Greg Bennett FA1), plus anything not downloadable.
Other sources: Poly Pizza, Poly Haven, Kenney and Quaternius have no era-specific F1 cars. Kenney's Car Kit and Quaternius's car packs (CC0) include generic race cars that can serve as a stylised fallback. CGTrader/TurboSquid free items are usually Royalty-Free or Editorial, not CC, so they're excluded unless reviewed one by one. Thingiverse/Printables have many STL F1 models (often NC). Not reviewed individually.

## 1950s front-engine (cigar)
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| Mercedes-Benz W196 | https://sketchfab.com/3d-models/mercedes-benz-w196-bc9f149fce8d449a988e5039f4da97cd | The_Nuke_Remolacha | CC-BY | glTF/GLB | 377k | 84 MB | likely | Mercedes star, race number | Heavy. Decimate to ~80k and compress textures (KTX2/WebP) |
| Ferrari "156 F1 1950" (Taruffi; actually a 1950s front-engine Ferrari) | https://sketchfab.com/3d-models/piero-taruffi-ferrari-156-f1-1950-da3d129d97a24c32854b6b232e814642 | haryaabima_visualgarage | CC-BY | glTF/GLB | 1.2M | 53 MB | likely | Ferrari badge | Too heavy without major decimation |
**Fallback:** no light model exists. Either decimate the W196 or build a simple cigar body (lathe geometry + 4 wire wheels) in Three.js/Blender. This shape is easy to model procedurally.

## 1960s mid-engine
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| 1967 Ferrari 312 | https://sketchfab.com/3d-models/1967-ferrari-312-105683345dbb441a8b28b71b713f2110 | Tyler_Dave | CC-BY | glTF/GLB | 78k | 7 MB | likely | Ferrari red, badges | **Best pick.** Light enough for mobile |
| Lotus 49C (1970 spec, small wings) | https://sketchfab.com/3d-models/formula-1-lotus-49c-d08e707e8d4442469f3bfacd5d5d3441 | dark_igorek | CC-BY | glTF/GLB | 300k | 56 MB | likely | Gold Leaf tobacco livery: retexture | High quality, desktop only unless optimised |

## Late-60s / 70s winged
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| 1972 Lotus 72D | https://sketchfab.com/3d-models/1972-lotus-72d-3b1fafbc153746aebad4a245f4acdd52 | Tyler_Dave | CC-BY | glTF/GLB | 33k | 3 MB | likely | JPS tobacco livery: retexture | **Best pick**, very light |
| 1976 Ferrari 312T | https://sketchfab.com/3d-models/1976-ferrari-312t-b82c13cee0d24966ae66d0324ac12054 | Tyler_Dave | CC-BY | glTF/GLB | 74k | 5 MB | likely | Ferrari and sponsor logos | Good |

## Late-70s / 80s ground effect & turbo
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| 1978 Brabham BT46B "fan car" | https://sketchfab.com/3d-models/1978-brabham-bt46b-18e99a321aca4670a56659b498a2236d | Tyler_Dave | CC-BY | glTF/GLB | 126k | 15 MB | likely | Parmalat livery | Good. Iconic ground-effect story |
| 1983 Brabham BT52 (turbo) | https://sketchfab.com/3d-models/1983-brabham-bt52-fb5eb650f4584192bf7d6b25d39d3688 | Tyler_Dave | CC-BY | glTF/GLB | 151k | 17 MB | likely | Parmalat livery | Good. Compress textures |
| McLaren MP4/4 low-poly | https://sketchfab.com/3d-models/f1-mclaren-mp44-e070ee4c8c1b4ac88963e1d27125423d | ezgibakim | CC-BY | glTF/GLB | 19k | <1 MB | check | Marlboro-style colours? | Ultra-light alternative |

## 1990s
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| 1990 Benetton B190 | https://sketchfab.com/3d-models/1990-benetton-b190-058b376937df4eb88193f3024bf6455d | Tyler_Dave | CC-BY | glTF/GLB | 67k | 8 MB | likely | Benetton/sponsor logos | **Best pick** |
| Williams FW16 + driver | https://sketchfab.com/3d-models/williams-fw16-ayrton-senna-ba86f97de7184b6b836458815897156f | GRIP420 | CC-BY | glTF/GLB | 71k | 11 MB | likely | Rothmans livery **and a real person's likeness**: retexture and drop the figure | Fine once the figure is removed |

## 2000s V10
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| McLaren MP4/19B low-poly | https://sketchfab.com/3d-models/mclaren-f1-mp419b-lowpoly-322d7355a54b409baaea32e915fb5f74 | luis.adrian.designs3D | CC-BY | glTF/GLB | 41k | 2 MB | check | McLaren/West livery | **Best for mobile** |
| 2004 Ferrari F2004 | https://sketchfab.com/3d-models/2004-ferrari-f2004-827e64acecba4f008759ae30a5bfeecc | Tyler_Dave | CC-BY | glTF/GLB | 263k | 14 MB | likely | Ferrari and sponsor logos | Desktop quality |

## 2009–2013 V8
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| Red Bull Racing RB6 (2010) | https://sketchfab.com/3d-models/red-bull-racing-rb6-7ba1ee5ca7544e46b6a652b4186f11b6 | CasacadeOperations | CC-BY | glTF/GLB | 53k | 3 MB | check | Red Bull livery | **Best pick** |
| 2010 Red Bull X2010 (game concept, not a real F1 car) | https://sketchfab.com/3d-models/2010-redbull-x2010-093eb21a4cf64cefb560d2cf4691cf3d | Tyler_Dave | CC-BY | glTF/GLB | 42k | 4 MB | check | Red Bull | Not era-accurate. Avoid as the main example |

## 2014–2021 hybrid
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| 2016 McLaren MP4/31 | https://sketchfab.com/3d-models/2016-mclaren-mp431-9ae094da549849659a5964f6a6baf0aa | Tyler_Dave | CC-BY | glTF/GLB | 31k | 3 MB | likely | McLaren/Honda logos | **Best pick** |
| Formula 1 car – RS19 (Renault 2019) | https://sketchfab.com/3d-models/formula-1-car-rs19-711cbe7f1ee84188bbf77a948003a68a | oliwer.andersson | CC-BY | glTF/GLB | 41k | 1 MB | check | Renault colours | Light alternative |

## 2022–2025 ground effect
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| F1 2022 Generic V3 | https://sketchfab.com/3d-models/f1-2022-generic-v3-reuploaded-from-theodevf1-55c119e7096a4322bc375c9b4f5a162d | DaniFold (orig. TheoDevF1) | CC-BY | glTF/GLB | 313k | 11 MB | likely | Generic, no team livery | **Best pick (no trademarks)**. Decimate for phones. Reupload: credit both authors and confirm the original was also CC-BY |
| F1 Mercedes W13 Concept | https://sketchfab.com/3d-models/f1-mercedes-w13-concept-b9e85594aec847f78883343d67ee97fb | nickbroad | CC-BY | glTF/GLB | 100k | 44 MB | likely | Mercedes/Petronas | Big textures. Resize them |

## 2026
| Name | Link | Author | License | Format | Faces | GLB size | Separate parts? | Livery/logo notes | Suitability |
|---|---|---|---|---|---|---|---|---|---|
| My take on the 2026 F1 regulations | https://sketchfab.com/3d-models/my-take-on-the-2026-f1-regulations-4b77c9b72dc44803a530eaaff18ed590 | MaG80 | CC-BY | glTF/GLB | 206k | 8 MB | likely | Generic concept | **Best pick** (fan concept) |
| F1 2026 Release Car (author marks it outdated/inaccurate) | https://sketchfab.com/3d-models/f1-2026-release-car-outdatedinaccurate-b5c4f3ef041345c68b8e918190d32a9c | Nimaxo | CC-BY | glTF/GLB | 206k | 7 MB | likely | Generic | Alternative |

## General optimisation
Run `gltf-transform optimize in.glb out.glb --compress draco --texture-compress webp` and decimate to roughly 30–80k triangles per car. Load one car at a time. A generic fallback: "( FREE ) Formula One LP-830 SDC" by Lambo_SC04 (CC-BY, 31k faces, 2 MB) at https://sketchfab.com/3d-models/free-formula-one-lp-830-sdc-aeebdfa53e294e0390f3c2e8bbfe31b6

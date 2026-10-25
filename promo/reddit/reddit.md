# Reddit posts

Link to use everywhere: https://open-wheel-lab.pages.dev
Read each subreddit's rules before posting. Post in one or two subs a day, not all at once (posting the same thing everywhere in one go can get flagged as spam).
Reply to every comment in the first hour or two. On Reddit that matters more than the post itself.

=====================================================================
1. r/SideProject   (Text post. Optional image: 03_take_apart.jpg)
=====================================================================

Title:
I made a free interactive guide to the F1 car: take a 2026 car apart in 3D, ride a lap of Sepang, try a pit stop game

Body:
F1 came back to Sepang (Malaysia) this month for the first time since 2017. Friends watching with me kept asking the same things: what do all the parts do, why do they have to pit, what changed for 2026. So I made a site that answers all of it in one place.

https://open-wheel-lab.pages.dev

What's in it:
- A 3D 2026 car you can rotate and take apart (14 parts, each with a plain-English explanation)
- 12 study models from 1950 to 2026 at the same scale, with the 2026 car as a ghost outline
- A lap of Sepang with live speed, gear, braking and battery, plus Monza, Monaco and Silverstone
- F1 vs Ferrari SF90 vs Toyota Corolla, race to 200 km/h
- A pit stop reaction game (the real record is 1.80 s)
- English and Chinese, works on mobile, no sign-up, no ads, sources listed for every number

How it was made: I'm not a professional developer. I built it together with Claude (code and design) and Grok (research). My job was deciding what it should be, testing everything and asking for a lot of changes. It's a single HTML file on Cloudflare Pages.

I'd really like feedback. What's confusing, what's wrong, and what would you add next?

=====================================================================
2. r/threejs   (Text or image post. Image: 03_take_apart.jpg)
=====================================================================

Title:
Procedural F1 cars in three.js: no model files, every car built from code (12 eras + a take-apart 2026 car)

Body:
https://open-wheel-lab.pages.dev

There are no GLTF or OBJ files. Every car (a 2026 car plus 12 era study models from 1950 to 2026) is generated at runtime from a small spec: bodies are lofted from superellipse cross-sections, wings are NACA-style airfoils extruded along the span with a bit of bend and sweep, plates use rounded, bevelled shapes, and the suspension arms anchor to the body surface at each station.

"Take it apart" moves 14 part groups along their own directions in a staged order, and the older eras can be exploded too. Everything is three.js r128 with OrbitControls and RoomEnvironment, in one HTML file.

Made with a lot of help from Claude. I'd love feedback on the look of the models, especially what makes them read as "toy" and what would make them feel more real.

=====================================================================
3. r/webdev   (Only as a comment in the weekly "Showoff Saturday" thread)
=====================================================================

Open Wheel Lab: an interactive guide to the F1 car. 3D take-apart car, 12 eras of cars at the same scale, a Sepang lap sim and a pit stop game. One HTML file, three.js, English and Chinese, hosted on Cloudflare Pages. Built with Claude as my coding partner. Feedback welcome, especially on mobile.
https://open-wheel-lab.pages.dev

=====================================================================
4. r/malaysia   (Optional. Casual. Check the rules on self-promotion first)
=====================================================================

Title:
F1 came back to Sepang after 9 years, so I made a little site about the car

Body:
Still not over seeing F1 cars on those two Sepang straights again. I made a free site that explains the car: a 3D 2026 car you can take apart, a lap of Sepang with speed, gear and braking, 76 years of F1 cars side by side, and a pit stop game. English and Chinese, works on phone, no ads.

https://open-wheel-lab.pages.dev

Built with help from Claude and Grok. Tell me what to add next.

=====================================================================
Avoid
=====================================================================
- r/formula1: self-promotion is usually not allowed in normal posts. If at all, only in the daily discussion thread, and check the rules first.
- r/F1Technical: strict about accuracy and promotion. Skip unless you're ready for detailed technical criticism.
- Don't use the 1.40 s score as bait on Reddit. People there will check, and "my best is 1.40 s" from the site's own developer reads as fake.

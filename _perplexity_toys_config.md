# Digital Toys: as builder of first prototype

This file perplexity_toys_config.md attached contains instructions on how to design, critique, and revise an accompanying HTML/JavaScript digital toy.

A digital toy is an essay you can grab by the handle. It makes a single physical or mathematical point, has knobs that let the reader feel where the point breaks, and earns its closing line. It is not a simulation — the word "simulation" promises a faithfulness to reality that browser code cannot deliver and that the reader does not need. A toy promises something smaller and more honest: a working model, scaled to fit on a screen, with the lies clearly marked.

Save revised toy code to /Users/furnival/Documents/PerplexityFiles/revised_toy_draft.html

---

# 1. The Animating Principle

A toy is an essay with knobs.

The text in the page must say something — a single claim, defensible in one sentence. The knobs must let the reader test where that claim is true and where it isn't. If a slider exists only to be moved, cut it. If a number is displayed only to look technical, cut it. Every control earns its place by changing what the reader believes.

**The opening is everything.** Within ten seconds of the page loading the reader must (a) see motion, (b) read one line that names what is happening, and (c) understand what at least one control does. If any of these is missing, the toy fails before it begins. Hacker News readers are generous with intelligence and stingy with patience.

**The verdict is everything else.** The last line on the page — under the canvas, in slightly subdued type — must name the lesson. Not summarize the controls. Not credit the math. Name the thing the reader now knows that they did not know before opening the tab. This is the toy's equivalent of McPhee's closing paragraph: earned, quiet, and devastating in its smallness.

---

# 2. Scenarios as Guided Readings

Sliders alone are a maze. The reader does not know which corner of the parameter space is interesting and will give up before finding it. The fix is preset buttons — three to five — each named for a viewpoint, not for a number.

Wrong: `Case 1`, `Case 2`, `High Drag`
Right: `The Cassini Plunge`, `The Lazy Spiral`, `Tether at 120 km`

Each preset is a tiny essay: a configuration that argues something. When the reader presses the button the toy snaps to that argument and the verdict line below the canvas updates to say what the argument is. Presets are the toy's table of contents. They reward exploration and they rescue the reader who would otherwise wander.

**Rule:** never label a preset with a number. Always label it with a stance.

---

# 3. Honest Defaults

The toy lands on a default state when the page loads. That state is the strongest claim the toy can make. Choose it deliberately. If the toy is about why air-breathing scoops fail above 140 km, the default is 140 km — not the midpoint of the slider, not the value that looks prettiest, but the value that makes the reader say *oh*.

Sliders should reveal physics, not hide it. If a parameter has a natural log scale (orbital semi-major axis, atmospheric density, tether length spanning 20–2000 km), use a log scale and label it as such. A linear slider across four orders of magnitude is a lie told for the sake of convenience.

When a slider has a sweet spot — a value where the physics balances — show it live as the slider moves. A small annotation beneath the slider reading `ideal ≈ 117 km` is worth a paragraph of explanation.

---

# 4. Animation as Argument

Animation is not decoration. Either it carries the point — orbital motion, atmospheric heating, the moment a scoop ignites — or it is noise. If the same insight survives a static screenshot, the animation is failing.

**The minimal control set:** Pause. Speed (0.25× to 4× is enough). Reset. Anything more is usually a confession that the toy is doing too much.

**Time compression must be labeled.** A caption near the canvas reading `one orbit = 5,400 s real / 3.2 s shown` saves the reader from the silent confusion of watching something move at the wrong speed and not knowing why. Mistrust any animated toy that does not declare its time base.

**Trails fade.** A particle trail of sixty points with decaying alpha makes an orbit shape readable in a way that a single dot cannot. But the trail must die — a permanent trail accumulates into a smear that hides the present moment.

**Use `requestAnimationFrame` with dt-based phase advance.** Never advance state by a fixed step per frame. The reader on a 120 Hz display should see the same physics as the reader on a 60 Hz laptop.

---

# 5. Color as Physics

Color is a second axis. Spend it carefully.

Reserve red, yellow, green for chemistry — combustion regimes, stability regions, thermal limits. Reserve blue for cool quantities — altitude, depth, distance. Reserve white or pale yellow for emissive features — the moment a particle enters atmosphere, the instant of capture, the flash of ignition.

A color legend is not optional. If a particle is red, the reader needs to know — within the page, not in a tooltip — that red means velocity above 5 km/s, or whatever the regime is. The legend is part of the essay.

**Dark mode is the default.** Geek-minded readers run dark themes; their eyes adapted half an hour before they opened the tab. A toy that ships in white blinds them and signals that the author has not thought about the audience. Use `#0a0a0a` or near-black as the canvas; choose foreground colors that hold their identity against it.

---

# 6. Visual Hierarchy

The page has four zones and they should never compete:

1. **The title.** One line. Names the toy.
2. **The canvas.** Where the physics lives. As large as the layout allows.
3. **The controls.** Beside or below the canvas, grouped by what they affect.
4. **The verdict.** Below everything else, in subdued type. The one line the reader leaves with.

Resist the temptation to add a fifth zone for credits, links, or a longer explanation. If the longer explanation is necessary, the toy is incomplete. If credits are necessary, put them in the page source as a comment — geeks read source.

Typography: a single sans-serif for UI, a single monospace for numbers. Numbers in monospace look like numbers; numbers in proportional type look like opinions.

---

# 7. The Iron Rules

These are absolute. Flag any violation.

1. **No fake numbers.** If a quantity is derived, derive it from the constants the toy actually uses. Never display a value that looks calculated but is hard-coded.
2. **Label every unit.** km, km/s, kg/m³, seconds. A unitless number on a technical page is a small betrayal of the reader.
3. **Source the constants.** A short comment at the top of the script naming where the atmospheric density profile, the gravitational parameter, or the drag coefficient came from. The reader who looks at source — and they will look — should find honest provenance.
4. **The math fits in the head.** A toy whose underlying equation cannot be stated in two lines is too big. Split it or shrink it.
5. **No analytics, no fonts from CDNs, no telemetry.** A toy that phones home is not a toy. It is a product.

---

# 8. Recurring Pitfalls (Personal)

Failure modes specific to this builder's process. Flag these when they appear in drafts.

**In the design phase:**

- **The dashboard trap.** Building a panel of fifteen readouts because each one seemed interesting. A toy is not a dashboard. One claim, three or four knobs, one verdict.
- **Simulating instead of arguing.** Trying to be faithful to every physical effect rather than choosing the one that carries the point. Faithfulness is the enemy of clarity. The toy is a cartoon with rigor where rigor matters.
- **Premature visual polish.** Tuning gradients before the physics is honest. The first version must be ugly and correct.

**In the build phase:**

- **The orphan slider.** A control that exists because the parameter exists in the equation. If moving it does not change what the reader believes, cut it.
- **The silent failure.** A toy that quietly renders nonsense when pushed past a regime boundary. Either constrain the slider or print a warning in the canvas.
- **Visual scale ≠ physical scale, unstated.** Drawing an atmosphere 50 km thick at the same pixel scale as an orbit 6,000 km up. Either label the scale exaggeration explicitly, or use two panels at different scales and say so.

**In the polishing phase:**

- **The lecture creep.** Adding paragraphs of explanatory text inside the page. The verdict is one line. If the toy needs three paragraphs to explain itself, the toy is wrong, not the explanation.
- **Animation for its own sake.** Spinning a logo, fading in a panel, easing a slider handle. If the motion is not physics, delete it.
- **The forgotten mobile reader.** Hacker News opens on phones. The toy need not be perfect there, but it must not be broken there. Test once at 375 px wide.

---

# 9. The Strunk/White Scan, Applied to Code

Perform a step-by-step scan of the HTML/JS for redundancy in the *Elements of Style* sense. Confirm each deletion with me.

- Variables named `tempValue`, `data1`, `result` that could carry the physical name (`vRel`, `rhoAlt`, `qHeat`).
- Comments that restate what the code says (`// increment i by one`). Cut.
- Inline styles repeating what a class already does.
- Three div wrappers where one would hold the layout.
- A library imported for a single function that is twelve lines of vanilla JS.

A toy that loads in under 100 KB, including its own fonts, with no dependencies, signals seriousness. The reader notices.

---

# 10. Reference Shelf: Builders to Study

Builders to read for technique, not subject matter. Each entry notes the specific craft quality worth stealing. Read the source. Read the source again. Then close the tab and build something smaller.

| **Builder**                          | **Work**                                                                                         | **What to Study**                                                                                                                                                                                                                                                       |
|:------------------------------------:|:------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| **Bret Victor**                      | *Up and Down the Ladder of Abstraction*; *Kill Math*; *Explorable Explanations* (worrydream.com) | The founding texts. Direct manipulation, immediate response, the reader as co-author of the argument. Every toy on this list descends from these essays.                                                                                                                |
| **Bartosz Ciechanowski**             | *Internal Combustion Engine*; *GPS*; *Gears*; *Bicycle* (ciechanow.ski)                          | The gold standard for explanatory toys. Every interactive carries a single physical insight; the prose around it is dense but never overwrites the diagrams. Study the restraint: no preset buttons, no flashy controls — just direct manipulation of the thing itself. |
| **Nicky Case**                       | *Parable of the Polygons* (with Vi Hart); *The Evolution of Trust*; *Loopy*                      | The toy as moral argument. Preset scenarios as guided readings. How a playful interface can carry weight that a paper cannot.                                                                                                                                           |
| **Steve Wittens**                    | *How to Fold a Julia Fractal*; *Animate Your Way to Glory* (acko.net)                            | Visual mathematics rendered without apology. Color as physics. The animated derivation as an essay form.                                                                                                                                                                |
| **Distill.pub**                      | *Why Momentum Really Works* (Goh); *A Visual Exploration of Gaussian Processes*                  | Typography and layout standards for technical interactives. The model for how text, math, and code share a page without fighting.                                                                                                                                       |
| **Matt Henderson**                   | Twitter/X experiments; CodePen demos                                                             | Tiny, complete, often a single canvas. The discipline of one idea per artifact. The willingness to ship something at 100 lines and stop.                                                                                                                                |
| **Sebastian Lague**                  | YouTube; *Coding Adventures*; geometry and pathing videos                                        | Geometric intuition built up from primitives. How to introduce a hard concept by first showing its degenerate, trivial case and adding complexity one step at a time.                                                                                                   |
| **Tomorrow Corporation**             | *Human Resource Machine*; *7 Billion Humans*                                                     | Aesthetic discipline at the interface level. Limited palette, generous whitespace, no decorative motion. The toy looks like a tool because it is a tool.                                                                                                                |
| **three.js examples**                | threejs.org/examples                                                                             | A negative example as much as positive: study which of these examples carry an idea and which are pure technique. Most are technique. The ones that aren't are gold.                                                                                                    |
| **Andy Matuschak / Michael Nielsen** | *How can we develop transformative tools for thought* (numinous.productions)                     | The frame around the field. Why these objects matter, what they are not yet, and what one is reaching for when building one.                                                                                                                                            |

**A note on use:** Read these to notice, not to imitate. When a Ciechanowski diagram makes a concept inevitable, stop and ask which design choice did the work — was it the direct manipulation, the labeling, the restraint of the surrounding prose? When a Nicky Case preset button reframes the toy in a sentence, copy the structure, not the words. Steal the technique, not the voice.

---

# 11. The Closing Line

The toy ends with one sentence below the canvas. It should be concrete, specific, and slightly understated. A reader who came for a slider should leave with a sentence they can quote.

**Examples of the register:**

- *Above 140 km the air is too thin to scoop and too thick to ignore.*
- *The tether trades fuel for cable; the cable is heavier than you think.*
- *Every elliptical pass through atmosphere is a coin flip the spacecraft is required to win.*

Avoid: *This simulation demonstrates...*  *As shown above...*  *In conclusion...*  These are the toy equivalents of throat-clearing. The reader who has played with the toy does not need to be told what was shown.

---

-- Lawrence Furnival
   first draft, May 30, 2026 @ Hamden, Connecticut

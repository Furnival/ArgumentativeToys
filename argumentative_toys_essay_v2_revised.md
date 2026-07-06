# Argumentative Toys

### An Invitation to Essays That Bite Back

---

Try this. Somewhere on this page a tether is turning, a cable a few kilometers long, hauling a small payload up to a higher orbit by spending its own altitude to do it. There is a slider. Push it. Ask the cable for a little more lift than it wants to give, and then a little more, and watch what the universe charges you for the favor. You did not come here to be taught how an electrodynamic tether works — a tether is just a long conducting wire that drags against Earth's magnetic field, trading the satellite's speed for a slow, free fall home. You came to find out how far you can push before the thing burns. That is a different kind of page, and I want to give it a name and hand you the tools to make your own.

I call it an **Argumentative Toy**: an essay you can grab by the scruff. The knobs let you feel the trade-off and find the place where it fails. It is not a simulation — a single web page cannot be faithful to the whole of reality, and it should not pretend to be. It is a toy, but an honest one, with its lies clearly marked.

Sliders alone, though, are a maze. A reader who is handed a fistful of controls and no path will wander and leave. So an Argumentative Toy needs presets — three to five, no more — and each preset is a tiny argument in its own right, labeled as such. The presets are the toy's table of contents; put them near the top where they can be seen. They reward exploration and rescue the reader who would otherwise get lost.

An example earns its keep here. One trouble we — the Earth — are walking into is that the planned orbital constellations may pollute the upper atmosphere badly as their satellites burn up. How to deorbit an aging satellite is a genuine trade-off. What should a responsible, deorbitable satellite carry: fuel for a controlled burn, or a trailing tether that drags against Earth's magnetic field to bleed off speed? It depends on the satellite's mass and how high it flies. Take a look.

[example file:///Users/furnival/Documents/PerplexityFiles/revised_toy_draft.html]

That is the argument. Not "here is how an electromagnetic tether works," but a claim the toy lets you test for yourself: *in this model, the clever tether helps most with the small cubesats, and earns its keep less and less as the satellite grows.* You did not read that and nod. You pushed a slider too far, and the conviction became yours.

So this is an invitation, not a manifesto. The form is cheap, it belongs to no one, and the world has more hidden trade-offs than any one person could ever build for. I want company in this. Here is what I have learned about how the genre works, and where it sits among the interactive pages it resembles but is not.

---

## The word I had to give up

I almost called these *simulations*, and I am glad I didn't. The reason is the spine of the whole idea.

"Simulation" promises faithfulness — that the thing on your screen is a small true copy of the world, and that what it shows you, the world will too. Browser code cannot keep that promise. The tether toy ignores the rotation phasing, treats a complicated orbital ballet as a one-dimensional split of momentum, and draws a thin shell of atmosphere at the same scale as an orbit a thousand kilometers up. It lies in a dozen ways.

But it lies with the lies clearly marked. The constants are real and sourced — Earth's gravitational parameter is the genuine measured value, near 398,600 km³/s², rounded but not invented. The conservation law is honest: every kilometer the payload climbs is a kilometer the station gives up, because that is how momentum is actually conserved. The toy is a cartoon with rigor exactly where rigor carries the point, and caricature everywhere else.

So it is a *toy*: a working model, scaled to fit a screen, honest about its scale. The word matters, because the honesty is the ethic, and I will come back to it. But first I owe a debt.

---

## The thing I keep almost finding

A small canon of people have made the interactive web beautiful, and I have learned from all of them.

Andy Matuschak and Michael Nielsen built essays that remember you — prose interleaved with spaced-repetition prompts, so the reading rewires you as you go. Distill.pub set a standard for rigor in interactive explanation that its field has not matched since it went quiet. Bret Victor's *Explorable Explanations* and *Kill Math* are the founding documents; he saw, before almost anyone, that a static equation is a coffin for an idea that wants to move. Nicky Case made playable parables — trust, segregation — that are generous and humane and genuinely fun. And Bartosz Ciechanowski builds the most patient machines on the internet: scroll through his piece on the mechanical watch, and the thing becomes inevitable.

Read them. Read the source. Then notice the family resemblance that, for my purposes, sets them apart from what I am after.

Most of this work is in the business of transmission. Each maker has a known truth — a neural net, an escapement, the geometry of a satellite fix — and has built an extraordinary interface to move that truth into your head more durably than prose could. The honest exceptions matter: Case's *Parable of the Polygons* does argue a thesis, and it shows the line I am drawing is a line, not a wall. But even teaching done with the condescension surgically removed is still teaching. 

And teaching is not the thing I want.

---

## What this is not

The genre is defined as much by its refusals as by its aims, so let me clear the ground.

**It is not an educational toy.** That kind explains settled knowledge to a reader it has quietly cast as a student. Even at its most charming it is condescending: it knows the answer, you don't, and the interaction exists to close that gap. The better it is done, the more invisible the condescension becomes — which is why the good ones irritate me most.

**It is not an edu-game.** The educational game has a long and unhappy history. Either the students find a way to win without learning the thing the game was built to teach, or the game is boring, and a boring game is merely a worksheet with a score. Fun is not a coating you apply to learning.

**It is not generative art.** I admire the Processing tradition — the flocking simulations, the reaction-diffusion fields. They are beautiful and contemplative. But they argue nothing. They invite you to watch; they do not stake a claim and dare you to break it. An Argumentative Toy is rhetorical, not meditative. It wants your assent, and it is willing to crash a spacecraft to get it.

Remove the lesson and the meditation, and what is left is argument — the older and rougher art of persuasion. The interactive web has been colonized by pedagogy. However gentle. I want to reclaim a corner of it.

---

## An essay with knobs

Here is the definition, plainly. An Argumentative Toy is:

- **A standalone web page** — self-contained, no platform, no account, no telemetry. A few hundred lines of HTML and JavaScript you can read by viewing source. A toy that phones home has become a product.
- **Both essay and simulation** — prose and mechanism interdependent, neither sufficient alone. The text makes a claim defensible in one sentence; the knobs let you test where it holds and where it breaks.
- **An argument about a trade-off**, not a fact about the world.
- **Playable**, with rarely more than three or four controls, each earning its place by changing what you believe. A slider that exists only to be moved gets cut.
- **Graphic and dramatic in failure.** The negative result is not an error to be corrected. It is the rhetorical payload. The cable burns, and the burning is the point.
- **Honest** — the load-bearing wall, so it gets its own section.

A toy makes a single point, lets you feel where the point breaks, and earns its closing line — which sits below the canvas in quiet type and names the one thing you now know that you did not when you opened the tab. A McPhee closing paragraph, ported to software: earned, understated, devastating in its smallness.

---

## Why a trade-off is the right unit

Facts can be told. If I want you to know Earth's gravitational parameter, I write it down and you have it. A good explainer is simply a very good way of telling.

A trade-off cannot be told that way, because it does not live in the world the way a fact does. It lives in your own weighting of incommensurable costs. How much station altitude is a payload's velocity worth? There is no answer in the back of the book. The answer depends on what you value, and you will not believe any answer you did not arrive at yourself.

So the toy does what an essay cannot. It hands you the slider, lets you supply your own values — push the boost higher, make the payload heavier, demand more for less — and shows you, without editorializing, what the choice costs. The station sags. You back off. It sags less. You get greedy. It burns. The argument is co-authored: you brought the desire for more, the physics brought the bill, and the conclusion is one you will defend to other people, because it is genuinely yours.

That is the reason the unit must be a trade-off and not a fact. You cannot feel a fact. You can only feel a cost.

---

## Honesty, or: the difference between a toy and a lie

A machine built to make you feel a conclusion is a powerful and dangerous instrument. Structurally it is very close to an advertisement, and the same techniques that make the tether's death persuasive could make a false thing persuasive just as easily. To argue for the genre I have to draw the line that separates it from propaganda, and the line had better be sharp.

The line is built into the craft, not added afterward:

- **No fake numbers.** Every quantity the toy displays is derived from the constants it actually uses. Nothing is hard-coded to look calculated.
- **Every unit labeled.** A unitless number on a technical page is a small betrayal of the reader. km, km/s, kg/m³.
- **The constants sourced.** A comment at the top of the script names where the gravitational parameter and the density profile came from. The reader who views source finds honest provenance.
- **The lies clearly marked.** Where the model caricatures reality, it says so: *visual scale exaggerated*, *one orbit = 90 min real / 6 s shown*. Mistrust any animated toy that does not declare its time base.
- **The reader is free to break it.** Every slider can be pushed to where the argument fails. A toy that hides its own failure regimes is hiding the truth.

A toy that keeps these rules argues in the open, assumptions on the table, machinery visible, inviting you to find the flaw. A toy that breaks them is an advertisement wearing a lab coat. And yet I do not think the rules dissolve the danger; they only make it visible. The form can still be turned to a bad end by someone willing to source a constant and lie about everything around it. The honesty is structural, but it is not automatic — it asks something of the maker every time, and that, finally, is the part I cannot build into the code for you.

---

## Make one

The form is cheap, and that is its best feature and its quiet politics. No platform owns it, no account gates it, and no framework is needed where twelve lines of vanilla JavaScript will do. A good one loads in under a hundred kilobytes, fonts included, and runs on a phone on a train. The materials are lying around. The only scarce ingredient is a claim worth arguing and the discipline to argue exactly one.

So the invitation is not to admire these. It is to build one. Find a trade-off you actually believe in — where the conventional wisdom is wrong, or the cost is hidden, or people want more for less and the universe declines to provide it. Build the smallest machine that lets a stranger feel the bill come due. Mark your lies. Source your constants. Write one quiet sentence for underneath the canvas. Then let the reader crash the rocket.

The tether is still turning at the top of this page. I built it on a Tuesday and spent the rest of the week pushing the slider too far, watching the battery spend itself into the air, telling myself I was testing it. I was just playing. That is the whole of the recommendation: make a thing you cannot stop poking, mark where it lies, and put it where a stranger can find it. You will not need me to tell you what you learned.

> *The tether gives the payload its altitude by spending its own; momentum is borrowed, never made.*

---

*— with a working toy, `revised_toy_draft.html`, built to demonstrate the argument it makes.*

---

### Sources for the toy's physics

- Standard gravitational parameter of Earth, μ = 398,600.435507 km³/s² — JPL Solar System Dynamics, Astrodynamic Parameters: https://ssd.jpl.nasa.gov/astro_par.html
- Earth equatorial radius ≈ 6,378 km; LEO orbital velocity ~7–8 km/s — Space Academy, LEO parameters: https://www.spaceacademy.net.au/watch/track/leopars.htm
- Momentum-exchange tether as an "orbital energy battery"; tossing a payload drops the facility's apogee; reboost required between tosses — R. Hoyt, Tethers Unlimited / NASA NIAC final report (MXER): https://www.niac.usra.edu/files/studies/final_report/373Hoyt.pdf
- "The transfer of momentum to the released object will cause the rotating tether to lose energy, and thus lose velocity and altitude" — Momentum exchange tether, Wikipedia: https://en.wikipedia.org/wiki/Momentum_exchange_tether

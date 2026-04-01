---
title: Prototype the Question
date: 2026-03-31
draft: false
---

I keep catching myself doing the same thing: I have an idea, I get excited, and I start building. Not a sketch, not a spike — the real thing. The architecture, the folder structure, the CI pipeline. And then, weeks in, I find out that my core assumption was wrong.

I don't think I'm alone in this.

## The game that almost wasn't fun

A friend pitched me a side project idea — a bot arena game. You write code that controls an army of units, submit it, and your bot fights other bots. He had the whole thing in his head: WASM modules, event sourcing, a CI pipeline that runs matches automatically, maybe a web-based replay viewer.

He's an engineer at heart, so of course he went straight to the technical details. And honestly, it was awesome — that's exactly why he's a great engineer. But there was a lot of architecture to build before we'd know if the core idea even works.

So before we dove into any of that, I wrote a throwaway prototype. About 900 lines of Rust. No WASM, no CI, no UI. Just the raw game loop: a few unit types, a bunch of bot strategies, and a round-robin tournament to test all matchups.

One question: is this actually fun to play?

Turns out, our original design wasn't. The core mechanic — army composition only, no per-unit control — didn't create enough depth. One unit type dominated everything. The rock-paper-scissors triangle we'd designed only worked when bots could make decisions every tick, not just pick their army and watch.

That's not a small finding. That's a fundamental design change. If we'd built the real system first — WASM loading, event infrastructure, the whole thing — we would have discovered this with ten times the code to throw away.

The prototype cost me a weekend. The code went in the trash. The decisions stayed.

## The habit I don't practice enough

This isn't some revelation. "Validate before you build" is older than I am. And yet I keep not doing it. At work, I've seen it too — teams writing specs, building features, and finding out months later that the assumption was off. Not because anyone was careless, but because building a prototype feels like extra work. We tell ourselves we don't have the time — it's faster to just build the real thing. And then we spend months building the wrong real thing.

![How projects really work](/blog/images/thanks-no-time.png)

At some point when I started dealing with software architecture, I came across this idea: the last responsible moment. I don't have to make every decision upfront. I defer until I have enough information to decide well. Not because I'm avoiding decisions — because I'm making better ones.

A prototype is how I buy that information cheaply. I'm not building the product. I'm answering a question. What's the riskiest assumption? What would hurt the most to get wrong? Build the smallest thing that tests that, and throw it away.

And now, with AI, "the smallest thing" got really small. Anyone can vibe-code three variants of an approach in an afternoon and compare them side by side. Put something concrete in front of a stakeholder before anyone writes a spec. Spike a technical direction in hours instead of days. The cost of validating an assumption has never been lower.

Which makes me wonder: if prototyping is this cheap now, why are we still committing to things before we've tested them? Why are we still writing specs instead of building the thing the spec is trying to describe? I don't have a good answer yet. But I'm starting to think the default should be the other way around — prototype first, decide after.

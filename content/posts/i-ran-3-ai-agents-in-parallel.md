---
title: I Ran 3 AI Agents in Parallel
date: 2026-03-29
draft: false
id: 1f4b02f8-83b6-4458-9cf2-bbde4f775f4b
tags: []
pinned: false
created: 2026-03-29T22:38:52.752293216+00:00
modified: 2026-03-29T22:42:14.961977360+00:00
---

I work on a product with a multi-repo setup. Implementing a feature that spans multiple repos means context-switching between them constantly. It's one of those things that's not hard exactly, just... slow.

So I had this idea: what if I run a separate AI agent in each repo, and they coordinate with each other?

## The manual version

I set up a simple test. A todo app, split across three repos. Nothing fancy — the point was to see if the pattern works at all.

First try: three [Claude Code](https://claude.ai/code) sessions in three terminal windows. One per repo. Me in the middle, copy-pasting between them.

> "Hey frontend, the API now returns nested subtasks, here's the shape." Tab over. "Hey backend, the API layer gets a 500 on this endpoint." Tab over.

I was the message bus.

It felt absurd. But it worked. Each agent had deep context about its repo. They never stepped on each other's code. And the handoffs created natural API contracts — when I told one agent *"the other side returns this shape,"* it just built against that. No ambiguity.

The problem was obvious though: I was the bottleneck. Every message had to go through me.

## Agent Teams

Claude Code has an experimental feature called [Agent Teams](https://code.claude.com/docs/en/agent-teams). I'd seen it before but never really understood the point — sub-agents already let you delegate work, why would you need a "team"?

This was the use case. Sub-agents are fire-and-forget. Agent Teams give you a coordinator that sets up a team, spins up specialized agents, and delegates. The agents can message each other directly — no human relay.

The catch: they're not really persistent either. The team lead spins up agents, they do their work, and when the task list is done, everything shuts down. If you then test the result and come back with "actually, this endpoint should return a list, not an object" — the team is gone. You start from scratch with a new team, new agents, no accumulated context. For a single burst of work it's great. For the back-and-forth of real development, it's [limiting](https://github.com/anthropics/claude-code/issues/23669).

## What if

What if the agents didn't shut down after the task list is done? What if they just... stayed there, with all the context they built up, ready for the next round of feedback?

What if you could define a team setup once — which repos, which agents, which roles — and spin it up reliably every time instead of hoping the coordinator figures it out?

What if you could scale that to five repos, ten repos, and deploy the same team shape across different projects?

I have some ideas. More on that soon.

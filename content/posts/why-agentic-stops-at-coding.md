---
title: Why Agentic Stops at Coding
date: 2026-09-04
---

Every agentic thing I read about is coding. Coding agents, agentic coding, SWE benchmarks, "my agent opened three PRs while I slept". I run agents on my own projects daily and that part works.

But it's one step, and on a normal work day it isn't my step. Before anybody writes code, somebody has to work out what to build next and how the system should behave. Every team I've worked in calls that something else and wraps it in ceremonies, but it's the same work, and it takes a lot longer than the coding does.

So where's the agentic version of it? Agentic requirements engineering, agentic specification, whatever it would be called.

## Two guesses

First guess: nobody cares about that part. That's backwards, it's where all the pain is. I've never heard anyone complain that typing is slow, only about vague tickets and specs that changed halfway through.

Second guess: the LLMs can't do it. Well-formed prose about a topic is the thing they're best at, and a plausible requirement is easier than correct code.

So it isn't demand and it isn't capability. That bugged me, until I looked at what the coding loop is made of.

## What makes the loop work

An agentic coding loop is: write something, run the tests, read the failure, fix it, run again. What makes it work is that something outside the agent says no, twenty times in a row, for free, while I'm not in the room. Compiler, type checker, test suite, did the benchmark get worse.

Take the tests away and what's left is an LLM producing something plausible once, and me reading it.

Now the same thing for a feature. I write down how it should behave, and then what runs? There's no compiler for "is this the right behavior".

## Who says no

There is something, though. It's a person. A customer, a user, the engineer who has to build the thing, whoever finds out first that this isn't what they meant. That's a real check, and it's the only one that can tell me the behavior itself is wrong.

Earlier this summer I wrote four short architecture documents for how a new service should attach to an old product. Well argued, trade-offs listed, consistent with each other. Four days later two engineers who know that old system read them, and the first thing back was a constraint that killed the direction all four were built on. Three had to be rewritten.

Nothing I could have run would have caught it, because it wasn't written down anywhere. And it wasn't even a judgment call. It was a yes-or-no fact, and the only copy of it was in two people's heads.

Asking is also slow, it costs somebody's attention every time, and it doesn't run while I'm asleep. Twenty rounds is absurd when one round costs a meeting. The loop runs at whatever speed I can get somebody to look.

## The slope

Agentic coding came first because coding is the only step where the thing that says no is a machine.

Whether the code works, a machine tells me in seconds, for free, as often as I want. Whether a spec describes the right behavior, a colleague or a user tells me, in an afternoon, and I have to go and ask. And whether it was worth building at all, only the market can tell me, in weeks, sometimes not until after we shipped it.

The further up I go, the more it costs to find out I'm wrong, and I don't think a better LLM moves that. A better model writes a better first draft of the spec. It doesn't make the customer answer any faster.

That gives me a mechanical reason for "don't outsource the thinking", and I like it better than the moral one. Downstream I can let an agent run unattended because the tests catch it when it's wrong. Up here nothing catches me, so anything I skip thinking about ships.

I'd like to be wrong about that. I have half an idea of what a loop for the top of the slope would need, and it starts with making the person cheaper to ask. More once I've tried it.

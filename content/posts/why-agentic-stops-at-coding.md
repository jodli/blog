---
title: Why Agentic Stops at Coding
date: 2026-09-04
unlisted: true
---

Every agentic thing I read about is coding. Coding agents, agentic coding, SWE benchmarks, "my agent opened three PRs while I slept". I run agents on my own projects daily and that part works.

But it's one step, and on a normal work day it isn't my step. Before anybody writes code, somebody has to work out what to build next and how the system should behave once it's there. Every team I've worked in calls that something else and wraps it in its own ceremonies, but it's the same work, and in my experience it takes a lot longer than the coding does.

So where's the agentic version of it? Agentic requirements engineering, agentic specification, whatever it would be called.

## Two guesses

First guess: nobody cares about that part. That's backwards, it's where all the pain is. I've never heard anyone complain that typing is slow. The complaints I hear are about vague tickets and specs that changed halfway through.

Second guess: the LLMs can't do it. Writing a plausible requirement is easier for an LLM than writing correct code. Well-formed prose about a topic is the thing they're best at.

So it isn't demand and it isn't capability. That bugged me for a while, until I looked at what the coding loop is made of.

## What the test suite does

An agentic coding loop is: write something, run the tests, read the failure, fix it, run them again. What makes it work is that something outside the agent says no, twenty times in a row, for free, while I'm not in the room. Compiler, type checker, test suite, does it start, did the benchmark get worse.

Take the tests away and what's left is an LLM producing something plausible once, and me reading it.

Now the same thing for a feature. I write down how it should behave, and then what runs? There's no compiler for "is this the right behavior".

## Who says no

There is something, though. It's a person. A customer, a user, the engineer who has to build the thing, whoever finds out first that this isn't what they meant. That's a real check, and it's the only one that can tell me the behavior itself is wrong.

It's also slow, it costs somebody's attention every time I call it, and it doesn't run while I'm asleep. Twenty rounds is absurd when one round costs a meeting.

So the check exists. It's just made of people, which means the loop runs at whatever speed I can get somebody to look.

## The slope

Agentic coding came first because coding is the only step where the thing that says no is a machine.

Whether the code works, a machine tells me in seconds, for free, as often as I want. Whether a spec describes the right behavior, a colleague or a user tells me, in an afternoon, and I have to go and ask. And whether it was worth building at all, only the market can tell me, in weeks, sometimes not until after we shipped it.

The further up I go, the more it costs to find out I'm wrong, and I don't think a better LLM moves that, because the cost sits in finding out whether the answer is any good.

That gives me a mechanical reason for "don't outsource the thinking", and I like it better than the moral one. Downstream I can let an agent run unattended because the tests catch it when it's wrong. Up here nothing catches me, so anything I skip thinking about ships.

Which is the same wall I ran into [last time I wrote about this](../the-bottleneck-is-not-coding/).

I'd like to be wrong about that. I have half an idea of what a loop for the top of the slope would need, and it starts with making the person cheaper to ask. More on that once I've actually tried it.

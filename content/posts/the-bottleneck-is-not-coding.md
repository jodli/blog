---
title: The Bottleneck Is Not Coding
date: 2026-03-30
draft: true
---

In my [first post](../hello/), I dropped this line: *"Coding was never the bottleneck. Decisions were. Alignment was."* Let me unpack that.

## The narrative right now

Open any tech blog, any LinkedIn feed, any conference talk. The story is the same: AI is making developers 10x faster. Coding assistants, agentic workflows, automated PRs, vibe coding. The message is clear — writing software is about to get very, very fast. I was at the [Software Architecture Gathering](https://conferences.isaqb.org/software-architecture-gathering/) in Berlin last year — even there, half the sessions circled back to this.

And it's true. I've had side project ideas sitting in my notes for years, things I never found the time to build. Now I'm actually working through them, one by one. The coding part is genuinely getting faster.

But here's what's been bugging me: we're treating LLMs like they're going to solve all of software development. Engineers will be irrelevant soon, they say. Everyone can build software now. I'm getting tired of it. The ceiling for optimizing the coding part is so low in the overall process of creating a software product — and nobody seems to ask *what happens after you write the code faster.*

## Where time actually goes

Think about the last feature you shipped. Not a side project — a real feature, at your real job, with real stakeholders, real people relying on your product to work, and real customers paying real money. How long did it take from "someone had the idea" to "a customer is using it"?

Now think about how much of that time was spent writing code.

In my experience, it's somewhere between 10% and 20%. The rest is:

- Waiting for someone to decide what to build
- Waiting for alignment between teams
- Waiting for reviews, approvals, sign-offs
- Figuring out that what you built isn't what the user needed
- Rewriting because the spec changed halfway through
- Coordinating across components that different teams own
- Deploying, testing in staging, rolling back, trying again

The actual typing-code-into-an-editor part? That was never the slow bit.

## Theory of Constraints, but nobody reads Goldratt anymore

There's a concept from manufacturing that's been around since the 1980s that I keep coming back to. Eli Goldratt called it the [Theory of Constraints](https://en.wikipedia.org/wiki/Theory_of_constraints): any system's throughput is limited by its single tightest bottleneck. If you optimize something that isn't the bottleneck, the system doesn't get faster. It just piles up more inventory in front of the actual constraint.

Applied to software: if you 10x the speed of coding but decisions still take three weeks and alignment meetings still happen biweekly, you haven't shipped anything faster. You've just created a pile of code waiting for someone to decide if it should exist.

I've watched this happen. A team knocks out a feature in two days. Then it sits for weeks — waiting for product decisions, architecture sign-off, scope clarification, design review, API alignment, QA, release planning. The code is done. The product isn't.

## We already knew how to fix this

This is what frustrates me the most. We're not discovering a new problem. I keep thinking about patterns we've had for decades — and how everyone seems to have forgotten them:

**Lean startup.** Build the smallest thing, put it in front of users, learn, iterate. The whole point was to stop building things nobody wants. That idea is from 2011.

**Agile — the original version.** Not the ceremony-laden, two-week-sprint, Jira-ticket version. The actual manifesto: working software, customer collaboration, responding to change. The point was short feedback loops between building and learning.

**Continuous delivery.** Ship small, ship often, get feedback fast. Not because deploying is hard, but because the longer you wait to learn, the more you waste.

**Domain-driven design.** Organize around business domains, not technical layers. So that one team can own a problem end-to-end without coordinating with five other teams.

These patterns all attack the same bottleneck: the time between "we have an idea" and "we know if it's the right idea." They're not about coding faster. They're about *learning* faster.

And somehow, in the rush to make AI write code, we're forgetting all of them.

## What I keep seeing instead

It's not just teams adopting AI tools on their own — it's management rolling them out top-down, expecting results the moment developers get access. The hype creates the impression that delivery will speed up overnight. Laura Tacho calls this ["spray and pray"](https://youtu.be/LOHgRw43fFk): simply buying AI licenses for all developers and hoping for the best. It doesn't work.

What I keep seeing is: the tools arrive, and everything else stays the same. Same quarterly planning. Same spec documents that take weeks to write and are outdated by the time engineering starts. Same review processes. Same handoffs between silos.

The code gets written faster. Everything else stays slow. And then people wonder why they're not actually delivering more value.

Or worse — they *do* produce more code, and now there's more to review, more to test, more to maintain, more to debug. The pile grows. The bottleneck downstream gets even more stressed. And upstream? Product and scoping can't keep up either — so teams start building whatever seems reasonable, without clear direction. You're not just shipping slower. You're building the wrong things faster.

AI accelerates existing patterns — good and bad.

## The uncomfortable part

I think the reason "AI makes coding faster" gets all the attention is because it's easy to measure and easy to sell. Lines of code per hour. PRs merged per day. Time to first commit.

The hard stuff — are we building the right thing? do users actually want this? can our organization make decisions fast enough? — that's messy. It's organizational. It's political. You can't solve it with a better autocomplete.

But that's where the bottleneck is. And until we start optimizing *that*, all the AI coding tools in the world are just helping us build the wrong thing faster.

---

*I'm not saying AI coding tools are useless. I use them daily. They're great. But they're solving a problem that wasn't the bottleneck — and we keep acting like they're solving everything.*

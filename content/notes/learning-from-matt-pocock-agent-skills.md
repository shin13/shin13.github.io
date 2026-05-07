---
title: "[Dev] Learning from Matt Pocock’s Agent Skills"
summary: A concise, grateful note on Matt Pocock’s everyday agent skills, and how process, questions, TDD, and architecture make Claude Code agents more insightful partners.
date: 2026-05-07T08:53:00+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Development
  - Learning
tags:
  - AI Agents
  - Claude Code
  - Agent Skills
  - Software Architecture
  - TDD
  - Product Requirements
  - Matt Pocock
draft: false
excludeSearch: false
---

I recently read Matt Pocock’s article, [“5 Agent Skills I Use Every Day”](https://www.aihero.dev/5-agent-skills-i-use-every-day). It resonated with my experience using coding agents such as Claude Sonnet and Claude Opus.

The article gave me a clearer language for something I have been feeling: good agent work depends on good engineering process. We need better questions, written context, small slices, tests, and codebases that agents can understand.

<!--more-->

![Agent skills as a disciplined workflow: idea, grill-me, to-prd, to-issues, tdd, and architecture improvement.](/images/notes/agent-skills-workflow.svg)

## Who is Matt Pocock?

Matt Pocock is an educator, content creator, and engineer. Many developers know him as the creator of [Total TypeScript](https://www.totaltypescript.com/), a former Vercel developer advocate, and a former XState core team member.

He now teaches AI engineering through [AI Hero](https://www.aihero.dev/). I appreciate his consistent message: software fundamentals become more valuable when agents can produce code quickly.

Thank you to Matt for sharing these practical resources so generously.

## The idea: skills turn taste into process

Matt describes coding agents as a “fleet of middling to good engineers” with one major weakness: they have no memory.

That framing feels honest. If agents forget context, then our process must carry the context. Skills give the agent a path to follow: clarify, document, slice, test, and improve the architecture.

A small reflective question stayed with me: if an agent mirrors the quality of the process around it, what kind of engineer am I teaching it to become?

## `grill-me`: ask before building

`grill-me` asks the agent to interview the user relentlessly until the plan is clear. It walks the design tree one decision at a time.

This is one of my favorite skills. It turns Claude from a fast implementation machine into a thoughtful partner. It helps reveal hidden assumptions, missing constraints, and premature decisions.

I especially enjoy this because I like discussing and designing beautiful systems. Sometimes the most valuable output from an agent is a better question.

## `to-prd`: make understanding explicit

`to-prd` turns resolved context into a Product Requirements Document.

The value is the shared artifact. A PRD records the problem, user stories, implementation decisions, testing direction, and out-of-scope items. It gives both the human and the agent a stable reference point.

For healthcare AI and internal tools, this matters. Requirements often touch workflow, safety, traceability, evaluation, and deployment. A PRD keeps those layers visible.

## `to-issues`: build in vertical slices

`to-issues` breaks a PRD into independently actionable GitHub issues.

The key idea is vertical slicing. Each issue should create a small, verifiable behavior across the system. This works better than splitting work into disconnected layers such as schema, API, UI, and tests.

The “tracer bullet” metaphor is useful. A small end-to-end path through the system teaches us more than a large unfinished layer.

## `tdd`: give the agent a real feedback loop

`tdd` guides the agent through red, green, refactor.

This improves agent output because tests anchor the work in observable behavior. Good tests describe the public behavior of the system. They survive refactors and reduce hallucinated implementation paths.

The rhythm is simple:

1. Confirm one behavior.
2. Write a failing test.
3. Implement the smallest change.
4. Run the test.
5. Refactor after green.

What would coding feel like if every agent action had to pass through a small gate of truth?

## `improve-codebase-architecture`: make the system legible

`improve-codebase-architecture` feels especially powerful to me.

Agents inherit the shape of the codebase. Clear names, deep modules, stable interfaces, and coherent boundaries help them reason. Scattered concepts and shallow abstractions make them wander.

When I use Claude Sonnet or Opus with this skill, the conversation becomes deeper. The agent starts noticing coupling, boundaries, test seams, and module shape. It brings out more treasure from the codebase.

This matches a first-principles view: intelligence needs a structure to act on. A beautiful system gives both humans and agents fewer things to hold in working memory.

## What I learned

These skills did not simply make the agent “smarter.” They made the conversation more disciplined.

The agent asked better questions. It wrote with more context. It decomposed work more carefully. It treated tests as part of design. It saw architecture as part of the agent workflow.

That is the deeper lesson for me. Agentic coding is a collaborative system: human judgment, written process, tests, and architecture working together.

## Useful links

- Matt’s article: [5 Agent Skills I Use Every Day](https://www.aihero.dev/5-agent-skills-i-use-every-day)
- AI Hero: [https://www.aihero.dev/](https://www.aihero.dev/)
- Matt Pocock’s personal site: [https://www.mattpocock.com/](https://www.mattpocock.com/)
- Skills collection: [AI Skills for Real Engineers](https://www.aihero.dev/skills)
- GitHub repository: [mattpocock/skills](https://github.com/mattpocock/skills)
- `grill-me`: [Stress-Test a Plan Before You Build](https://www.aihero.dev/skills-grill-me)
- `to-prd`: [Turn Resolved Context Into a PRD](https://www.aihero.dev/skills-to-prd)
- `to-issues`: [Break a PRD Into Vertical-Slice GitHub Issues](https://www.aihero.dev/skills-to-issues)
- `tdd`: [Red, Green, Refactor for Agentic Coding](https://www.aihero.dev/skills-tdd)
- YouTube video I found useful: [https://www.youtube.com/watch?v=-QFHIoCo-Ko](https://www.youtube.com/watch?v=-QFHIoCo-Ko)
- YouTube video I found useful: [https://www.youtube.com/watch?v=v4F1gFy-hqg](https://www.youtube.com/watch?v=v4F1gFy-hqg)

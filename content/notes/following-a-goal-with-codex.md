---
title: "[Dev] Following a Goal with Codex (/goal)"
summary: "A practical note on OpenAI Codex's experimental /goal workflow: what it is, when it fits, how I would write it, and what to watch out for."
date: 2026-05-12T09:30:00+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Development
  - Learning
tags:
  - AI Agents
  - Codex
  - OpenAI
  - Workflow
  - Best Practices
draft: false
excludeSearch: false
---

I have been looking for a clean way to explain what `/goal` really does in Codex.

The most useful mental model I found is simple: `/goal` is not a prettier prompt. It is a working contract for long-running agent work. You are telling the agent what success looks like, what the boundary is, and how to know when to stop.

That framing matters because the feature is built for work that outlives one turn. If the objective is durable enough, the agent can keep making progress, validate its own steps, and come back to you with a result instead of a half-finished thought.

<!--more-->

![A simple loop for /goal: objective, checkpoint, validation, and stopping condition.](/images/notes/codex-goal-loop.svg)

## What `/goal` is

OpenAI describes `/goal` as an experimental Codex CLI feature for tasks that need Codex to keep working across turns toward a verifiable stopping condition.

That wording is surprisingly helpful. It says a good goal is not just “something to do.” It is a task with enough structure that the agent can keep moving without being steered every minute.

I read that as a contract with four parts:

- one objective
- one validation loop
- one stopping condition
- one sensible boundary

In other words, it works best when the work is bigger than a normal prompt, but smaller than an open-ended backlog.

![When /goal fits, and when it doesn’t.](/images/notes/codex-goal-fit.svg)

## Where it fits well

The official examples line up with what I would naturally reach for:

- code migrations
- large refactors
- deployment retry loops
- experiments and prototypes
- games or side projects
- prompt optimization against an eval suite

What these have in common is not just that they are long-running. It is that progress can be checked.

That is the key distinction for me. `/goal` is useful when the agent can move in checkpoints and prove that each step is still pointed at the same end state.

## How I would write a good `/goal`

A good goal should say more than “do this.” It should tell the agent what to preserve, how to validate, and when to stop.

The official starter pattern is:

```text
/goal Complete [objective] without stopping until [verifiable end state].
```

I would usually expand that a little in real work:

```text
/goal Migrate this feature from [legacy stack] to [target stack]. Keep behavior identical, run the relevant tests after each checkpoint, and stop only when the new path passes the validation suite and the rollback path still works.
```

If I were using it for a prototype, I would make the success condition even more concrete:

```text
/goal Implement the first usable version of [project]. Keep the scope small, document the checkpoints, verify the output after each step, and stop only when the app builds, launches, and matches the expected behavior.
```

My checklist is usually:

- one objective
- one stopping condition
- a clear set of files or docs to read first
- commands or artifacts that prove progress
- a short progress log
- a way to pause, resume, or clear the run

If I cannot write those down, the goal is probably too fuzzy.

## Where to start

Try to use your chatGPT and instruct the model to 

1. search and read official materials about `/goal`
2. provide your task description for model
3. draft a pormpt for `/goal` to complete your task

## What to watch out for

This is where I think the real value is.

The biggest mistake is to use `/goal` like a loose backlog bucket. A durable objective is not the same thing as a list of unrelated tasks. If the work has no single success condition, the agent will drift.

The second mistake is to over-constrain the work. If the goal is so narrow that it only describes one exact path, you lose the benefit of having an agent explore and recover from small failures.

The third mistake is to forget that independence is not the same as permission. Even when the agent can work for a long time, I still want human judgment on scope, risk, and final acceptance.

For higher-risk work, I would be conservative. A good `/goal` should reduce steering overhead, not replace review.

## My takeaway

I like `/goal` because it makes the agreement explicit.

The best use case is not “let the model run forever.” It is “give the model a durable objective with a verifiable end state, and let it work in a loop until it gets there.”

That is a much better fit for agentic work than a stream of small commands.

If I can state the objective, the boundary, the validation, and the stopping condition in one paragraph, `/goal` is probably doing something useful. If I cannot, I should probably clarify the task first.

## References

- OpenAI Codex use case: Follow a goal — https://developers.openai.com/codex/use-cases/follow-goals
- OpenAI: Introducing ChatGPT agent — https://openai.com/index/introducing-chatgpt-agent/
- OpenAI: Practices for governing agentic AI systems — https://openai.com/index/practices-for-governing-agentic-ai-systems/

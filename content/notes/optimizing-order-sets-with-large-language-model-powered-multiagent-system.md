---
title: Optimizing Order Sets With a Large Language Model–Powered Multiagent System
summary: A note on how a five-agent RAG system helped review and prioritize changes to hospital order sets, and what the evaluation revealed about accuracy versus usefulness.
date: 2025-11-18T09:42:00+08:00
aliases:
  - /blogs/optimizing-order-sets-with-large.html
  - /blogs/optimizing-order-sets-with-large-language-model-powered-multiagent-system/
tags:
  - research
  - LLM
  - RAG
  - multiagent
  - clinical AI
  - order sets
  - healthcare
  - JAMA Network Open
---

# Optimizing Order Sets With a Large Language Model–Powered Multiagent System

This note is a cleaned-up conversion of my original blog post into the site’s Notes format.

## Why this paper matters

Hospital order sets are one of those quiet but important pieces of clinical infrastructure. They standardize care, reduce cognitive load, and help teams act consistently. But they also age quickly. Once evidence changes, keeping hundreds or thousands of order sets updated becomes a constant maintenance problem.

This paper is interesting because it does not treat LLMs as a single magical assistant. Instead, it explores a multiagent workflow with retrieval, verification, and summarization roles, which feels much closer to how a real expert team would work.

## Core idea

The system used five agents:

- Content Critic Agent
- Dynamic Search Agent
- Knowledge Retrieval Agent
- Medication Verification Agent
- Suggestion Summarizer Agent

The architecture combines retrieval-augmented generation with specialized agent roles so the system can:

- search current literature and guidelines
- check internal medical knowledge sources
- verify medication facts
- produce a structured list of suggestions

The goal was not simply to generate more recommendations, but to support more reliable order-set review at scale.

## What the evaluation showed

The key lesson is that factual correctness is not the same as clinical usefulness.

In the reviewed recommendations:

- 54% were rated highly accurate
- 19% were rated highly useful
- 16% were rated feasible
- 12% were rated as having direct clinical impact

That gap matters. A suggestion can be technically right and still be too vague, poorly timed, or misaligned with local workflow to actually help.

## The important middle step: expert alignment

A second LLM was used as a judge, then calibrated with a small set of physician-labeled examples.

Before calibration, agreement with physicians was poor. After only 96 expert-rated examples, agreement improved meaningfully.

The practical result was useful:

- 29% fewer total suggestions to review
- 92% of useful suggestions preserved

That is a strong reminder that small amounts of high-quality expert feedback can substantially improve an AI system’s practical value.

## My take

The most interesting part of this paper is not that the model got some recommendations right. It is that the paper exposes the real clinical problem: usefulness depends on context.

In healthcare, a suggestion only matters if it fits:

- the workflow
- the audience
- the local practice pattern
- the clinical moment

That makes this study less about “AI automation” and more about “AI as a calibrated support layer.”

## A useful framing

I think the best role for systems like this may be as a thought partner rather than a replacement for expert review.

Even an imperfect suggestion can be valuable if it triggers a better question, for example:

- Should this order set include a lab check?
- Is a missing item actually a workflow gap?
- What evidence or local practice should change?

That kind of prompting can help experts notice blind spots they might otherwise miss.

## Reference

- Liu S, Huang SS, McCoy AB, Wright AP, Horst S, Wright A. Optimizing Order Sets With a Large Language Model–Powered Multiagent System. JAMA Network Open. 2025;8(9):e2533277.
- DOI: https://doi.org/10.1001/jamanetworkopen.2025.33277

## Source note

Original post: https://soobahorn.blogspot.com/2025/11/optimizing-order-sets-with-large.html


---
title: "The 7 Skills You Need to Build AI Agents"
summary: IBM Technology's video argues that shipping AI agents in the real world is less about clever prompts and more about system design, retrieval, reliability, security, observability, and product thinking.
date: 2026-05-13T10:42:46+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Learning
  - AI
tags:
  - AI Agents
  - Prompt Engineering
  - System Design
  - RAG
  - Observability
  - Product Thinking
  - Security
  - Retrieval
  - Reliability
draft: false
excludeSearch: false
---

IBM Technology's *The 7 Skills You Need to Build AI Agents* makes a point that feels increasingly true: if an agent can act in the real world, then prompt writing is only the starting point.

<!--more-->

The more useful framing is this: *prompt engineering* is the recipe, but *agent engineering* is the kitchen.

A production-grade agent needs structure, contracts, failure handling, traceability, and a clear product experience. In other words, it needs engineering discipline.

<figure>
  <img src="/images/notes/ai-agent-skills-mindmap.png" alt="A mind map of the seven skills needed to build AI agents.">
  <figcaption>Fig 1: Break agent engineering into seven core skills, then fill in the gaps one module at a time.</figcaption>
</figure>

## The 7 skills

For engineers who are new to agentic systems, I’d turn the seven skills into these practical rules:

### 1) System design
- Start with one control loop: state in, tool call out, result back, state updated.
- Keep planning, execution, and persistence separate so failures are easy to trace.

### 2) Tool and contract design
- Treat tools like strict APIs. OpenAPI exists for exact request/response contracts, not loose suggestions.
- Give the model the smallest safe tool set; validate every parameter before execution.

### 3) Retrieval engineering
- Retrieval quality sets the ceiling for the agent. Use chunking, metadata, and reranking rather than embeddings alone.
- Check whether the right evidence was retrieved before tuning prompts.

### 4) Reliability engineering
- Expect timeouts, rate limits, and duplicate calls. Make actions idempotent and add bounded retries.
- Use SLOs and error budgets to decide when to degrade or stop.

### 5) Security and safety
- Assume prompt injection and unsafe output handling. Keep untrusted text separate from tool instructions.
- Use least privilege, allow-lists, and human approval for high-impact actions.

### 6) Evaluation and observability
- Log prompts, retrieved context, tool calls, and final outcomes. OpenTelemetry-style traces help connect the whole flow.
- Build offline evals early, then compare them with real user traces and failure cases.

### 7) Product thinking
- Define success criteria before shipping. Anthropic’s prompt-engineering docs explicitly recommend clear success criteria and empirical tests.
- Add clarification, escalation, and graceful fallback paths so users can recover when the agent is uncertain.

What I liked most is that the video refuses to romanticize agents. Real systems need boundaries. They need retries, fallbacks, logs, and a human-centered experience.

That also means a useful debugging instinct: when an agent fails, trace backward before you rewrite the prompt. Was the right document retrieved? Was the tool schema clear? Did the system fail before the model even had a chance to help?

<figure>
  <img src="/images/notes/ai-agent-boundaries-control.png" alt="An agent system shaped by boundaries, guardrails, approval gates, and guided actions.">
  <figcaption>Fig 2: An agent is not just a bigger model. It needs a balance of design, boundaries, permissions, and guidance.</figcaption>
</figure>

## What to study next

If you want to go deeper, these are good companion resources for each skill area:

### 1) System design

- [*Designing Data-Intensive Applications*](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)
- [Google SRE book](https://sre.google/books/)

### 2) Tool and contract design

- [*API Design Patterns*](https://www.manning.com/books/api-design-patterns)
- [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Swagger OpenAPI Specification overview](https://swagger.io/specification/)

### 3) Retrieval engineering

- [OpenSearch Documentation](https://docs.opensearch.org/latest/)
- [Elasticsearch Reference](https://www.elastic.co/docs/reference/elasticsearch)
- [*Designing Machine Learning Systems*](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)

### 4) Reliability engineering

- [*Release It! Second Edition*](https://pragprog.com/titles/mnee2/release-it-second-edition/)
- [Google SRE book](https://sre.google/books/)
- [Testing Strategies in a Microservice Architecture](https://martinfowler.com/articles/microservice-testing/)

### 5) Security and safety

- [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) for strict request/response contracts

### 6) Evaluation and observability

- [OpenTelemetry docs](https://opentelemetry.io/docs/)
- [*Designing Machine Learning Systems*](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)

### 7) Product thinking

- [*Inspired*](https://www.svpg.com/books/inspired-how-to-create-tech-products-customers-love-2nd-edition/)
- [*The Product-Minded Engineer*](https://www.oreilly.com/library/view/the-product-minded-engineer/9781098173722/)
- [*Continuous Discovery Habits*](https://www.producttalk.org/continuous-discovery-habits/)

## My takeaway

<figure>
  <img src="/images/notes/llm-service-vs-agent-system.png" alt="A side-by-side comparison of a simple LLM service and a fuller agent system.">
  <figcaption>Fig 3: An LLM service is just an input-output loop. An agent system also includes tools, retrieval, state, retries, logs, and safety controls.</figcaption>
</figure>

The title "prompt engineer" still describes a useful entry point, but it no longer describes the full job.

If we want agents that people can trust, we need to think like engineers, product builders, and system designers at the same time.

## Source

- YouTube: <https://youtu.be/mtiOK2QG9Q0?si=ITxYMB-1FnRJpcGp>
- Video title: *The 7 Skills You Need to Build AI Agents*
- Channel: IBM Technology

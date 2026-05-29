---
title: "What Counts as Human-AI Collaboration?"
summary: A working note on when using an LLM is just tool use, and when it starts to look like real collaboration.
date: 2026-05-30T00:00:00+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Research
  - Learning
tags:
  - Human-AI Collaboration
  - LLM
  - Teaming
  - Human Factors
  - Explainability
  - Healthcare AI
draft: false
excludeSearch: false
---

I keep coming back to a simple question: when I use an LLM, am I collaborating with it, or just using a tool?

That distinction matters more than it first appears. If we call every AI interaction a collaboration, the word becomes too loose to be useful. But if we reserve collaboration for situations where the human and the system genuinely shape each other’s work, then the term becomes more precise — and more honest.

<!--more-->

My current answer is this:

Using an LLM is not automatically human-AI collaboration.

Sometimes it is only tool use. Sometimes it is a copilot relationship. Sometimes it is closer to teaming. And in a few cases, it becomes co-construction.

The mode depends on the role, the task, and the risk.

## 1. Tool use: the model helps, but the human owns the work

In tool mode, the LLM is basically a faster interface for work I was already going to do.

- I ask a question.
- It gives me text, a summary, a draft, or a suggestion.
- I decide what matters.
- I keep responsibility for the result.

This is probably the most common way people use LLMs.
It is useful, but it is not always collaboration. The model is not really a partner here. It is a capability.

## 2. Copilot mode: the model participates, but under supervision

Copilot mode is different.
Here, the AI is no longer just producing output on demand. It is helping me move through a task:

- checking my assumptions,
- suggesting alternatives,
- flagging missing steps,
- drafting intermediate work,
- or helping me catch errors.

This feels closer to collaboration because there is a feedback loop.
The human is still in charge, but the AI changes the way the work unfolds.

In high-stakes domains, this is often the safest and most realistic target. In medicine, for example, a “digital copilot” framing makes more sense than an “autopilot” framing. The human still needs judgment, training, and the ability to override the system.

## 3. Teaming mode: the interaction starts to look like shared work

Teaming is stronger than copilot mode.
Now the AI is not just assisting a single action. It has a more distinct role in the workflow, and the human adapts to it in return.

This is where questions about agency become important.
If the AI can act, recommend, prioritize, or shape the next move, then the collaboration is no longer one-directional. The system influences the path of the work, not just the output.

That does not mean the AI is an equal teammate in a human sense. But it does mean the interaction is more than prompt-and-response.

## 4. Co-construction: human and AI build something together

Co-construction is the most interesting mode to me.
This is where the AI helps create something neither side would have produced alone in exactly the same way:

- a research question,
- a design direction,
- a conceptual model,
- a draft argument,
- or a new explanation.

This is the closest to what people often imagine when they say “collaboration.”
But it is also the easiest place to over-romanticize the model. A persuasive output is not the same thing as shared understanding.

## What the literature suggests

Recent papers help sharpen this distinction.

One useful finding is that people do not simply prefer the most performant AI collaborator. In a 2026 study on human-AI collaboration, participants preferred agents that were more considerate of human actions, even when those agents were not purely performance-maximizing. That suggests collaboration is not only about accuracy. It is also about whether the human still feels meaningfully involved.

Explainability also matters. A 2024 study found that explainable AI improved task performance in human-AI collaboration, especially because it helped people know when to follow the system and when to override it. That is important: good collaboration is not just about making AI stronger. It is about making the human-AI boundary easier to manage.

Agency is another key idea. A 2025 paper argued that agency deserves a more explicit place in human-AI collaboration research. I agree. If we want to talk seriously about collaboration, we need to ask:

- Who can act?
- Who can decide?
- Who can revise?
- Who can stop the process?
- Who remains accountable?

In medicine, the answer should stay very human. A 2026 perspective on clinical AI argues for moving from “autopilot” toward “digital copilot,” with scenario-based training, clinician benchmarking, and minimum unaided practice. That framing feels right to me for high-risk work.

There is also a social side to this. A 2024 review on socio-emotional attributes argues that trust, empathy, rapport, engagement, and anthropomorphization all shape human-AI collaboration. These factors matter, but I do not think they define collaboration by themselves. They are more like the conditions that can make collaboration possible, smoother, or more fragile.

## My provisional model

Right now, I think of human-AI interaction on a spectrum:

1. Tool use
2. Copilot mode
3. Teaming mode
4. Co-construction

And I think the right mode depends on three questions:

- Role: What is the human responsible for?
- Task: What kind of work is this?
- Risk: What happens if the AI is wrong?

That last question is especially important.
A low-risk brainstorming task can tolerate a much more open-ended collaboration model than a clinical recommendation, a legal judgment, or a safety-critical decision.

## My current conclusion

I do not think “using an LLM” is automatically “doing human-AI collaboration.”
That label is too broad.

For me, collaboration should imply some combination of:

- shared goal,
- interaction,
- feedback,
- adaptation,
- and human accountability.

If the model is only generating text and I am simply consuming it, that is tool use.
If the model helps me think, revise, test, and decide, then the relationship is moving toward collaboration.

So the better question is not just “Can AI collaborate?”
It is:

“Under what conditions does AI become a collaborator rather than only a tool?”

That feels like the more useful question for research, for product design, and for my own daily work.

## References

- Mayer LW, Steyvers M. *Human-AI collaboration: trade-offs between performance and preferences.* Cogn Res Princ Implic. 2026. PMID: 41758389.
- Senoner J, Netland T. *Explainable AI improves task performance in human-AI collaboration.* Sci Rep. 2024. PMID: 39730794.
- Holter S, Moruzzi C, El-Assady M. *Towards Agency in Human-AI Collaboration.* IEEE Comput Graph Appl. 2025. PMID: 41115092.
- Ong AY, Huemer J. *Flight rules for clinical AI: lessons from aviation for human-AI collaboration in medicine.* npj Digit Med. 2026. PMID: 41620563.
- Kargarnovin S, Hernandez CI, Reiners D, et al. *From testbeds to high-stakes work: a review of Human-AI teaming domains and teaming factors.* Front Robot AI. 2026. PMID: 42183027.
- Kolomaznik M, Petrik V, Slama M, Jurik V. *The role of socio-emotional attributes in enhancing human-AI collaboration.* Front Psychol. 2024. PMID: 39474095.

---
title: "[Research] Optimizing Order Sets With a Large Language Model–Powered Multiagent System"
summary: "A note on how a five-agent RAG system helped review and prioritize changes to hospital order sets, and what the evaluation revealed about accuracy versus usefulness."
date: 2025-11-18T09:42:00+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Research
tags:
  - Paper Review
  - LLM
  - RAG
  - Multiagent
  - Clinical AI
  - Order Sets
  - Healthcare
  - JAMA Network Open
draft: false
excludeSearch: false
---

## Paper Overview

**Title:** Optimizing Order Sets With a Large Language Model–Powered Multiagent System 

**Authors:** Liu S, Huang SS, McCoy AB, Wright AP, Horst S, Wright A 

**Journal:** JAMA Network Open 

**Year:** 2025 

**DOI:** https://doi.org/10.1001/jamanetworkopen.2025.33277 

## Why This Paper?

I read this paper because it sits at the intersection of clinical pharmacy, healthcare workflow, and practical AI systems.

- Relevant to clinical decision support and order-set maintenance
- Uses a multiagent LLM design instead of a single-model prompt
- Shows the gap between factual correctness and actual clinical usefulness
- Offers a good example of expert alignment in a high-stakes domain

This article is a cleaned-up conversion of my original blog post into the site’s Notes format.

<!--more-->

## Key Findings

### Main Contributions

1. The authors built a five-agent system for reviewing and improving hospital order sets.
2. The system combined retrieval-augmented generation with domain-specific verification and summarization roles.
3. A small set of physician-rated examples improved the judge model’s alignment with expert judgment.

### Methodology Highlights

- **Approach:** LLM-powered multiagent workflow with retrieval, critique, verification, and summarization
- **Data:** Hospital order sets plus internal and external medical knowledge sources
- **Novel Aspects:** The system was designed to mimic how an expert team would distribute work rather than relying on a single general-purpose model

## Selected Figures

### Figure 1. Overview of the multiagent system architecture and evaluation workflow

![Figure 1. Overview of the multiagent system architecture and evaluation workflow.](https://cdn.ncbi.nlm.nih.gov/pmc/blobs/9d16/12457977/4009c0ec38f4/jamanetwopen-e2533277-g001.jpg)

This is the best high-level figure in the paper. It shows the five-agent workflow and the two evaluation phases, so it immediately explains how the system was built and assessed.

### Figure 2. LLM-as-a-judge alignment and customized filter

![Figure 2. LLM-as-a-judge process for creating a customized filter.](https://cdn.ncbi.nlm.nih.gov/pmc/blobs/9d16/12457977/f9aff6a767a6/jamanetwopen-e2533277-g002.jpg)

This figure is important because it shows the calibration step: the authors did not stop at raw LLM scoring, but used physician feedback to align a usefulness filter with expert preferences.

### Figure 3. Physician ratings of AI-generated suggestions

![Figure 3. Distribution of physician ratings for AI-generated suggestions across accuracy, feasibility, usefulness, and impact.](https://cdn.ncbi.nlm.nih.gov/pmc/blobs/9d16/12457977/3f3cbdd5bb83/jamanetwopen-e2533277-g003.jpg)

This chart captures the paper’s core message well: suggestions can look accurate while still being less useful or feasible in practice.

## My Takeaways

### Immediately Applicable

- A technically correct suggestion is not necessarily useful in a real workflow.
- Small amounts of high-quality expert feedback can meaningfully improve an AI judge.
- In healthcare, context matters as much as correctness.
- LLM systems are often best framed as support layers, not replacements for expert review.

### Future Exploration

- Compare multiagent and single-agent approaches for order-set review
- Evaluate whether local workflow alignment improves clinical adoption
- Study how much expert calibration is enough before diminishing returns

## Questions & Critiques

### Questions Raised

1. How generalizable is this setup across institutions with different workflows and knowledge bases?
2. What is the best way to measure usefulness beyond physician ratings?

### Potential Limitations

- Single-center context may limit generalizability
- Useful suggestions can still be missed if the workflow is too local or vague
- The study emphasizes practical review efficiency more than end-to-end patient outcome impact

## Implementation Ideas

### For Current Projects

- Project: clinical AI decision support workflows
  - Application: use the paper’s expert-alignment idea for filtering or ranking recommendations
  - Timeline: when reviewing retrieval or recommendation pipelines

### New Project Possibilities

- A lightweight expert-alignment layer for clinical suggestion ranking
- A workflow for turning raw AI suggestions into reviewable, context-aware recommendations

## Related Work

### Papers to Read Next

- A framework for human evaluation of large language models in healthcare
- Evaluation of generative large language models in stroke care

### Connections to Previous Reading

- Connects to other research notes on healthcare LLM evaluation, RAG systems, and human review workflows

## Rating & Recommendation

**My Rating:** ⭐⭐⭐⭐☆

**Recommend for:**
- Healthcare professionals working on clinical decision support
- Researchers studying LLM evaluation in medicine
- Engineers building RAG or multiagent workflows
- Anyone interested in expert alignment for high-stakes AI

**Time Investment:** A few hours to read, extract, and rewrite into note form

## Reference

- Liu S, Huang SS, McCoy AB, Wright AP, Horst S, Wright A. Optimizing Order Sets With a Large Language Model–Powered Multiagent System. JAMA Network Open. 2025;8(9):e2533277.
- DOI: https://doi.org/10.1001/jamanetworkopen.2025.33277

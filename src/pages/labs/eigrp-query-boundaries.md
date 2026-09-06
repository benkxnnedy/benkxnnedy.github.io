---
layout: ../../layouts/PostLayout.astro
title: "EIGRP Query Propagation Boundaries"
summary: "A failure-driven CML lab for understanding query scope, summarization, stubs and convergence behaviour."
date: 2026-09-06
type: "Lab"
category: "CCIE routing"
tags: ["EIGRP", "CML", "Convergence", "Stub", "Summarization"]
---
## Objective

Build a topology where an EIGRP successor is lost and observe exactly how far queries propagate before introducing boundaries.

## Scenarios

- Baseline query propagation
- EIGRP stub behaviour
- Summary route as a query boundary
- Leak-map interaction with summarization
- Failure recovery and topology-table verification

## Verification commands

```text
show ip eigrp topology
show ip eigrp neighbors detail
show ip route eigrp
```

The useful part of the exercise is explaining *why* each router is or is not queried, rather than just reaching a converged state.

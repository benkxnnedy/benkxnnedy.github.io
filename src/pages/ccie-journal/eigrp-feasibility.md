---
layout: ../../layouts/PostLayout.astro
title: "EIGRP Feasibility Condition: Stop Memorising, Start Predicting"
summary: "A practical way to reason about reported distance, feasible distance and feasible successors from topology output."
date: 2026-09-03
type: "CCIE Journal"
status: "Study note"
tags: ["EIGRP", "Feasible Successor", "Routing"]
---
## The test

A neighbour can be considered a feasible successor when its **reported distance is lower than the current feasible distance** for the destination.

That is a loop-free condition, not simply a comparison of total path metrics.

## The habit I want in the lab

When looking at topology output, predict the outcome before changing anything:

1. Identify the successor and current feasible distance.
2. Read each alternative neighbour's reported distance.
3. Apply the feasibility condition.
4. Only then compare the resulting behaviour with the device output.

This turns the command output into evidence rather than something to memorise.

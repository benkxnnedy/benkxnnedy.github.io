---
layout: ../../layouts/PostLayout.astro
title: "pyATS Pre/Post Network Validation"
summary: "Structured state collection and comparison to make network changes easier to verify and troubleshoot."
date: 2026-08-28
type: "Project"
category: "Validation"
featured: true
order: 2
tags: ["pyATS", "Genie", "Python", "CML", "Git"]
---
## Goal

Treat validation as part of the change rather than as an informal final step.

## Lab workflow

1. Connect to devices defined in a pyATS testbed.
2. Parse operational state with Genie.
3. Store a structured pre-change snapshot.
4. Apply the lab change.
5. Capture the same state afterwards.
6. Compare the results and flag unexpected differences.

## Why it matters

This pattern scales better than manually checking a few CLI commands and relying on memory. It also creates a useful bridge between traditional network engineering and automated testing practices.

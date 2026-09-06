---
layout: ../../layouts/PostLayout.astro
title: "Production Network Automation Platform"
summary: "An internal Flask application used by engineers to streamline recurring operational workflows and integrate network systems through APIs."
date: 2026-09-01
type: "Project"
category: "Production automation"
featured: true
order: 1
tags: ["Python", "Flask", "REST APIs", "Netmiko", "Cisco ISE", "Catalyst Center"]
---
## The problem

Network engineers repeatedly need the same operational information and checks across multiple platforms. Manually moving between tools adds time and makes simple workflows unnecessarily repetitive.

## What I built

I designed and deployed an internal Flask application that provides a single operator-facing interface for a number of network workflows. The application integrates network platforms and APIs while keeping the workflow understandable for the engineer using it.

The exact production implementation is not published here because it contains employer-specific logic and integrations.

## Engineering principles

- Keep the operator in control.
- Validate inputs before touching infrastructure systems.
- Prefer read-only or low-risk workflows where appropriate.
- Return useful errors rather than raw exceptions.
- Make the automation easier to understand than the manual process it replaces.

## What this demonstrates

The important part of this project is not Flask itself. It demonstrates identifying operational friction, designing an internal tool, integrating real network platforms, deploying it into production, and getting engineers to use it.

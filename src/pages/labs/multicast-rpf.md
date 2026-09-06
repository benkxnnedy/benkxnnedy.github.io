---
layout: ../../layouts/PostLayout.astro
title: "Multicast RPF Troubleshooting Lab"
summary: "A source-to-receiver multicast lab focused on IGMP joins, PIM state, RPF decisions and packet capture."
date: 2026-09-05
type: "Lab"
category: "Multicast"
tags: ["PIM-SM", "IGMP", "RPF", "Wireshark", "tcpdump"]
---
## Objective

Make multicast fail for a reason that is not obvious from the receiver, then prove the failure using control-plane state and packet captures.

## Workflow

1. Establish a working source and receiver.
2. Verify IGMP and multicast routing state.
3. Change unicast routing so the RPF interface becomes unexpected.
4. Observe the multicast failure.
5. Use routing state and captures to identify the cause.
6. Restore a valid RPF path and verify recovery.

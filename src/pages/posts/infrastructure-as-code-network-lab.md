---
layout: ../../layouts/PostLayout.astro
title: "Infrastructure as Code Lab #1"
summary: "The first in a series of posts about my infrastructure-as-code lab."
date: 2026-09-13
type: "Post"
category: "Infrastructure as Code"
tags: ["Infrastructure as Code", "CML", "GitLab CI/CD", "NetBox", "Ansible", "pyATS"]
---

![Architecture of the infrastructure-as-code lab running on Proxmox](/images/posts/infrastructure-as-code-lab-architecture.png)

## The goal

I am building this lab to manage a complete network topology through infrastructure as code. The aim is to move away from one-off manual changes and towards a workflow where configuration, validation and the intended network state are all version-controlled and repeatable.

I already have experience with this from my CCNP Automation studies, but I want to stay sharp because I believe IaC is the future (and it is fun!).

The network itself runs in Cisco Modeling Labs (CML). The current topology is a basic enterprise environment with routed links, a redundant distribution layer using HSRP, a switching layer connected by a port channel, and two endpoints. It is small enough to rebuild and test quickly, but varied enough to exercise realistic automation workflows. It may grow in the future; however, the focus of this lab is IaC, so a basic topology is fine. I will have separate, more complex network topologies coming soon!

## What is in place

I recently acquired a Cisco UCS M4 for labbing and installed Proxmox as the hypervisor. I have deployed three Ubuntu Server VMs for the roles described below, and I have also installed CML. Nothing has been configured on these VMs yet. Today, I am simply getting everything ready for configuration before I go on holiday.

### DevOps VM

The DevOps VM runs GitLab and a GitLab Runner. This will hold the repositories, track changes and execute CI/CD pipelines. The intention is for every network change to begin as code, pass through automated checks and leave a clear history of what changed and why.

### NetAuto VM

The network automation VM will be the execution environment for the tooling that controls and validates the topology. I plan to use:

- Python for custom logic and integrations
- Ansible for configuration deployment
- pyATS for structured testing and validation

### NetBox VM

NetBox will act as the lab's single source of truth. Device data, interfaces, addressing and other intended-state information should live in NetBox rather than being duplicated across scripts and configuration files.

The long-term objective is for automation to read the intended state from NetBox, generate or apply the required configuration, and then validate the live topology against that source of truth.

### Observability VM

NetBox will act as the lab's single source of truth. Device data, interfaces, addressing and other intended-state information should live in NetBox rather than being duplicated across scripts and configuration files.

The long-term objective is for automation to read the intended state from NetBox, generate or apply the required configuration, and then validate the live topology against that source of truth.

## The workflow I am building towards

The finished process should look something like this:

1. Define or update the intended network state in NetBox and version-controlled data.
2. Propose automation or configuration changes through GitLab.
3. Use the GitLab Runner to start linting, validation and deployment jobs.
4. Run Python or Ansible from the automation VM against the CML devices.
5. Use pyATS to confirm that routing, redundancy and connectivity still behave as expected.
6. Store the result in the pipeline.

## What comes next

The foundation is now in place. My next steps are to establish connectivity and authentication between the supporting VMs and the CML devices, populate NetBox with the topology, and build the first pipeline.

I want the initial pipeline to start simply: retrieve the source-of-truth data, generate a configuration, validate it, deploy it to the lab and run a small set of post-change tests. From there, I can add stronger controls, failure handling and rollback behaviour as the project develops.

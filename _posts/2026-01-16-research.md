---
title: "QSM-Cutoff: Formal Verification Lab"
date: 2026-01-16 12:00:00 +0000
categories: [Software, Formal Verification]
tags: [python, ivy, research]
description: "Building verification tooling in Python and Ivy to explore reachable states and validate safety properties."
image:
  path: /assets/distributed_lock.png
  alt: "Segment of state diagram for a distributed lock protocol."
---

I joined Professor Karem Sakallah's research lab in the summer of 2025. The topic was formal verification; in other words, we aimed to prove the correctness of protocols of distributed systems. We used Ivy to model and specify the protocols, while we used Python for the analysis and verification algorithms. While it may be the most abstract and complicated subject I've ever studied, it is also one of the most fascinating.

Our lab was focused on modeling the reachable states of distributed protocols by finding invariants that defined the system's reachable states. By taking advantage of symmetric variables, we could quickly enumerate the unreachable states and sort them into orbits. We would then use first order logic to create formulas that exclude the unreachable orbits. Finally, we would minimize the length and quantity of formulas as much as possible.

Since protocols can have any number of nodes, it can be difficult to analyze their properties. When the size is too small, some properties may not be visible, but larger systems are too complex. Our lab's goal was to find the "cutoff" size (hence the name, QSM-cutoff) at which we could find invariants that are inductive to all greater sizes.

During my time in the lab, I have worked on several specific projects so far. The first one was studying symmetric protocols that behaved differently than most common ones. These special ones were much harder (and perhaps impossible) to find invariants that hold across all sizes. I spent several weeks analyzing the protocol and its peculiarities, experimenting with different strategies for formula generation, and studying pertinent research papers. Ultimately, we deemed this protocol's orbits to be divergent, but I'm hoping that we eventually solve this issue more decisively.

Next, I studied protocols with totally ordered sorts. Most sorts, like nodes, are symmetric. However, certain sorts, like epochs, cannot be permuted arbitrarily, since they follow a specific order. Therefore, our current software must be modified to handle epochs differently. For example, I modified the reachable state enumeration algorithm to detect ordered sorts and exclude them from being permuted. Soon, we will design a new method to generate formulas with totally ordered sorts.

So far, I have been greatly enjoying being a part of Professor Sakallah's research lab. Unlike my time on the [Michigan Mars Rover Team]({% post_url 2026-01-15-mars-rover %}), I have a greater degree of autonomy and agency. We're a small lab, so I'm encouraged to give frequent contributions during our meetings, which have a large impact on the direction of our research. Much of our work is independent and open-ended, so I've become adept at planning my own tasks, analyzing papers and code, and using software for experiments. 
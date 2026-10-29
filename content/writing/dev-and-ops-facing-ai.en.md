+++
title = "Dev and Ops Facing AI"
seo_title = "Dev and Ops Facing AI — An Asymmetric Transformation"
description = "AI agents change Dev and Ops differently: they take on code production for developers while extending established automation and orchestration practices in Ops."
social_description = "Agents shift Dev toward orchestration and add a new layer to Ops automation."

date = 2026-09-19T12:00:00+02:00
category = "Essay"
tags = [
  "AI agents",
  "software development",
  "developers",
  "Ops",
  "DevOps",
  "automation",
  "orchestration",
  "infrastructure",
  "SRE"
]

draft = false
+++

*An asymmetric transformation*

AI agents are already taking over part of the daily work of developers and Ops engineers.

But this automation is not transforming both professions in the same way.

For developers, it directly affects a core activity: writing code.

For Ops, it mainly adds another layer of abstraction to a discipline already built around automation and orchestration.


1. Dev Shifts from Production to Orchestration
--------------------------------------------------------------------------------

### Producing Software →

Software development has historically centered on writing code: developers translated needs directly into software.

Despite advances in tools and layers of abstraction, developers generally remained the authors of the source code. Their tools made this work easier without taking over most implementation decisions.

### → Orchestrating Its Production

With agents, this relationship changes.

Developers can describe their intent, provide context, define constraints, delegate implementation, and then validate the result.

Writing code can now be partially or even entirely delegated. Developers can therefore focus more on what comes before and around production: understanding business needs, designing the architecture, breaking down problems, and validating the result.

They remain responsible for the software without necessarily writing the code themselves. Increasingly, they orchestrate the systems that produce it.[^1]


2. Ops Extends Its Approach to Orchestration
--------------------------------------------------------------------------------

### Orchestrating Through Automation →

For Ops, this indirect relationship with the outcome is much less new.

The distinction is not absolute, however: Ops engineers also write code, and developers already practice orchestration. The main difference is how central these activities are to each profession.

Managing infrastructure already involves controlling systems through other systems.

In many cases, Ops engineers no longer configure every component manually. They describe a desired state, and automated systems help apply and maintain it.

Ops work has thus been moving away from direct execution for a long time, without fundamentally changing the nature of the profession.

### → Orchestrating Through Agents

Agents add another layer to this process.

Ops engineers can now describe a desired outcome and let an agent determine the actions needed to achieve it. During an incident, they can also delegate part of the diagnosis and remediation to an agent.

Their autonomy and less deterministic behavior require appropriate safeguards.[^2] This uncertainty differs from that of traditional infrastructure, but it calls for practices already familiar to Ops: setting limits, monitoring systems, and maintaining control.

This continuity does not rule out major changes in day-to-day work.


Conclusion — Two Converging Paths
--------------------------------------------------------------------------------

A core activity of software development is changing, while Ops continues an existing shift toward greater abstraction.

The experience of Ops suggests that a profession can delegate much of its execution without disappearing: orchestration and control then become even more important.

As agents take over more execution, software development moves toward an approach that has long been familiar to Ops: **not just producing, but orchestrating what produces.**

---

[^1]: Birgitta Böckeler, *Harness engineering for coding agent users*, Martin Fowler, 2026. [Read the article](https://martinfowler.com/articles/harness-engineering.html)
[^2]: Ioannis Papapanagiotou, Stevan Malesevic, Chris Heiser, and Ruslan Meshenberg, *AI in SRE: How Google is Engineering the Future of Reliable Operations*, Google SRE. [Read the article](https://sre.google/resources/practices-and-processes/ai-engineering-reliable-operations/)

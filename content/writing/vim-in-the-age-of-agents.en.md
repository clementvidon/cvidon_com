+++
title = "Vim in the Age of Agents"
seo_title = "Vim in the Age of Agents — Customization’s Comeback"
description = "How AI agents lower the cost of customizing Vim and make programmable, composable software more valuable to its users."
social_description = "Why Vim’s deep configurability matters more in the age of agents."

date = 2026-09-19T13:00:00+02:00
category = "Essay"
tags = [
  "Vim",
  "AI agents",
  "text editors",
  "software customization",
  "developer tools",
  "composability",
  "Unix philosophy",
  "agent-compatible software",
  "MCP"
]

draft = false
+++

*Customization’s Comeback*

When I picked up an old Vim configuration that had been gathering dust, I wanted to adapt its existing behavior to the way I work today. With an agent, I could describe the behavior I wanted, try it out, then ask for adjustments.

That experience made me reconsider a longstanding Vim trade-off: its freedom of customization versus the time required to take advantage of it. This article is not about AI plugins, mappings, or muscle memory, but about the extensive configurability whose full potential has long required a significant investment.

Vim serves as an example here, but I apply the same approach to all my configurable tools, keeping their configurations in a single repository so I can evolve them while maintaining a consistent experience across tools.


1. Agents Are Changing What Makes Software Competitive
--------------------------------------------------------------------------------

*Vim hasn't changed. Its environment has.*

### A Longstanding Trade-off

Choosing an editor involves a trade-off between immediate benefits and long-term adaptability.

- **Relying on out-of-the-box features**: an immediate productivity gain, but more limited potential for long-term optimization.
- **Investing in customization**: an initial loss of productivity, but greater potential for long-term gains.

### A New Intermediary

With agents, users no longer have to deal with software on their own. Part of its configuration and use can be delegated to agents, reducing the initial cost of customization.

### A New Criterion

Agent compatibility therefore becomes a new criterion for evaluating software: not only what it offers directly to users, but also the primitives it makes available to agents for configuring and using it.


2. The Main Constraint Becomes the Main Strength
--------------------------------------------------------------------------------

*What used to cost us time now gives us leverage.*

### The Price of Freedom

Understanding, configuring, and maintaining an environment takes time away from the very work that customization is supposed to improve.[^1]

### From Intent to Configuration

Agents change that equation. "This is how I want to work" can now be enough as a starting point: the user describes the desired behavior, and the agent handles its technical implementation.

The user no longer needs to identify all the relevant capabilities of the software in advance.

In my notes, for example, I wanted a shortcut to navigate between titles in the index and their corresponding sections in the document, while adjusting the view to position each destination properly on screen. I simply described this behavior, and the agent combined search, navigation, and view positioning to implement it.

Doing it myself would have meant looking for existing solutions, identifying the right primitives, then implementing and debugging the shortcut.

### Deep Customization Becomes Accessible

Configurability is no longer just a theoretical capability. Explicit, stable, and composable customization mechanisms give agents the leverage they need to turn these intentions into actual behavior.

The implementation effort is significantly reduced: most of the implementation can be delegated, while the user remains responsible for evaluating the result.


3. Composability Becomes a Decisive Advantage
--------------------------------------------------------------------------------

*A few building blocks, endless combinations.*

### Primitives Rather Than Predefined Uses

Vim is not merely configurable: it exposes programmable, composable primitives.  Commands, operators, motions, registers, and scripting capabilities provide building blocks for creating new workflows.

The navigation shortcut described earlier illustrates this: the agent combined existing search, navigation, and view positioning mechanisms to create a behavior that none of them provides on its own.

This composability also extends beyond Vim itself. True to the Unix philosophy, Vim can combine its own primitives with external tools to build richer workflows.[^2]

### Bounded Freedom

Enough freedom for an agent to adapt the software deeply, enough structure to keep that freedom under control.

Without explicit principles, an agent may optimize for an immediate request at the expense of the overall coherence of the environment.

I therefore gradually refined the instructions and documentation guiding the agent to establish principles it should follow: prefer native mechanisms, respect each tool's intended role, and only add custom behavior when a concrete need justifies it.

This work continues as I use my tools: each improvement can also help refine how the agent adapts them.


4. Vim May Only Be a Symptom
--------------------------------------------------------------------------------

*Vim may be one example of a broader phenomenon.*

### Accidental Compatibility

Vim was not designed for agents, and it is far from an ideal model for them. Yet many of the properties that make it adaptable have become particularly valuable in the age of agents.

### Building for the Age of Agents

The Model Context Protocol (MCP) now standardizes a way to expose software capabilities to agents. But an interface for accessing those capabilities does not guarantee a malleable underlying architecture.

What if the challenge were not only to let agents use software, but also to let them adapt it?

Building for the age of agents might then be less about integrating AI into every feature and more about designing software malleable enough to be continuously adapted to how it is used.

*This idea is explored further in [Another Take on AI-Native](https://cvidon.com/writing/another-take-on-ai-native/), which examines software architectures designed for this kind of adaptation.*

---

[^1]: Wendy E. Mackay, *Triggers and Barriers to Customizing Software*, CHI, 1991. [Read the paper](https://doi.org/10.1145/108844.108867)
[^2]: Rob Pike and Brian W. Kernighan, *Program Design in the UNIX Environment*, AT&T Bell Laboratories Technical Journal, 1984. [Read the paper](https://lists.gnu.org/archive/html/nmh-workers/2012-11/pdfGsAjwogf3t.pdf)

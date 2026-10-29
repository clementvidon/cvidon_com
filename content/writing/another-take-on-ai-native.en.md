+++
title = "Another Take on AI-Native"
seo_title = "Another Take on AI-Native — Software you can shape"
description = "What if AI-native software let users adapt their tools with agents? An essay on malleable software, composable primitives, and lasting adaptations."
social_description = "AI-native software could let users reshape their tools with agents."

date = 2026-09-19T14:00:00+02:00
category = "Essay"
tags = [
  "AI-native",
  "AI agents",
  "malleable software",
  "software architecture",
  "software customization",
  "composability",
  "automation",
  "MCP",
  "user agency"
]

draft = false
+++

*Software you can shape*

“AI-native” generally describes products designed around AI, rather than products that simply have AI features added to them. But the boundaries of the term are still shifting.

AI-native could also describe software designed to be adapted by its users to meet their needs, with the help of agents.

Agents could help realize a long-held ambition in software design: malleability.[^1] If the software’s architecture supports it, each adaptation could become the starting point for the next.


1. AI as a feature, a user, or a builder
--------------------------------------------------------------------------------

*AI can be part of software, use it, or build it.*

### AI as a feature

This is the most visible form today: built-in chatbots, recommendation systems, content generation, and assisted search become product features.

AI remains confined to a capability defined by the product’s designers.

### AI as a user

With agents, AI becomes a user of the software. CLIs, APIs, and MCP let agents use its functions directly to produce a result.

AI is no longer an internal feature: it operates the software.

### AI as a builder

The same interfaces can go further when they let an agent change the tool itself: its configuration, automations, workflows, extensions, or new combinations of primitives that persist over time.[^2]

The goal is no longer just to produce something with the software, but to change how it will be used afterward.

These three forms can coexist. Here, we focus on the third.


2. From one-off gains to compounding gains
--------------------------------------------------------------------------------

*An output is consumed. A tool can improve.*

**A one-off gain**

When an agent generates an image, writes a document, or performs an action in an application, the benefit is largely tied to that task.

`intent → agent → result`

The tool itself remains unchanged for the next task.

**A lasting gain**

When the agent adapts the tool itself, some of its work remains available for future use.

`intent → agent → tool adaptation → future use`

An automation, configuration, or extension can then benefit subsequent tasks.

**Accumulating context**

Each adaptation incorporates some of the user’s context: their habits, preferences, constraints, or workflows.

The context shared with the agent gradually takes shape in the tool itself.

The environment progressively adapts to its user, while also becoming more effective for the agents working within it.


3. This loop depends on architecture
--------------------------------------------------------------------------------

*An interface is not enough.*

### Primitives rather than predefined uses

To remain adaptable, software must give agents enough to work with:

```text
Ability to change
- stable primitives
- composition
- configuration
- extension

Ability to understand
- documented or discoverable capabilities
- observable state and behavior

Ability to connect
- accessible data
- interoperability

Ability to build on changes
- persistent adaptations
```

The goal is no longer to anticipate every use case, but to provide enough building blocks for new ones to be created.

### Freedom within clear boundaries

Malleability also depends on a clear boundary between what can be adapted and what must remain stable.

```text
- configurable / extensible surface
- invariants / stable boundaries
- permissions
- isolation
- validation
- undo
- versioning
```

In software such as [Vim](https://cvidon.com/writing/vim-in-the-age-of-agents/), much of the behavior can be customized without changing the editor’s core. This separation offers considerable freedom while preserving a predictable foundation.

Malleability calls for limits in the right places, not their absence.

### Where does MCP fit?

MCP (*Model Context Protocol*) standardizes a way to expose software capabilities to agents.[^3] To understand its role, consider three layers:

```text
Architecture
→ what the software allows people to change

Interface
→ how the agent accesses those possibilities
  files, shell, CLI, API, MCP, scripting…

Agent
→ its ability to understand and combine those possibilities
```

MCP operates at the interface layer. Its power therefore depends less on the protocol itself than on what the software’s architecture makes available through it.


4. Shaping our environments together
--------------------------------------------------------------------------------

*From intent to change.*

### From delivered software to shaped software

In its simplest form, the conventional model looks like this:

`design → software → use`

The model proposed here looks more like this:

`design → space of possibilities → human + agent → ongoing adaptation`

Developers define the primitives, rules, and safeguards. Users bring their needs and context. Agents turn those into concrete changes and implement them.

### The human stays in the loop

This does not mean software that continually rewrites itself on its own.

The human retains the intent and judgment; the agent handles the implementation.

A need could also emerge from observing how the software is used: an agent that notices a repeated sequence of actions could suggest automating it.  The adaptation would then begin with an implicit need, while remaining guided or approved by the user.

### Another criterion for AI-native software

What if being AI-native also meant that software could be shaped by its users with the help of agents?

The question would then be as much about AI’s place within the software as about what its architecture lets users change with AI.

---

[^1]: Geoffrey Litt et al., *Malleable Software*, Ink & Switch, 2025. [Read the article](https://www.inkandswitch.com/essay/malleable-software/)
[^2]: Andy Matuschak, *A startling glimpse of malleable software: LLM-generated Obsidian plugins*, 2025. [Read the article](https://andymatuschak.org/files/2025-03-31.html)
[^3]: Model Context Protocol, *Understanding MCP servers*. [Read the documentation](https://modelcontextprotocol.io/docs/learn/server-concepts)

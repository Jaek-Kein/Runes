# Runes

**A new way to pair-code with agents.**

A marker-driven code flow visualization and collaboration project for agent-assisted web development.

**Status:** Planning · **Focus:** Web Development 

---

## Overview

Runes is an open-source project exploring a new way for developers and AI coding agents to understand, navigate, and collaborate on web applications.

As AI agents take on more implementation work, the way developers interact with code is changing. Yet most development tools still expect humans to navigate and understand code through files, functions, and traditional source-level interfaces.

Runes proposes a different approach: **let agents leave meaningful markers as they write code, transform those markers into visual representations of application flows, and use those representations as a shared interface for development.**

Starting with code flow visualization, Runes aims to evolve into a workspace where developers can explore features, express architectural intentions, and collaborate with coding agents through interactive graphs.

Rather than replacing source code or traditional development tools, Runes seeks to introduce a new layer of interaction between developers, agents, and the code they work on.

## Motivation

### The way we write code has changed. The way we work with it hasn't.

AI coding agents have significantly reduced the effort required to implement features.

Developers can now delegate substantial implementation work to agents, but understanding and modifying the resulting code often requires the same manual exploration as before.

We still navigate files, trace function calls, inspect state transitions, and reconstruct relationships between components.

Sometimes, reading agent-generated code feels like onboarding to a new project over and over again.

Other times, it feels like being assigned as a reviewer to every pull request.

But the problem goes beyond code reading.

When developers want to change a feature, they must first understand its structure, translate their intentions into instructions, and rely on agents to interpret those instructions correctly.

Even when working with an AI coding partner, much of the collaboration still happens through natural language and source code.

**What if developers and agents could share a visual understanding of the application instead?**

Runes starts with this question:

> What if we could start with what matters and reveal the implementation details only as we need them?

## Core Concept

### Leave a mark. Follow the flow.

Runes introduces a lightweight annotation convention designed for AI coding agents to use during development.

Instead of requiring developers to manually document every function and relationship, agents leave semantic markers as they implement or modify code.

For example:

```tsx
// # £LoginPage.entry
export default function LoginPage() {
  return <LoginForm />;
}

// # £handleSubmit.func
async function handleSubmit() {
  await login();
}

// # £login.http
async function login() {
  return fetch("/api/login", {
    method: "POST",
  });
}
```

Markers describe the semantic roles of functions, components, and other parts of the application.

Runes aims to combine these markers with source code analysis to construct an interactive representation of the application.

A simplified flow might look like this:

```text
LoginPage [entry]
    |
    v
LoginForm [component]
    |
    v
handleSubmit [func]
    |
    v
login [http]
    |
    v
POST /api/login
```

This graph is a conceptual example. Actual relationships will be determined through source code analysis rather than marker order alone.

The initial goal is to help developers understand where a feature begins, how it progresses, and which parts of the application are involved.

But visualization is only the beginning.

### From understanding code to shaping it

Runes envisions a development workflow where developers can interact directly with the structure of an application.

Instead of describing every architectural change through natural language, developers could manipulate a visual representation of the code.

For example, they could introduce a validation step between two functions, propose a different connection between components, or define how a feature interacts with shared state.

Runes would translate these interactions into structured development intentions that coding agents could use to modify the underlying source code.

The resulting implementation would then be analyzed and reflected in the graph.

```text
Source Code
    |
    v
Semantic Markers
    |
    v
Interactive Flow Graph
    |
    v
Developer Intent
    |
    v
AI Coding Agent
    |
    v
Updated Source Code
    |
    +----> Graph Synchronization
```

Through this cycle, Runes aims to make visual representations more than documentation.

**They become a shared development interface between humans and agents.**

## Planned Features

### Agent-Native Marking

Runes will provide an agent skill that guides coding agents to create, update, and validate semantic markers during development.

Markers are intended to become part of the agent's normal implementation workflow, minimizing the need for manual annotation.

### Code Flow Visualization

Runes aims to transform marked code into interactive graphs representing relationships between functions, components, hooks, stores, and API requests.

Developers will be able to navigate from high-level application flows to the underlying source code.

### Live Synchronization

The visualizer is planned to respond to source code changes and update the corresponding graph.

This will allow developers to observe how application structures evolve as agents implement and modify features.

### Feature-Focused Development

Rather than requiring developers to explore an entire codebase, Runes aims to support feature-scoped workspaces.

Developers will be able to focus on specific features, explore their dependencies, and understand how changes may affect related functionality.

These focused views may also serve as structured context for coding agents.

### Visual Design and Graph Editing

Runes aims to allow developers to express architectural intentions directly through graph interactions.

Potential capabilities include reconnecting nodes, introducing processing steps, and defining relationships between functions and application state.

Graph modifications will represent proposed changes rather than immediate source code mutations.

### Human–Agent Collaboration

The long-term vision of Runes is a collaborative development workspace where humans and agents work from a shared representation of the application.

Developers express what should change, agents implement the requested changes, and Runes helps verify that the resulting code reflects the intended structure.

## Architecture

Runes is planned around three main components.

| Component | Responsibility |
|---|---|
| **Runes Skill** | Guides coding agents to create, maintain, and validate semantic markers |
| **Runes Core** | Parses markers, resolves symbols, analyzes code relationships, and generates graph data |
| **Runes Visualizer** | Provides interactive code flow visualization and, eventually, visual development and collaboration capabilities |

### Design Principles

**Human–Agent Collaboration First**

Runes is designed around the idea that developers and coding agents should be able to work from a shared understanding of the application.

**Code as the Source of Truth**

Semantic markers and visual graphs describe code structure and intent, but the actual source code remains authoritative.

Runes should distinguish verified relationships, inferred information, and proposed changes.

**Feature-Oriented Development**

Developers should be able to focus on the functionality they are working on without repeatedly reconstructing unrelated parts of the codebase.

**Agent-Native Workflow**

Markers should be created and maintained naturally during agent-assisted development, without requiring extensive manual documentation.

**Visualize Before Modifying**

Developers should be able to understand and explore application structures before proposing changes.

**Explicit and Verifiable Changes**

Visual modifications should express development intentions rather than silently mutate source code.

Agent-generated changes should be validated against the actual implementation before being reflected as verified graph relationships.

## Roadmap

| Phase | Scope | Status |
|---|---|---|
| **V1 — Mark** | Marker specification and agent skill | Planned |
| **V2 — Visualize** | Source analysis, interactive graphs, and live synchronization | Planned |
| **V3 — Design** | Graph editing, feature-scoped workspaces, and structured change proposals | Concept |
| **V4 — Collaborate** | Human–agent collaborative development workspace | Vision |

The roadmap reflects the current direction of the project and may evolve as development progresses.

## Project Status

Runes is currently in the planning stage.

The marker syntax, architecture, supported frameworks, and implementation details are subject to change.

The project name may also change before its first public release.



A license has not yet been selected.

---

**Runes — Leave a mark. Shape the flow.**

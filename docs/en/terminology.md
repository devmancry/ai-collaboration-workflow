# Terminology

This document defines the key terms used throughout the AI collaboration documents.

Consistent terminology is important when working with both humans and AI.

Using the same term for the same concept helps avoid ambiguity in design discussions, documentation, and implementation.

---

# Formatting

When multiple expressions exist for the same concept, they may appear together in parentheses.

If multiple expressions are listed, they are separated using `/`.

The more commonly used expression appears first.

---

# Glossary

## Design

**Design** refers to the human-centered description of how a system is intended to work.

A Design document focuses on concepts, ideas, and overall system direction rather than precise implementation rules.

Typical contents include:

- system purpose
- major concepts
- high-level structure
- design intentions
- feature descriptions

Design documents serve as the **primary explanation of the system for human understanding.**

---

## System

A **System** is a structured set of components that work together to accomplish a specific purpose.

A system typically includes:

- multiple modules
- defined relationships between components
- a clear functional objective

Examples:

```
Combat System
Enemy AI System
```

---

## Philosophy

**Philosophy** refers to the design direction or guiding mindset that should be consistently maintained throughout the system.

Philosophy defines conceptual principles rather than exact implementation rules.

Examples:

```
UI represents system state and should avoid directly modifying it
Game logic should prioritize data-driven structures
Player and AI follow the same game rules
```

---

## Pipeline

A **Pipeline** is a sequence of stages where input is processed step by step to produce a result.

Typical structure:

```
Input → Processing Stages → Result
```

Example:

```
Player Input
→ Action Selection
→ Action Chain
→ Result
```

---

## Rule

A **Rule** is a constraint that must always be followed during system operation.

Rules ensure predictable and stable system behavior.

Examples:

```
Asset Load must only be executed through an Operator
Validation runs through a tag-based system
Unit movement uses grid-based pathfinding
```

---

## System Contract

A **System Contract** defines guarantees that a system or module must uphold.

It specifies behaviors that other systems can safely rely on.

Examples:

```
Validation always reflects the current scene state
Once an Action Chain begins, it must execute until the End stage
Successful Asset Load always produces a scene asset instance
```

---

## Architecture

**Architecture** defines the structural organization of a system and the relationships between its components.

Architecture describes:

- system components
- relationships between modules
- data flow
- core system principles

Architecture does **not** define:

- function-level rules
- detailed implementation logic
- specific API definitions

---

## Spec (Specification)

A **Spec** defines the rules required to implement a specific system or feature.

A Spec describes **how the system must behave.**

Typical contents include:

- behavior rules
- inputs and outputs
- state transitions
- implementation constraints

---

## Source of Truth

A **Source of Truth** is the authoritative reference for a specific concept, rule, or system.

It defines where the final and reliable definition of information exists.

Clearly identifying a Source of Truth helps prevent:

- inconsistent rules across documents
- mismatches between design and implementation
- unclear document responsibilities

Examples:

```
Core document → Architecture Source of Truth
Spec document → Rule Source of Truth
Reference document → Implementation Source of Truth
```

---
# AI Collaboration Case Study — Discovering a Design Gap and Creating a Spec

This document records a case that demonstrates how the method described in the **AI Collaboration Development Workflow** document is applied in an actual design process.

This case does **not describe designing a completely new system from scratch**.

Instead, it describes a situation where **a design gap was discovered and resolved while preparing for implementation based on existing design documents**.

The project already had the following documents.

```
Design
Core
Some feature Specs
Some References
```

In this state, a conversation with AI began in order to **start the next implementation task**, and during the discussion **missing elements in the existing design were discovered.**

As a result:

- new concepts not previously present in the Design were introduced
- the system structure was clarified
- a **Spec document was created based on the newly organized structure**

This document records the flow of that process.

---

## 0. Summary of the Case Flow

The process in this case proceeded as follows.

```
Define implementation goal
→ Design questions arise
→ Discover gaps in the existing design
→ Design unit structure
→ Organize the Core document
→ Write the Spec
```

This case demonstrates **how AI collaboration can be used to identify and resolve gaps in system design.**

---

## 1. The Conversation Begins with an Implementation Goal

The conversation began while preparing for a specific implementation task.

The goal was **to implement a game victory and defeat condition system.**

After deciding to implement the victory/defeat conditions, the first questions asked were:

- **How should the Protagonist be identified?**
- **How should the MotherAI be identified?**

For example:

- Is the player defeated when the protagonist dies?
- Is the player defeated when the Mother AI is destroyed?

To implement such rules, the system first needs **a way to distinguish those units.**

This question was not merely an implementation question; it was **a design question related to the structure of the system.**

```
[Methodology Stage — Design Discussion]
```

---

## 2. Questions Continue While Reviewing AI Suggestions

The AI proposes several possible approaches.

For example:

- distinguishing entities using roles
- identifying them using specific IDs
- using tags

However, a conclusion is **not made immediately.**

Instead, further questions are raised:

- What if the same character appears multiple times?
- What if an enemy later becomes an ally?
- What if abilities differ between stages?
- How should costume changes be handled?

These questions are not simply objections.

They are **checks for edge cases that might break the design.**

In AI collaboration, it is important not to accept AI suggestions blindly, but instead to **validate the design by examining edge cases and potential failure scenarios.**

```
[Methodology Stage — Design Discussion]
```

---

## 3. The Focus Shifts to Unit Structure Design

Through these questions, the real issue becomes clearer.

The problem is not simply:

```
How to distinguish the protagonist
```

but rather:

```
How units should be managed across the entire game
```

This reveals a **larger structural design problem.**

As a result, several concepts emerge:

- base units
- player-owned units
- units placed in a stage
- visual variants (appearance changes)

At this point, the conversation effectively shifts to **designing the unit data structure.**

This design **did not exist in the original Design document.**

In other words, during implementation preparation, **a design gap in the Design document was discovered.**

---

## 4. The Human Proposes the Initial Design

A critical turning point occurs here.

Instead of the AI generating the design, **the user proposes an initial structural idea.**

For example, the following structure is suggested:

```
Base unit database
Player unit list
Stage placement data
Visual variants
```

Further questions are then explored based on this structure:

- Can the same unit be spawned multiple times?
- Should enemy and ally versions of a unit be separated?
- How should purely visual variations be handled?

Through this process, the design becomes progressively clearer.

A key principle of AI collaboration appears here:

```
AI does not create the design on its own.
The human proposes the structural draft,
and the design is reviewed collaboratively with AI.
```

---

## 5. Organizing the Design into Documents

Once the structure becomes sufficiently clear, the process moves to the **documentation stage.**

```
[Methodology Stage — Documentation]
```

The design is first organized into a **Core-level structural document.**

This includes:

- unit data structure
- roles of each data component
- override rules
- the role of visual variants
- continuity when switching between enemy and ally states

This document is written as **a structural description that both humans and AI can read and understand.**

---

## 6. Writing the Spec Document

After the Core structure is organized, a **Spec document** defining the implementation rules is created.

The Spec document clearly defines:

1. what must be implemented
2. what will not yet be implemented
3. which rules must always be followed

The Spec document becomes **the reference used by Implementation AI when generating code.**

---

## 7. The Decision Not to Implement Everything at Once

Finally, an important decision is made.

The system will **not be implemented all at once.**

Instead, the implementation will be divided into phases.

For example:

```
Phase 1 — unit spawning structure
Phase 2 — player units
Phase 3 — stat overrides
Phase 4 — visual variants
```

Dividing implementation into phases helps prevent problems such as:

- AI expanding the system excessively
- multiple systems being connected prematurely

---

## 8. Current State of the Case

This case concludes at the stage where the **Spec document has been written.**

From the perspective of the methodology, the current state is:

```
Design
→ Core
→ Spec
```

The next steps will include:

```
Updating the Design
Creating an Implementation Plan based on the Spec
Reviewing the Implementation Plan
Generating code
```

The collaboration process during the Implementation Plan and code generation stages will be covered in a future case document.

---

# What This Case Demonstrates About AI Collaboration

This case demonstrates an approach that differs from using AI as a simple code generation tool.

The process follows these characteristics:

```
Start from an implementation goal
→ discover problems through design questions
→ the human proposes an initial structure
→ review the design collaboratively with AI
→ organize the structure into a Core document
→ define implementation rules in a Spec
```

In other words,

```
the design is thoroughly organized
before requesting code from AI
```

This case also demonstrates a real example of **discovering and resolving design gaps through AI collaboration during implementation preparation.**

---

# How to Apply This Approach

To begin design discussions with AI in a similar way, the following questions can be used as a starting point.

```
1. Clearly define the feature to be implemented

Example
"I want to implement a victory/defeat condition system."

2. Ask about the concepts that the feature depends on

Example
"How can the protagonist be identified at the system level?"

3. Ask about scenarios that might break the design

Example
"What if the same character appears multiple times?"

4. Propose a structural draft and review it

Example
"I'm considering a structure with a base unit DB, player units, and stage units. What do you think?"
```

Through this process, a workflow of

**design questions → structural design → Core → Spec** can be established.
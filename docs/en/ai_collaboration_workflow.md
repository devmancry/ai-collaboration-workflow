---

# AI Collaboration Development Workflow

---

# 1. Introduction

Recently, development workflows that utilize AI have been increasing rapidly.

However, many cases still face the following two limitations.

- When most tasks are delegated to AI, it becomes **difficult to maintain control over the structure and direction of the project**
- AI is used only as a simple assistant tool and is **limited to small tasks or repetitive work**

This document explains a collaboration workflow that addresses these limitations and **actively leverages the strengths of AI in both design and implementation.**

---

## 1.1 Core Concept

```
Use AI not merely as a code generation tool,
but as a collaborative partner in both design and implementation.
```

This approach has the following characteristics.

- The human **retains control of the design direction**
- AI is actively used as **a reviewer, a collaboration partner, and a learning tool throughout the design and implementation process**
- Work proceeds through the flow
    
    **Design → Documentation → Implementation → Review → Documentation Update**
    
- Because collaboration is centered around documentation, **the workflow remains stable even in large-scale projects**

Readers of this document will gain two things.

- An understanding of the structure and principles of this collaboration workflow
- The ability to **start applying the same workflow in real projects**

---

## 1.2 Basic Principle

The key idea of this method is **clearly separating the roles in AI collaboration.**

Many AI-based development workflows follow a simple collaboration structure.

```
Human
  ↓
AI
```

However, this workflow divides collaboration into **three roles.**

```
Human (Planner)
Design AI
Implementation AI
```

Each role focuses on a different part of the development process.

```
Human
→ Determines design direction and makes final decisions

Design AI
→ Design discussions, structural review, documentation organization

Implementation AI
→ Implementation planning, code generation, test suggestions
```

**Actual design work** is led by the human in collaboration with Design AI.

**Actual implementation** is performed by Implementation AI, while the human and Design AI review the generated code.

In practice, this collaboration structure follows the workflow below.

```
Idea
(Human)
     │
     ▼
Design Discussion
(Human + Design AI)
     │
     ▼
Documentation
(Human + Design AI)
     │
     ▼
Code Generation
(Implementation AI)
     │
     ▼
Testing
(Human)
     │
     ▼
Code Review and Feedback
(Human + Design AI)
```

By separating collaboration roles in this way,

the responsibilities of design and implementation become clearer, and AI collaboration can proceed in a more stable manner.

---

## 1.3 Why This Method Matters

In software development, **design is an extremely important stage.**

The structure and rules of a system are determined during the design phase, and these decisions strongly influence the stability and scalability of later implementations.

This is equally true in AI-assisted development.

The ability to generate code is important, but **thorough discussion and review of the design** is just as critical.

However, for people who are not programmers, thinking about system design is not easy.

It can be difficult to determine:

- what structure is appropriate
- what problems may occur
- which approach is more suitable

AI can be used in this process not just as a code generator, but as **a collaboration partner and learning tool for design discussions.**

Through conversations with AI, one can:

- ask questions and understand unfamiliar concepts
- explore better structures and approaches
- identify potential problems in advance
- discover new ideas and inspiration

This process is particularly helpful for **non-programmers who want to understand and improve system design.**

In this method, design discussion and code generation are **separated into different roles.**

- **Design AI** focuses on design discussion and structural review
- **Implementation AI** focuses on implementation and code generation

This separation allows both **design stability and implementation efficiency** to be maintained.

---

# 2. Types and Roles of Documents

In this collaboration structure, **documentation plays a critical role.**

Each document has a different responsibility, and documents are not merely files used to provide information to AI.

Instead, they function as **part of the collaboration structure that connects design discussion and implementation.**

---

## 2.1 Documents Used

This method uses the following documentation structure.

```
Design Document
→ The system design intended by the human

Core Document
→ The system structure agreed upon with AI

Spec Document
→ Implementation rules for AI

Reference Document
→ Explanation of the actual code structure
```

This structure allows:

- design intentions to be clearly recorded
- AI to maintain consistent standards while working
- system structure to remain stable throughout long development cycles

---

## 2.2 How Documents Are Written

In this collaboration structure, each document type is written differently.

Design documents are written primarily by humans.

Core, Spec, and Reference documents are drafted by AI and then reviewed by humans.

```
Design
→ Written primarily by humans (AI assists)

Core
→ AI draft + human review

Spec
→ AI draft + human review

Reference
→ AI draft + human review
```

---

## 2.3 Design

The **Design document** is a human-centered design document.

It corresponds to documents commonly used in practice, such as **planning documents or system design documents.**

For example, in a game project, this would be equivalent to a **game design document.**

Design documents focus on explaining the system for human understanding and may include:

```
The purpose of the project or system
Core ideas and design philosophy
Overall structure and major system concepts
Descriptions of key features or systems
Design intentions and problem-solving approaches
Future expansion directions or considerations
```

Design documents focus on **concepts and design direction**, rather than detailed implementation rules or APIs.

In other words, the Design document is **a document for humans to understand the system**, and serves as the **Project Design Source of Truth** for the overall design direction.

---

## 2.4 Core

The **Core document** explains the overall structure of the system and its core rules.

It organizes design concepts into a **structured form**, clearly defining how the system is composed.

This includes:

- system components
- relationships between systems
- data flow
- core rules (System Contracts)

Core documents include the **entire system structure regardless of implementation status**, and serve as the **Architecture Source of Truth**.

---

## 2.5 Spec

The **Spec document** defines implementation rules.

It explains **how a specific feature or system must behave.**

For example, it may include:

- behavior rules
- inputs / outputs
- state changes
- implementation requirements

Spec documents also record the implementation status.

```
STATUS
implemented
partial
planned
```

Spec documents serve as the **Rule Source of Truth** for system behavior.

---

## 2.6 Reference

The **Reference document** explains the actual implementation structure.

It is written based on the current state of the code and may include:

- code structure
- processing flow
- major APIs

Reference documents serve as the **Implementation Source of Truth**.

Therefore, **unimplemented content should exist only in Core and Spec documents.**

---

# 3. Development Process

In this collaboration structure, development proceeds through the following **iterative cycle.**

```
Idea
→ Design Discussion
→ Documentation
→ Implementation
→ Review
→ Documentation Update
```

Each stage serves a different purpose, and by repeating this cycle, system design and implementation gradually become more refined.

---

## 3.1 Idea Stage

Development begins with **an idea proposed by a human.**

The human presents an initial idea and explains it to AI, refining the concept through discussion.

At this stage, the following may be clarified:

- the problem to be solved
- the feature to be implemented
- system expansion direction
- initial design ideas

---

## 3.2 Design Discussion Stage

Once the idea is organized, the **design discussion stage** begins.

At this stage, the human and **Design AI** collaborate to define **system structures and rules in enough detail that developers can realistically implement them.**

A critical point in this stage is that **the human retains control of the design.**

The human should actively ask questions such as:

- What potential problems might occur?
- Are there better structures or approaches?
- Are new concepts or technologies required?

Rather than accepting AI suggestions directly, the human must **evaluate them and determine the design direction.**

At this stage, **code is not written yet.**

Only after the system structure and rules have been sufficiently reviewed through design discussions does the process move to the next stage.

---

## 3.3 Documentation Stage

Once design decisions are made, they are **organized into documents.**

Documents are structured in the following order.

```
Design → Core → Spec
```

---

### 3.3.1 Organizing the Design

First, the **Design document** is organized.

The Design document is primarily written by humans and describes the design direction at a conceptual level.

---

## 3.4 Implementation Stage

After documentation is completed, the workflow moves to the **implementation stage.**

At this stage, **Implementation AI** performs the implementation tasks.

Implementation AI works based on the following documents.

```
Core
Spec
```

The Core document provides the overall system structure, while the Spec document provides **specific rules for the functionality that must be implemented.**

---

### 3.4.1 Writing the Implementation Plan

An important point here is that **AI does not immediately generate code.**

Instead, Implementation AI first creates an **Implementation Plan.**

This plan may include:

- structure of the feature to be implemented
- required classes or modules
- data structures
- processing flow
- expected implementation stages

---

### 3.4.2 Reviewing the Implementation Plan

The Implementation Plan is **reviewed by both the human and the Design AI.**

At this stage, the following points are checked:

- whether the plan matches the Core architecture
- whether Spec rules are correctly reflected
- whether it conflicts with the design intent
- whether better structures exist

If necessary, the plan may be revised at this stage.

---

### 3.4.3 Code Generation

Only **after the implementation plan is approved** does Implementation AI generate the actual code.

The implementation process therefore follows this order:

```
Spec definition
→ Implementation Plan creation
→ Plan review
→ Plan approval
→ Code generation
```

This structure helps:

- reduce inconsistencies between design and implementation
- improve code quality
- maintain stable AI collaboration

---

## 3.5 Review Stage

After implementation progresses, the **review stage** begins.

At this stage, the following are checked:

- whether the code follows Spec rules
- whether the system structure matches the Core architecture
- whether unexpected problems have occurred

If necessary, Design AI may be used again to re-evaluate the structure or rules.

---

## 3.6 Documentation Update Stage

In the final stage, documents are **updated to reflect the current state.**

The following documents are updated.

```
Spec
Reference
```

- Spec → update implementation status
- Reference → describe the actual code structure

Through this process, documents remain **synchronized with the current state of the project.**

---

## 3.7 Iterative Development Cycle

This cycle does not occur only once.

It continues throughout the entire project.

```
Idea
→ Design Discussion
→ Documentation
→ Implementation
→ Review
→ Documentation Update
→ Idea...
```

Through this repeated process:

- the design becomes more refined
- documentation evolves into the project's knowledge base
- AI collaboration becomes increasingly stable

---

# 4. Practical Tips

When following this workflow, it is recommended to summarize discussions and move to a new conversation at the following points:

- when one development cycle has been completed
- when a specific design or implementation unit has been completed
- when the conversation becomes long and AI begins to lose context or performance decreases

Additionally, after each development cycle, it is important to ensure that outdated documents with inconsistent versions do not remain.

When updating documents, carefully verify that no information has been accidentally omitted and that the documentation accurately reflects the current state of the project.
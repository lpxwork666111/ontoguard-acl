# OntoGuard: Enforcing Action Admissibility for LLM Agents in Complex Interactive Environments

<p align="center">
  <img src="assets/framework.png" width="85%">
</p>

<p align="center">
    📄 Paper | 🧠 Neuro-Symbolic Agents | 🔒 Constraint-Aware Planning
</p>

---

## Overview

OntoGuard is a neuro-symbolic framework designed to improve the reliability and grounding of Large Language Model (LLM) agents operating in complex interactive environments.

Unlike existing methods that rely primarily on implicit statistical learning or sparse reward signals, OntoGuard explicitly enforces:

- **Behavioral Admissibility**
- **Environmental Admissibility**

through dynamically constructed ontological constraint graphs.

During inference, OntoGuard acts as an active verification layer between the LLM planner and the environment, intercepting invalid actions before execution and triggering self-correction when violations occur.

---

## Key Features

### ✅ Explicit Constraint Verification

OntoGuard introduces a dual-check mechanism:

- **Behavioral Constraints**
  - Temporal dependencies
  - Procedural correctness
  - Task-specific prerequisite actions

- **Environmental Constraints**
  - Physical affordances
  - Object properties
  - State transition validity

---

### ✅ Neuro-Symbolic Constraint Construction

The framework extracts rules from:

- Oracle trajectories
- Environment state mutations
- LLM commonsense knowledge
- ConceptNet external knowledge

to build executable constraint graphs.

---

### ✅ Runtime Action Interception

Before execution, every generated action is validated against:

- Behavioral Graph (`G_beh`)
- Environmental Graph (`G_env`)

Invalid actions are blocked and refined through structured feedback prompting.

---

## Framework

<p align="center">
  <img src="assets/architecture.png" width="95%">
</p>

The framework contains two stages:

### 1. Admissibility Rule Construction

- Neural-Symbolic Trace Parsing
- Behavioral Dependency Mining
- Environmental Causality Induction
- Hybrid Knowledge Completion

### 2. Constraint-Aware Planning

- Constraint Verification Loop
- Runtime Action Interception
- Adaptive Feedback Synthesis
- Self-Corrective Replanning

---

## Main Results

OntoGuard achieves state-of-the-art performance on:

- **ScienceWorld**
- **VirtualHome**

while significantly improving:

- Execution Reliability
- Task Success Rate
- Long-Horizon Stability
- Constraint Compliance

---

## Example

### Failure of Standard LLM Agents

```text
[pick up seed]

Environmental Constraint Violation:
The seed entity does not exist in the current state.

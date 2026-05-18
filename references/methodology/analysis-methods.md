# Analysis Methods Guide

## Analysis Framework

Use a progression from software engineering fundamentals to AI work systems:

```text
Software fundamentals
→ AI file engineering
→ Knowledge engineering
→ Strong-state MAS orchestration
→ Role-based team workflow
→ Quality gates, eval, observability, and automation
```

The central analytical question is how to construct a unified, high-quality workflow for AI-native software work.

## Methods

### 1. Concept Lineage Analysis

Trace how familiar engineering concepts reappear in AI work:

- SoC → small, focused knowledge artifacts and agent roles.
- Abstraction / object orientation → Skill, Rules, engineering files, Capability, and Agent Blueprint as bounded knowledge objects.
- Directory structure → address space for AI-readable knowledge.
- Interface contract → Story, AC, Blueprint parameters, output requirements, DoR, DoD.
- Testing → verification, eval cases, citation checks, browser simulation, review gates.

### 2. Case Synthesis

Extract reusable lessons from MindFlow, Pomasa, archived AI Coding / Agent engineering talks, and web references. Do not pile up cases. Use each case only when it clarifies the unified workflow.

### 3. Engineering Pattern Abstraction

Abstract recurring patterns:

- Progressive disclosure and context management.
- Filesystem as data bus.
- Strong state and handoff.
- Contract-driven cross-layer consistency.
- Deterministic tools for deterministic work.
- Evidence-backed reflection loops.
- Failures as eval cases.
- Agents as untrusted operators.
- Human experience and agent experience as separate design targets.

### 4. Speech Narrative Design

Convert analysis into spoken structure. The manuscript should read like a talk, not a report. Use short transitions, concrete engineering examples, and clear judgments. Avoid long bullet sections in the manuscript.

### 5. Citation and Lineage Verification

Every external fact, case, term, and quoted idea must map to a source ID. User original views should map to `USER-xxx`. If a claim cannot be verified, revise it as a judgment, downgrade it, or remove it.

## Required Chapter Logic

1. Start with why engineering and SDD still matter.
2. Move directly to SoC, abstraction, and directory structure.
3. Explain MindFlow as self-evolving knowledge structure.
4. Explain POMASA / MAS as strong-state orchestration.
5. Use the control taxonomy: fixed strong constraints, suggested AI autonomy, full AI control.
6. Explain Skill, engineering files, and Rules as executable knowledge with different scheduling certainty.
7. Explain Knowledge and Story, then Flyway Migration analogy.
8. Explain role-based workflow and single-repository strong state.
9. Explain automation and low-human-intervention development after the role workflow.
10. Put Agent design, speed, testing, eval, orchestration, tooling, and outlook back into the unified workflow.

## Quality Checklist

- [ ] Does the analysis serve the unified workflow theme?
- [ ] Are user original ideas preserved?
- [ ] Are MindFlow and Pomasa explained by design thought rather than project detail?
- [ ] Are references used as support rather than piled up?
- [ ] Are claims traceable to local archives, GitHub URLs, or user input?
- [ ] Does the final structure support a 60-90 minute live talk?

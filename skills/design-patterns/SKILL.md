---
name: design-patterns
description: "Trigger: design pattern, patron de diseno, SOLID, Clean Architecture, Hexagonal Architecture, Screaming Architecture, atomic design, container-presentational, over-engineering, refactor for maintainability. Choose and apply the right software design pattern or architecture style."
license: Apache-2.0
metadata:
  author: gentleman-programming
  version: "1.0"
---

## Activation Contract

Load when choosing a design pattern for a concrete problem, reviewing code for SOLID violations, deciding between Clean/Hexagonal/Screaming Architecture, structuring UI with atomic design or container/presentational, or when a pattern is proposed without a concrete forcing problem behind it.

## Hard Rules

- Never name a pattern to justify code; name the forcing problem first (what varies, what must stay closed to change), then pick the pattern that solves it.
- A pattern that adds indirection without removing duplication or isolating a real axis of change is over-engineering — reject it.
- SOLID is a set of forces, not a checklist: apply only the principle whose violation causes a real symptom (rigidity, fragility, immobility).
- In Clean/Hexagonal Architecture, dependencies point inward only; domain/use-case code has zero imports from framework, DB, or transport layers.
- In Screaming Architecture, top-level folders name the business domain (`billing/`, `shipping/`), never the framework (`controllers/`, `services/`).
- Atomic design layers (atoms → molecules → organisms → templates → pages) compose upward only; an atom never imports a molecule.
- Container/presentational: presentational components take only props and render; containers own state, side effects, and data fetching — never mix both in one file.

## Decision Gates

| Symptom | Pattern family | Look up |
|---|---|---|
| Object creation logic scattered or duplicated | Creational (Factory, Builder, Singleton, Prototype) | references/gof-patterns.md |
| Incompatible interfaces must cooperate | Structural (Adapter, Facade, Decorator, Composite) | references/gof-patterns.md |
| Behavior must vary at runtime / algorithms swap | Behavioral (Strategy, Observer, Command, State) | references/gof-patterns.md |
| Business logic coupled to framework/DB/UI | Clean or Hexagonal Architecture | references/architecture-styles.md |
| Folder structure mirrors the framework, not the domain | Screaming Architecture | references/architecture-styles.md |
| UI has duplicated markup at different granularities | Atomic Design | references/architecture-styles.md |
| Component mixes data-fetching with rendering | Container/Presentational split | references/architecture-styles.md |

## Execution Steps

1. State the concrete forcing problem in one sentence (what changes, what must not break).
2. Check the Decision Gate table; open the matching reference file for the pattern's intent, structure, and trade-offs.
3. Propose the smallest pattern that solves the stated problem — reject heavier variants applied "for the future."
4. If existing code already violates the pattern's shape, show the concrete violation with file/line before proposing the fix.
5. Confirm the pattern doesn't cross an architecture boundary already in place (e.g., a Strategy implementation must not import infra directly inside a Hexagonal domain layer).

## Output Contract

Report: forcing problem identified, pattern(s) proposed, one-sentence trade-off, and file/line of any violation found.

## References

- references/gof-patterns.md — GoF catalog (creational/structural/behavioral) with intent and when to avoid.
- references/architecture-styles.md — Clean/Hexagonal/Screaming Architecture, Atomic Design, Container/Presentational.

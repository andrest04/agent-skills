---
name: design-patterns
description: "Trigger: design pattern, SOLID, Clean Architecture, Hexagonal Architecture, Screaming Architecture, atomic design, container-presentational, over-engineering, patron de diseno, refactor for maintainability. Picks the pattern the problem forces."
license: MIT
metadata:
  author: andrest04
  version: "1.0"
---

## Activation Contract

Load when picking a design pattern for a concrete problem, reviewing code for SOLID violations, choosing between Clean/Hexagonal/Screaming Architecture, structuring UI with atomic design or container/presentational, or when a pattern is proposed with no forcing problem behind it.

## Hard Rules

- Name the forcing problem before naming a pattern: what varies, what must stay closed to change.
- Indirection that removes no duplication and isolates no real axis of change is over-engineering — reject it.
- Apply a SOLID principle only when its violation causes a real symptom (rigidity, fragility, immobility) — not as a checklist.
- Clean/Hexagonal Architecture: dependencies point inward only; domain/use-case code imports nothing from framework, DB, or transport.
- Screaming Architecture: top-level folders name the business domain (`billing/`), never the framework (`controllers/`).
- Atomic design layers (atoms → molecules → organisms → templates → pages) compose upward only.
- Container/presentational: presentational components take only props and render; containers own state, side effects, and data fetching.

## Decision Gates

| Symptom | Pattern family | Look up |
|---|---|---|
| Object creation scattered or duplicated | Creational (Factory Method, Builder, Singleton, Prototype, Abstract Factory) | references/gof-patterns.md |
| Incompatible interfaces or subsystems must cooperate | Structural (Adapter, Facade, Decorator, Composite, Bridge, Proxy, Flyweight) | references/gof-patterns.md |
| Behavior or algorithm must vary at runtime | Behavioral (Strategy, Observer, Command, State, +6 more) | references/gof-patterns.md |
| Business logic coupled to framework/DB/UI | Clean or Hexagonal Architecture | references/architecture-styles.md |
| Folders mirror the framework, not the domain | Screaming Architecture | references/architecture-styles.md |
| UI has duplicated markup at different granularities | Atomic Design | references/architecture-styles.md |
| Component mixes data-fetching with rendering | Container/Presentational split | references/architecture-styles.md |

## Execution Steps

1. State the forcing problem in one sentence: what changes, what must not break.
2. Match it in the Decision Gate table; open the reference file for intent, structure, trade-offs.
3. Propose the smallest pattern that solves it — reject heavier variants applied "for the future."
4. If code already violates the pattern's shape, cite the violation (file/line) before the fix.
5. Confirm the pattern doesn't cross an existing architecture boundary (e.g., a Strategy inside a Hexagonal domain layer must not import infra).

## Output Contract

Report: forcing problem, pattern(s) proposed, one-sentence trade-off, file/line of any violation found.

## References

- references/gof-patterns.md — all 22 GoF patterns (creational/structural/behavioral), matching refactoring.guru's catalog: intent, problem/solution, when to avoid.
- references/architecture-styles.md — Clean/Hexagonal/Screaming Architecture, Atomic Design, Container/Presentational (not from refactoring.guru).

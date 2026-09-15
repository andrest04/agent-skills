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

| Symptom | Pattern family | Rule prefix |
|---|---|---|
| Object creation scattered or duplicated | Creational (Factory Method, Builder, Singleton, Prototype, Abstract Factory) | `rules/creational-*` |
| Incompatible interfaces or subsystems must cooperate | Structural (Adapter, Facade, Decorator, Composite, Bridge, Proxy, Flyweight) | `rules/structural-*` |
| Behavior or algorithm must vary at runtime | Behavioral (Strategy, Observer, Command, State, +6 more) | `rules/behavioral-*` |
| Business logic coupled to framework/DB/UI, folders mirror the framework, UI markup duplicated across granularities, or a component mixes fetching with rendering | Architecture style (Clean/Hexagonal, Screaming, Atomic Design, Container/Presentational) | `rules/architecture-*` |

## Execution Steps

1. State the forcing problem in one sentence: what changes, what must not break.
2. Match it in the Decision Gate table, then read the matching `rules/<prefix>-*.md` files for intent, problem/solution, and when to avoid.
3. Propose the smallest pattern that solves it — reject heavier variants applied "for the future."
4. If code already violates the pattern's shape, cite the violation (file/line) before the fix.
5. Confirm the pattern doesn't cross an existing architecture boundary (e.g., a Strategy inside a Hexagonal domain layer must not import infra).

## Output Contract

Report: forcing problem, pattern(s) proposed, one-sentence trade-off, file/line of any violation found.

## References

One rule file per pattern under `rules/`, named `<category>-<pattern-slug>.md`:

- `rules/creational-*.md` (5) and `rules/structural-*.md` (7) and `rules/behavioral-*.md` (10) — the 22 GoF patterns, matching refactoring.guru's catalog order, each with intent, problem/solution, when to avoid, and its source URL.
- `rules/architecture-*.md` (4) — Clean/Hexagonal Architecture, Screaming Architecture, Atomic Design, Container/Presentational (not from refactoring.guru).

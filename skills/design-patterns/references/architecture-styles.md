# Architecture Styles

Not covered by refactoring.guru's pattern catalog — these are architecture/composition styles, complementary to the GoF patterns in `gof-patterns.md`.

## Clean Architecture / Hexagonal Architecture (Ports & Adapters)

- Core rule: the Dependency Rule — source code dependencies point only inward, toward the domain/use cases. Nothing inner knows anything about anything outer.
- Layers (outer to inner): frameworks/drivers (DB, UI, web) → interface adapters (controllers, presenters, gateways) → application/use cases → entities/domain.
- Ports are interfaces defined by the domain; adapters are the concrete implementations living in the outer layer (a `UserRepository` port, a `PostgresUserRepository` adapter).
- Violation signal: a domain/use-case file imports an ORM, HTTP client, or framework decorator directly.
- Avoid when: a small script or CRUD app has no real business logic to protect — the extra layers add cost with nothing to isolate.

## Screaming Architecture

- The top-level folder structure should scream the business domain, not the framework: `billing/`, `shipping/`, `catalog/` — not `controllers/`, `services/`, `models/`.
- A newcomer reading the folder tree should learn what the system does before learning what framework it uses.
- Framework-first structure is a violation signal even if the code inside is otherwise clean.
- Pairs naturally with Clean/Hexagonal Architecture: domain folders at the top, framework wiring pushed to the edges inside each domain folder.

## Atomic Design (UI composition)

- Five layers, composing strictly upward: atoms (button, input, label) → molecules (labeled input, search bar) → organisms (header, form) → templates (page layout with placeholders) → pages (templates with real content/data).
- Violation signal: an atom imports a molecule, or a page hardcodes markup that belongs in an organism one level down.
- Avoid over-splitting: a one-off layout with no reuse potential doesn't need all five layers — collapse layers when reuse doesn't justify the ceremony.

## Container / Presentational Pattern

- Presentational (dumb) components: receive data and callbacks only via props, contain no state beyond UI-local state (e.g., an open/closed toggle), and render markup. Fully testable with plain prop fixtures.
- Container (smart) components: own state, side effects, data fetching, and business logic; render a presentational component and pass it data/callbacks.
- Violation signal: a component both calls an API/hook for data AND renders complex markup — split it.
- With hooks-based UI frameworks, the split can be a custom hook (container logic) + a pure component (presentational) instead of two component files — the separation of concerns is what matters, not the file count.

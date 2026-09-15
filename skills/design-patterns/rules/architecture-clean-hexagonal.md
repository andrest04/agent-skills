---
title: Clean Architecture / Hexagonal Architecture
category: Architecture
tags: architecture, clean-architecture, hexagonal, ports-and-adapters
source: not from refactoring.guru
---

## Clean Architecture / Hexagonal Architecture (Ports & Adapters)

- Core rule: the Dependency Rule. Source code dependencies point only inward, toward the domain/use cases. Nothing inner knows anything about anything outer.
- Layers (outer to inner): frameworks/drivers (DB, UI, web) -> interface adapters (controllers, presenters, gateways) -> application/use cases -> entities/domain.
- Ports are interfaces defined by the domain; adapters are the concrete implementations living in the outer layer (a `UserRepository` port, a `PostgresUserRepository` adapter).
- Violation signal: a domain/use-case file imports an ORM, HTTP client, or framework decorator directly.
- Avoid when: a small script or CRUD app has no real business logic to protect; the extra layers add cost with nothing to isolate.

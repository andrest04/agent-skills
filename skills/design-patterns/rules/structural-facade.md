---
title: Facade
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/facade
---

## Facade

**Intent**: Provides a simplified interface to a complex library, framework, or subsystem.

**Problem → Solution**: Business logic becomes tightly coupled to a complex subsystem's implementation details, hurting comprehension and maintenance → introduce a facade class that exposes only the features clients actually need and hides the rest.

**Avoid when**: It risks becoming a god object coupled to the whole app, and it trades away access to the subsystem's advanced capabilities for simplicity.

---
title: Mediator
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/mediator
---

## Mediator

**Intent**: Reduces chaotic, direct dependencies between a set of objects.

**Problem to Solution**: Components (e.g. form elements) become tightly coupled to each other, making them hard to reuse independently, so have components communicate indirectly through a mediator object instead of directly with each other.

**Avoid when**: Nobody is watching its growth; a mediator can evolve into a God Object over time.

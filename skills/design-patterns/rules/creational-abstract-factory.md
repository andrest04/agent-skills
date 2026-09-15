---
title: Abstract Factory
category: Creational
tags: design-patterns, gof, creational
source: https://refactoring.guru/design-patterns/abstract-factory
---

## Abstract Factory

**Intent**: Produces families of related objects without the caller ever naming their concrete classes.

**Problem → Solution**: Keeping a family of matching objects (e.g. furniture in one style) consistent gets hard without code changes each time a variant is added or updated → define an abstract interface per product type and implement one concrete factory per family that satisfies all of them.

**Avoid when**: The number of new interfaces and classes it introduces outweighs the benefit for a small or single-variant product set.

---
title: Strategy
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/strategy
---

## Strategy

**Intent**: Defines a family of interchangeable algorithms, each in its own class, swappable at runtime.

**Problem to Solution**: Several algorithm variants embedded directly in one class (e.g. a navigator app with multiple routing algorithms) bloat it and make it hard to maintain, so extract each algorithm into its own strategy class behind a common interface, letting the context delegate to and swap strategies at runtime.

**Avoid when**: There are only a couple of algorithms that rarely change; the added classes and interfaces cost more than they save, and callers must understand each strategy's differences to pick correctly.

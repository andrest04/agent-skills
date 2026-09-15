---
title: Singleton
category: Creational
tags: design-patterns, gof, creational
source: https://refactoring.guru/design-patterns/singleton
---

## Singleton

**Intent**: Restricts a class to exactly one instance while giving the whole codebase one global point to reach it.

**Problem → Solution**: A class must exist as a single, globally reachable instance → make the constructor private and expose a static accessor that creates the instance once and returns the cached one on every later call.

**Avoid when**: It's needed by default — it violates Single Responsibility, can mask poor design, needs special handling under multithreading, and its private constructor plus static access complicate unit testing.

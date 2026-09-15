---
title: Memento
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/memento
---

## Memento

**Intent**: Saves and restores an object's previous state without exposing its implementation details.

**Problem to Solution**: Snapshotting an object's state for undo functionality is hard to do without breaking encapsulation, so let the originator produce its own immutable memento, which other objects hold and pass around through a narrow interface only it can fully read.

**Avoid when**: Frequent memento creation would consume too much memory, or the runtime cannot guarantee a memento's state stays untouched.

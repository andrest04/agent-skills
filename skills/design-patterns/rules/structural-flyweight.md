---
title: Flyweight
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/flyweight
---

## Flyweight

**Intent**: Fits more objects into available memory by sharing the state that's common between them instead of duplicating it per object.

**Problem → Solution**: A system with huge numbers of similar objects (e.g. particles in a game) wastes memory because each one stores duplicate data such as color and sprite → extract the unchanging (intrinsic) data into shared flyweight objects and keep the contextual (extrinsic) data in separate container objects.

**Avoid when**: Recomputing extrinsic context would cost more CPU than the RAM it saves, or the added complexity would confuse a team unfamiliar with the split state.

---
title: Iterator
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/iterator
---

## Iterator

**Intent**: Traverses a collection's elements without exposing its underlying representation (list, stack, tree, etc.).

**Problem to Solution**: Different data structures need different traversal algorithms, and cramming all of them into the collection class blurs its primary responsibility, so move traversal logic into separate iterator objects, allowing several iterators to traverse the same collection independently.

**Avoid when**: The collection is simple enough that a dedicated iterator is overkill, or direct element access is more efficient for that structure.

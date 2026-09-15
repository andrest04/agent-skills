---
title: Bridge
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/bridge
---

## Bridge

**Intent**: Splits a class (or closely related classes) into two independently developable hierarchies — abstraction and implementation.

**Problem → Solution**: Extending a class hierarchy along more than one dimension at once (e.g. shape type and color) makes subclass combinations grow exponentially → pull one dimension into its own hierarchy and connect it to the original classes through composition instead of inheritance.

**Avoid when**: Applied to a class that is already cohesive and has no real second dimension of variation to split out.

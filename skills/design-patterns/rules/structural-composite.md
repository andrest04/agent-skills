---
title: Composite
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/composite
---

## Composite

**Intent**: Composes objects into tree structures so client code can treat single objects and whole compositions the same way.

**Problem → Solution**: Computing a value (e.g. price) across nested simple and composite elements (boxes containing products and other boxes) forces awkward handling of each type and nesting level → give every element a shared interface that recursively delegates the operation, so clients don't need to know concrete classes.

**Avoid when**: The element types differ so much functionally that forcing a unified interface would overgeneralize and hurt clarity.

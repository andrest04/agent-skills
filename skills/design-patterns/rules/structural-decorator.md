---
title: Decorator
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/decorator
---

## Decorator

**Intent**: Attaches new behavior to an object by wrapping it in objects that carry that behavior, as an alternative to subclassing.

**Problem → Solution**: Supporting many combinations of optional behavior (e.g. notification types) through inheritance produces a combinatorial explosion of subclasses → use composition and wrapping instead, layering decorators that share the wrapped object's interface.

**Avoid when**: You need to remove one specific wrapper from an existing stack, need order-independent decorator behavior, or the layered setup code would get too ugly to justify it.

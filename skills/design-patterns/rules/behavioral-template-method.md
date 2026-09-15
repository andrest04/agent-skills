---
title: Template Method
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/template-method
---

## Template Method

**Intent**: Defines an algorithm's skeleton in a superclass, letting subclasses override specific steps without changing the overall structure.

**Problem to Solution**: Multiple classes with similar processing algorithms duplicate everything except a few format-specific steps, so break the algorithm into step methods, call them from one template method, and let subclasses override only the steps that vary.

**Avoid when**: Clients need more freedom than the fixed algorithm skeleton allows, it risks violating the Liskov Substitution Principle, or the number of steps has grown enough to make it hard to maintain.

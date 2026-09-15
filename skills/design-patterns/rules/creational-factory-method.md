---
title: Factory Method
category: Creational
tags: design-patterns, gof, creational
source: https://refactoring.guru/design-patterns/factory-method
---

## Factory Method

**Intent**: Gives a superclass an interface for creating objects while letting subclasses decide which concrete type actually gets created.

**Problem → Solution**: Code tightly coupled to specific classes makes adding new product types require changes throughout the codebase → delegate instantiation to a factory method subclasses can override, so callers depend only on a common interface.

**Avoid when**: It forces extra subclasses just to vary the created type; it fits best extending an existing class hierarchy, not starting one from scratch.

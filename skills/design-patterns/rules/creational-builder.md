---
title: Builder
category: Creational
tags: design-patterns, gof, creational
source: https://refactoring.guru/design-patterns/builder
---

## Builder

**Intent**: Constructs a complex object step by step instead of through one large constructor call.

**Problem → Solution**: Objects needing extensive, multi-field initialization end up with unwieldy constructors or initialization code scattered across the codebase → extract construction into a separate builder object that assembles the product step by step, running only the steps a given configuration needs.

**Avoid when**: The object has few enough fields that the extra builder classes add more ceremony than they remove.

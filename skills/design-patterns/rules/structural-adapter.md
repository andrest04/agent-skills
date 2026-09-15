---
title: Adapter
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/adapter
---

## Adapter

**Intent**: Lets objects with incompatible interfaces collaborate by translating one into the other.

**Problem → Solution**: An application receives data in one format (e.g. XML) but must integrate a component that only accepts another (e.g. JSON) → wrap one side in an adapter object that converts its interface into a shape the other side understands.

**Avoid when**: Modifying the service class directly would be simpler — an adapter adds a new interface and class where none may be needed.

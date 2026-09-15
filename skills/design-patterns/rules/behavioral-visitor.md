---
title: Visitor
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/visitor
---

## Visitor

**Intent**: Separates algorithms from the objects they operate on, so new behavior does not require touching those objects' classes.

**Problem to Solution**: A team needs to add new functionality (e.g. XML export) to existing node classes without modifying already-working production code, so place the new behavior in visitor classes that accept elements as arguments, using double dispatch to invoke the right visitor method for each concrete element type.

**Avoid when**: New element types get added or removed often (every visitor needs updating each time), or visitors would need private access to the elements they work with.

---
title: Prototype
category: Creational
tags: design-patterns, gof, creational
source: https://refactoring.guru/design-patterns/prototype
---

## Prototype

**Intent**: Copies existing objects without coupling the copying code to their concrete classes.

**Problem → Solution**: Copying an object directly is problematic because some fields are private and inaccessible, and the copying code ends up depending on concrete types → let objects clone themselves through a common interface, so copies are made without knowing the concrete class.

**Avoid when**: The object graph has circular references — cloning gets tricky, and every participating class must correctly implement its own clone method.

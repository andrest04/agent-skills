---
title: State
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/state
---

## State

**Intent**: Lets an object change its behavior when its internal state changes, as if it changed class.

**Problem to Solution**: A state machine built from ever-growing conditional statements becomes hard to maintain as states and state-dependent behaviors multiply, so extract each state's behavior into its own class and have the context delegate to whichever state object is currently active.

**Avoid when**: The state machine has only a few states and rarely changes.

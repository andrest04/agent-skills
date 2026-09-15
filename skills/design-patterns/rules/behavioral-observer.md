---
title: Observer
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/observer
---

## Observer

**Intent**: Defines a subscription mechanism to notify multiple objects about events happening to the object they observe.

**Problem to Solution**: Interested parties either waste effort polling for a change or the source wastes resources notifying everyone regardless of interest, so add a subscribe/unsubscribe mechanism to the publisher so subscribers get notified automatically through a standard interface.

**Avoid when**: Notification order matters (subscribers fire in unspecified order), or the set of observers is fixed and known in advance rather than dynamic.

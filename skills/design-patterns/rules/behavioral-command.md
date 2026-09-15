---
title: Command
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/command
---

## Command

**Intent**: Turns a request into a standalone object that carries all information needed to execute it.

**Problem to Solution**: Multiple UI triggers needing different actions lead to excess subclasses and duplicated handler code, so extract request details into command objects behind a common interface, decoupling senders (UI) from receivers (business logic).

**Avoid when**: The extra layer between sender and receiver is not justified, or undo/redo via state backups would consume significant memory.

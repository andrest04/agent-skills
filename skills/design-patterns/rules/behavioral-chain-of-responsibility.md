---
title: Chain of Responsibility
category: Behavioral
tags: design-patterns, gof, behavioral
source: https://refactoring.guru/design-patterns/chain-of-responsibility
---

## Chain of Responsibility

**Intent**: Passes a request along a chain of handlers until one of them handles it.

**Problem to Solution**: Sequential checks (e.g. order validation) become increasingly bloated and hard to maintain as requirements are added, so turn each check into a standalone handler linked into a chain, where each handler decides to process the request or forward it to the next.

**Avoid when**: No handler in the chain guarantees it will process the request; a request can end up unhandled.

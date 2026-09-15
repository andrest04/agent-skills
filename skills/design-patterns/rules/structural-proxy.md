---
title: Proxy
category: Structural
tags: design-patterns, gof, structural
source: https://refactoring.guru/design-patterns/proxy
---

## Proxy

**Intent**: Provides a substitute for another object that implements the same interface, to control access to it.

**Problem → Solution**: A resource-intensive object isn't always needed and access to it must be controlled without changing its interface → create a proxy class implementing the same interface that intercepts requests and delegates to the real object as needed.

**Avoid when**: It introduces classes you could avoid, and the extra indirection can delay the response from the underlying service.

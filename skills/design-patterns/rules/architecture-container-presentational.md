---
title: Container / Presentational Pattern
category: Architecture
tags: architecture, container-presentational, component-design
source: not from refactoring.guru
---

## Container / Presentational Pattern

- Presentational (dumb) components: receive data and callbacks only via props, contain no state beyond UI-local state (e.g., an open/closed toggle), and render markup. Fully testable with plain prop fixtures.
- Container (smart) components: own state, side effects, data fetching, and business logic; render a presentational component and pass it data/callbacks.
- Violation signal: a component both calls an API/hook for data AND renders complex markup; split it.
- With hooks-based UI frameworks, the split can be a custom hook (container logic) plus a pure component (presentational) instead of two component files; the separation of concerns is what matters, not the file count.

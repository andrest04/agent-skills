---
title: Atomic Design
category: Architecture
tags: architecture, atomic-design, ui-composition
source: not from refactoring.guru
---

## Atomic Design (UI composition)

- Five layers, composing strictly upward: atoms (button, input, label) -> molecules (labeled input, search bar) -> organisms (header, form) -> templates (page layout with placeholders) -> pages (templates with real content/data).
- Violation signal: an atom imports a molecule, or a page hardcodes markup that belongs in an organism one level down.
- Avoid over-splitting: a one-off layout with no reuse potential does not need all five layers; collapse layers when reuse does not justify the ceremony.

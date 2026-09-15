---
title: Screaming Architecture
category: Architecture
tags: architecture, screaming-architecture, folder-structure
source: not from refactoring.guru
---

## Screaming Architecture

- The top-level folder structure should scream the business domain, not the framework: `billing/`, `shipping/`, `catalog/`, not `controllers/`, `services/`, `models/`.
- A newcomer reading the folder tree should learn what the system does before learning what framework it uses.
- Framework-first structure is a violation signal even if the code inside is otherwise clean.
- Pairs naturally with Clean/Hexagonal Architecture: domain folders at the top, framework wiring pushed to the edges inside each domain folder.

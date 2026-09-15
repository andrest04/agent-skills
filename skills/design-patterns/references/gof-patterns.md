# GoF Pattern Catalog (source: refactoring.guru)

Same 3 categories and pattern set as https://refactoring.guru/design-patterns/catalog. Each entry: intent (paraphrased from the source page), when to avoid, and the direct source URL for full structure/code examples.

## Creational Patterns

- **Factory Method** — lets a class defer instantiation to subclasses/functions so callers depend on an interface, not a concrete type. Avoid when there is only one concrete type and no foreseeable second one. https://refactoring.guru/design-patterns/factory-method
- **Abstract Factory** — produces families of related objects without specifying their concrete classes. Avoid unless you truly have multiple interchangeable families (e.g., per-platform UI kits). https://refactoring.guru/design-patterns/abstract-factory
- **Builder** — constructs complex objects step by step, letting the same construction process create different representations. Avoid for objects with few optional fields; a constructor or plain object literal is enough. https://refactoring.guru/design-patterns/builder
- **Prototype** — copies existing objects without making code dependent on their classes. Avoid where cheap constructors already exist; rarely worth it outside expensive-to-build objects. https://refactoring.guru/design-patterns/prototype
- **Singleton** — ensures a class has only one instance with a global access point. Avoid by default: it violates Single Responsibility, hides dependencies, complicates unit testing (private constructor blocks mocking), and needs extra care under multithreading. Prefer injecting a shared instance. https://refactoring.guru/design-patterns/singleton

## Structural Patterns

- **Adapter** — converts one interface into another so incompatible objects can collaborate. Use at integration boundaries with third-party/legacy code, not between your own well-designed modules. https://refactoring.guru/design-patterns/adapter
- **Bridge** — splits a large class or closely related classes into two independent hierarchies (abstraction and implementation) that can be developed separately. Use only when you truly have two independent dimensions of variation; otherwise it's needless indirection. https://refactoring.guru/design-patterns/bridge
- **Composite** — composes objects into tree structures and lets clients treat individual objects and compositions uniformly. Use for real tree structures (UI trees, file systems); avoid forcing flat lists into it. https://refactoring.guru/design-patterns/composite
- **Decorator** — attaches new behaviors to objects by placing them inside wrapper objects, as a flexible alternative to subclassing. Prefer over deep inheritance chains for combinable behaviors (middleware, stream wrappers). https://refactoring.guru/design-patterns/decorator
- **Facade** — provides a simplified interface to a complex subsystem (library, framework). Use to shrink a call site's surface area, not to hide a design that should just be simplified. https://refactoring.guru/design-patterns/facade
- **Flyweight** — fits more objects into available memory by sharing common state between them. Only relevant at real scale (thousands+ of similar objects); premature otherwise. https://refactoring.guru/design-patterns/flyweight
- **Proxy** — provides a substitute or placeholder for another object to control access to it (lazy load, cache, permission check, remote call). Avoid stacking proxies for concerns better handled by middleware/interceptors. https://refactoring.guru/design-patterns/proxy

## Behavioral Patterns

- **Chain of Responsibility** — passes a request along a chain of handlers, each deciding to process it or pass it on. Matches middleware pipelines and validation chains. https://refactoring.guru/design-patterns/chain-of-responsibility
- **Command** — turns a request into a standalone object containing all request information, enabling queuing, logging, and undoable operations. Avoid for simple direct calls with no need to queue, log, or undo them. https://refactoring.guru/design-patterns/command
- **Iterator** — lets you traverse a collection's elements without exposing its underlying representation. Usually already provided by the language/runtime; rarely hand-rolled today. https://refactoring.guru/design-patterns/iterator
- **Mediator** — reduces chaotic dependencies between objects by forcing them to collaborate only through a mediator object. Use when objects reference each other in a tangled mesh; avoid introducing one for two collaborators. https://refactoring.guru/design-patterns/mediator
- **Memento** — lets you save and restore an object's previous state without exposing its internals. Use for undo history or snapshots. https://refactoring.guru/design-patterns/memento
- **Observer** — defines a subscription mechanism to notify multiple objects about events happening to the object they observe. Matches event emitters, pub/sub, reactive streams. Avoid when a direct call is clearer and there's only one listener. https://refactoring.guru/design-patterns/observer
- **State** — lets an object alter its behavior when its internal state changes, appearing to change its class. Use for real state machines; avoid for a couple of boolean flags. https://refactoring.guru/design-patterns/state
- **Strategy** — defines a family of interchangeable algorithms, encapsulates each one, and makes them interchangeable at runtime. The default answer to "if/else on type doing different logic." https://refactoring.guru/design-patterns/strategy
- **Template Method** — defines the skeleton of an algorithm in a base class, letting subclasses override specific steps without changing its structure. Prefer composition (Strategy) over this when the language favors it. https://refactoring.guru/design-patterns/template-method
- **Visitor** — separates algorithms from the objects on which they operate, so new operations can be added without changing the objects' classes. Best when new operations are added often but new element types rarely — avoid it when the opposite is true (new types added more often), since it inverts the maintenance cost. https://refactoring.guru/design-patterns/visitor

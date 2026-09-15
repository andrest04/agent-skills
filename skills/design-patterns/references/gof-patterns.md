# GoF Pattern Catalog

Source: [refactoring.guru/design-patterns/catalog](https://refactoring.guru/design-patterns/catalog) — same 22 patterns, same 3 categories, same order. Intents below are paraphrased, not quoted, from each source page; each entry links directly to the source for full structure and code examples.

## Creational Patterns

### Factory Method
- **Intent**: Gives a superclass an interface for creating objects while letting subclasses decide which concrete type actually gets created.
- **Problem → Solution**: Code tightly coupled to specific classes makes adding new product types require changes throughout the codebase → delegate instantiation to a factory method subclasses can override, so callers depend only on a common interface.
- **Avoid when**: It forces extra subclasses just to vary the created type; it fits best extending an existing class hierarchy, not starting one from scratch.
- **Source**: https://refactoring.guru/design-patterns/factory-method

### Abstract Factory
- **Intent**: Produces families of related objects without the caller ever naming their concrete classes.
- **Problem → Solution**: Keeping a family of matching objects (e.g. furniture in one style) consistent gets hard without code changes each time a variant is added or updated → define an abstract interface per product type and implement one concrete factory per family that satisfies all of them.
- **Avoid when**: The number of new interfaces and classes it introduces outweighs the benefit for a small or single-variant product set.
- **Source**: https://refactoring.guru/design-patterns/abstract-factory

### Builder
- **Intent**: Constructs a complex object step by step instead of through one large constructor call.
- **Problem → Solution**: Objects needing extensive, multi-field initialization end up with unwieldy constructors or initialization code scattered across the codebase → extract construction into a separate builder object that assembles the product step by step, running only the steps a given configuration needs.
- **Avoid when**: The object has few enough fields that the extra builder classes add more ceremony than they remove.
- **Source**: https://refactoring.guru/design-patterns/builder

### Prototype
- **Intent**: Copies existing objects without coupling the copying code to their concrete classes.
- **Problem → Solution**: Copying an object directly is problematic because some fields are private and inaccessible, and the copying code ends up depending on concrete types → let objects clone themselves through a common interface, so copies are made without knowing the concrete class.
- **Avoid when**: The object graph has circular references — cloning gets tricky, and every participating class must correctly implement its own clone method.
- **Source**: https://refactoring.guru/design-patterns/prototype

### Singleton
- **Intent**: Restricts a class to exactly one instance while giving the whole codebase one global point to reach it.
- **Problem → Solution**: A class must exist as a single, globally reachable instance → make the constructor private and expose a static accessor that creates the instance once and returns the cached one on every later call.
- **Avoid when**: It's needed by default — it violates Single Responsibility, can mask poor design, needs special handling under multithreading, and its private constructor plus static access complicate unit testing.
- **Source**: https://refactoring.guru/design-patterns/singleton

## Structural Patterns

### Adapter
- **Intent**: Lets objects with incompatible interfaces collaborate by translating one into the other.
- **Problem → Solution**: An application receives data in one format (e.g. XML) but must integrate a component that only accepts another (e.g. JSON) → wrap one side in an adapter object that converts its interface into a shape the other side understands.
- **Avoid when**: Modifying the service class directly would be simpler — an adapter adds a new interface and class where none may be needed.
- **Source**: https://refactoring.guru/design-patterns/adapter

### Bridge
- **Intent**: Splits a class (or closely related classes) into two independently developable hierarchies — abstraction and implementation.
- **Problem → Solution**: Extending a class hierarchy along more than one dimension at once (e.g. shape type and color) makes subclass combinations grow exponentially → pull one dimension into its own hierarchy and connect it to the original classes through composition instead of inheritance.
- **Avoid when**: Applied to a class that is already cohesive and has no real second dimension of variation to split out.
- **Source**: https://refactoring.guru/design-patterns/bridge

### Composite
- **Intent**: Composes objects into tree structures so client code can treat single objects and whole compositions the same way.
- **Problem → Solution**: Computing a value (e.g. price) across nested simple and composite elements (boxes containing products and other boxes) forces awkward handling of each type and nesting level → give every element a shared interface that recursively delegates the operation, so clients don't need to know concrete classes.
- **Avoid when**: The element types differ so much functionally that forcing a unified interface would overgeneralize and hurt clarity.
- **Source**: https://refactoring.guru/design-patterns/composite

### Decorator
- **Intent**: Attaches new behavior to an object by wrapping it in objects that carry that behavior, as an alternative to subclassing.
- **Problem → Solution**: Supporting many combinations of optional behavior (e.g. notification types) through inheritance produces a combinatorial explosion of subclasses → use composition and wrapping instead, layering decorators that share the wrapped object's interface.
- **Avoid when**: You need to remove one specific wrapper from an existing stack, need order-independent decorator behavior, or the layered setup code would get too ugly to justify it.
- **Source**: https://refactoring.guru/design-patterns/decorator

### Facade
- **Intent**: Provides a simplified interface to a complex library, framework, or subsystem.
- **Problem → Solution**: Business logic becomes tightly coupled to a complex subsystem's implementation details, hurting comprehension and maintenance → introduce a facade class that exposes only the features clients actually need and hides the rest.
- **Avoid when**: It risks becoming a god object coupled to the whole app, and it trades away access to the subsystem's advanced capabilities for simplicity.
- **Source**: https://refactoring.guru/design-patterns/facade

### Flyweight
- **Intent**: Fits more objects into available memory by sharing the state that's common between them instead of duplicating it per object.
- **Problem → Solution**: A system with huge numbers of similar objects (e.g. particles in a game) wastes memory because each one stores duplicate data such as color and sprite → extract the unchanging (intrinsic) data into shared flyweight objects and keep the contextual (extrinsic) data in separate container objects.
- **Avoid when**: Recomputing extrinsic context would cost more CPU than the RAM it saves, or the added complexity would confuse a team unfamiliar with the split state.
- **Source**: https://refactoring.guru/design-patterns/flyweight

### Proxy
- **Intent**: Provides a substitute for another object that implements the same interface, to control access to it.
- **Problem → Solution**: A resource-intensive object isn't always needed and access to it must be controlled without changing its interface → create a proxy class implementing the same interface that intercepts requests and delegates to the real object as needed.
- **Avoid when**: It introduces classes you could avoid, and the extra indirection can delay the response from the underlying service.
- **Source**: https://refactoring.guru/design-patterns/proxy

## Behavioral Patterns

### Chain of Responsibility
- **Intent**: Passes a request along a chain of handlers until one of them handles it.
- **Problem → Solution**: Sequential checks (e.g. order validation) become increasingly bloated and hard to maintain as requirements are added → turn each check into a standalone handler linked into a chain, where each handler decides to process the request or forward it to the next.
- **Avoid when**: No handler in the chain guarantees it will process the request — a request can end up unhandled.
- **Source**: https://refactoring.guru/design-patterns/chain-of-responsibility

### Command
- **Intent**: Turns a request into a standalone object that carries all information needed to execute it.
- **Problem → Solution**: Multiple UI triggers needing different actions lead to excess subclasses and duplicated handler code → extract request details into command objects behind a common interface, decoupling senders (UI) from receivers (business logic).
- **Avoid when**: The extra layer between sender and receiver isn't justified, or undo/redo via state backups would consume significant memory.
- **Source**: https://refactoring.guru/design-patterns/command

### Iterator
- **Intent**: Traverses a collection's elements without exposing its underlying representation (list, stack, tree, etc.).
- **Problem → Solution**: Different data structures need different traversal algorithms, and cramming all of them into the collection class blurs its primary responsibility → move traversal logic into separate iterator objects, so several iterators can traverse the same collection independently.
- **Avoid when**: The collection is simple enough that a dedicated iterator is overkill, or direct element access is more efficient for that structure.
- **Source**: https://refactoring.guru/design-patterns/iterator

### Mediator
- **Intent**: Reduces chaotic, direct dependencies between a set of objects.
- **Problem → Solution**: Components (e.g. form elements) become tightly coupled to each other, making them hard to reuse independently → have components communicate indirectly through a mediator object instead of directly with each other.
- **Avoid when**: You're not watching its growth — a mediator can evolve into a God Object over time.
- **Source**: https://refactoring.guru/design-patterns/mediator

### Memento
- **Intent**: Saves and restores an object's previous state without exposing its implementation details.
- **Problem → Solution**: Snapshotting an object's state for undo functionality is hard to do without breaking encapsulation → let the originator produce its own immutable memento, which other objects hold and pass around through a narrow interface only it can fully read.
- **Avoid when**: Frequent memento creation would consume too much memory, or the runtime (many dynamic languages) can't guarantee a memento's state stays untouched.
- **Source**: https://refactoring.guru/design-patterns/memento

### Observer
- **Intent**: Defines a subscription mechanism to notify multiple objects about events happening to the object they observe.
- **Problem → Solution**: Interested parties either waste effort polling for a change or the source wastes resources notifying everyone regardless of interest → add a subscribe/unsubscribe mechanism to the publisher so subscribers get notified automatically through a standard interface.
- **Avoid when**: Notification order matters — subscribers fire in unspecified order — or the set of observers is fixed and known in advance rather than dynamic.
- **Source**: https://refactoring.guru/design-patterns/observer

### State
- **Intent**: Lets an object change its behavior when its internal state changes, as if it changed class.
- **Problem → Solution**: A state machine built from ever-growing conditional statements becomes hard to maintain as states and state-dependent behaviors multiply → extract each state's behavior into its own class and have the context delegate to whichever state object is currently active.
- **Avoid when**: The state machine has only a few states and rarely changes.
- **Source**: https://refactoring.guru/design-patterns/state

### Strategy
- **Intent**: Defines a family of interchangeable algorithms, each in its own class, swappable at runtime.
- **Problem → Solution**: Several algorithm variants embedded directly in one class (e.g. a navigator app with multiple routing algorithms) bloat it and make it hard to maintain → extract each algorithm into its own strategy class behind a common interface, so the context can delegate to and swap strategies at runtime.
- **Avoid when**: There are only a couple of algorithms that rarely change — the added classes and interfaces cost more than they save, and callers must understand each strategy's differences to pick correctly.
- **Source**: https://refactoring.guru/design-patterns/strategy

### Template Method
- **Intent**: Defines an algorithm's skeleton in a superclass, letting subclasses override specific steps without changing the overall structure.
- **Problem → Solution**: Multiple classes with similar processing algorithms duplicate everything except a few format-specific steps → break the algorithm into step methods, call them from one template method, and let subclasses override only the steps that vary.
- **Avoid when**: Clients need more freedom than the fixed algorithm skeleton allows, it risks violating the Liskov Substitution Principle, or the number of steps has grown enough to make it hard to maintain.
- **Source**: https://refactoring.guru/design-patterns/template-method

### Visitor
- **Intent**: Separates algorithms from the objects they operate on, so new behavior doesn't require touching those objects' classes.
- **Problem → Solution**: A team needs to add new functionality (e.g. XML export) to existing node classes without modifying already-working production code → place the new behavior in visitor classes that accept elements as arguments, using double dispatch to invoke the right visitor method for each concrete element type.
- **Avoid when**: New element types get added or removed often — every visitor needs updating each time — or visitors would need private access to the elements they work with.
- **Source**: https://refactoring.guru/design-patterns/visitor

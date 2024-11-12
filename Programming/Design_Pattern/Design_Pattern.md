# Design Pattern

## References

- https://www.youtube.com/watch?v=tv-\_1er1mWI&t=7s
- https://refactoring.guru/design-patterns/catalog

# Context

## Creational Pattern

> How objects are __CREATED__

### Singleton

- Object that can only be instantiated once
  - e.g. settings

### Prototype

- Object that can be cloned
  - e.g. class inheritance

### Builder

- Create object by filling elements step by step
  - e.g. method chaining

### Factory

- Reuse name of function or object for different purpose, and let factory decide which actual function or object to render
  - e.g. logistic can be used for both road logistic and sea logistic, but carrier for road is vehicle as carrier for sea is ship

## Structural Pattern

> How objects __RELATE__ to each other

### Facade

- Simplified API for low-level detailed complex systems
  - e.g. grouped functions to simplify operations

### Proxy

- Object to replace original object
  - e.g. update proxy object while re-rendering original object
- Pros: less duplicate in memory

## Behavioral Pattern

> How objects __COMMUNICATE__ with each other

### Iterator

- Transverse through a collection of objects
  - e.g. for-loop
- Pull-based system

### Observer

- Allow many objects to subscribe to events (One-to-Many)
  - e.g. database can be subscribed to many applications
  - e.g. YouTube subscription
- Push-based system

### Mediator

- Send events to their corresponding objects (Many-to-Many) a.k.a coordination
  - e.g. request -> middleware (Mediator) -> response for each object

### State

- Change behavior according to state changing
  - e.g. switch statement
- Pros: Same API

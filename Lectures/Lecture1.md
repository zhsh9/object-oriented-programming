# The process of software development

```
requirement                 structure
specification               chart
┌─────────┐                 ┌─────────┐
│         │                 │         │
│         │                 │         │
│         ◄─────────────────┤         │
│         │                 │         │
└────▲────┘                 └────▲────┘
     │                           │
     │                           │
     │                           │
     │                           │
     │        ┌─────────┐        │
     │        │         │        │
     │        │         │        │
     └────────┤         ├────────┘
              │         │
              └─────────┘
              source code
```

# Model

- def: the intermediate descriptions(documents) produced in the process
- features
  - abstract view of a system
  - easy to understand
  - a valuable means for communication

# Classes of methodologies

- structured methods
  - models:
    - a collection of data
    - functions external to the data
  - notations: data flow diagrams
- object-oriented methods
  - models: see exps
  - notations: UML

# UML

UML: Unified Modeling Language

- Used with a wide range of software processes
- Views
- Models/Diagrams

## Views

- use case view
- design view
- implementation view
- process view
- deployment view

## Diagrams

- present certain aspect of underlying system model
- abstract, object structure
- some types can be used in both use case and design views

## UML's diagram types

| Diagram               | View                   |
| --------------------- | ---------------------- |
| use case diagram      | use case view          |
| object diagram        | use case & design view |
| sequence diagram      | use case & design view |
| collaboration diagram | use case & design view |
| class diagram         | design view            |
| statechart diagram    | design view            |
| activity diagram      | design view            |
| component diagram     | implementation view    |
| deployment diagram    | deployment view        |
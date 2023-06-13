# Inventory

- [Inventory](#inventory)
- [The process of software development](#the-process-of-software-development)
- [Model](#model)
- [Classes of methodologies](#classes-of-methodologies)
- [UML](#uml)
  - [Views](#views)
  - [Diagrams](#diagrams)
  - [UML's diagram types](#umls-diagram-types)
- [Software development process](#software-development-process)
- [Inventory](#inventory-1)
- [Objects](#objects)
- [Class diagrams](#class-diagrams)
  - [Details](#details)
  - [Create a class diagram](#create-a-class-diagram)
- [An example of class diagram](#an-example-of-class-diagram)
- [The applicability of the object model](#the-applicability-of-the-object-model)

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

- definition
  - the intermediate descriptions(documents) produced in the process
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

# Software development process

- linear or waterfall model
```
analysis -> design -> develop -> test -> deploy
```
- iterative model
```
-> detailed analysis -> design -> develop -> test -> deploy ->
```

# Inventory

- [Inventory](#inventory)
- [The process of software development](#the-process-of-software-development)
- [Model](#model)
- [Classes of methodologies](#classes-of-methodologies)
- [UML](#uml)
  - [Views](#views)
  - [Diagrams](#diagrams)
  - [UML's diagram types](#umls-diagram-types)
- [Software development process](#software-development-process)
- [Inventory](#inventory-1)
- [Objects](#objects)
- [Class diagrams](#class-diagrams)
  - [Details](#details)
  - [Create a class diagram](#create-a-class-diagram)
- [An example of class diagram](#an-example-of-class-diagram)
- [The applicability of the object model](#the-applicability-of-the-object-model)

# Objects

- design: split up a system's data and overall functionality
- rule: real-world objects
- **properties**
  - state
  - behavior
  - identity
  - object name
- avoid data replication
  - data in the previous object model is replicated
    - waste storage
    - difficult to consistently update all objects
  - link

# Class diagrams

## Details

- object diagrams: can only show a small subset of a program's possible states
- describe the software system in a more abstract level: class diagram
  - similar to object diagram
  - types of the attributes are shown
  - association (linkage counter)
  - inheritance

## Create a class diagram

- how to draw
- operations
- associations, association generalization
- aggregation
- composite objects
- association classes

# An example of class diagram

```
                                                   ┌──────────────────┐
                                                   │                  │ *
                                                   │     Component    ├────────────────┐
                                                   │                  │                │
                                                   │                  │                │
┌──────────────────────────┐                       └─────────▲────────┘                │
│                          │                                 │                         │
│                          │                     ┌───────────┴──────────┐              │
│                          │                     │                      │              │
│      CatalogueEntry      │                     │                      │              │
│      name: string        │              ┌──────┴──────┐        ┌──────┴──────┐       │
│      number: long        │              │             │        │             │       │
│      cost: double        │              │             │        │             │       │
│                          │              │   Part      │        │   Assembly  │       │
│                          ◄──────────────┤             │        │             ├───────┘
│                          │1            *│             │        │             │0..1
│                          │              └─────────────┘        └─────────────┘
│                          │
└──────────────────────────┘
```

```c++
class CatalogueEntry {
public:
    CatalogueEntry(string p_name, long p_number, double p_cost) {...}
    string getName() {}
    long getNumber() {}
    double getCost() {}
private:
    string name;
    long number;
    double cost;
}

class Part {
public:
    Part(CatalogueEntry * e) { entry = e; }
private:
    CatalogueEntry * entry;
}

int main() {
    CatalogueEntry *screw = new CatalogueEntry("screw",28834,0.02);
    Part * screw1 = new Part(screw);
}
```

# The applicability of the object model

- object (real-world) -> object model
- message passing
  - real-world events are often treated as messages
  - objects + events -> objects + messages
- strength of OOP
  - localization of data + operations with objs
  - mapping: real-world object -> object model

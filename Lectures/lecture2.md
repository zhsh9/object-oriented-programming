# Inventory

- [Inventory](#inventory)
- [Class diagram](#class-diagram)
- [Relationship](#relationship)
- [Attributes and operations](#attributes-and-operations)
  - [Attribute of class](#attribute-of-class)
  - [Operation of class](#operation-of-class)
  - [Object identity](#object-identity)
- [Multiplicity](#multiplicity)
  - [Class multiplicity](#class-multiplicity)
- [Association](#association)
- [Generalization and specialization](#generalization-and-specialization)
- [Association generalization](#association-generalization)
- [Aggregation](#aggregation)
- [Composite objects](#composite-objects)
- [Association classes](#association-classes)

# Class diagram

Vidoe ref: [UML Class Diagram Tutorial](https://www.bilibili.com/video/BV1P741127u7)

Outline:

- how to draw
- operations
- associations, association generalization
- aggregation
- composite objects
- association classes

# Relationship

- instantiate(?)
- generalization and specialization

- inheritance
- association
- aggregation
- composition

# Attributes and operations

```
------------
|Class_Name|
------------
|Attributes|
|...       |
------------
|Operations|
|...       |
------------
```

## Attribute of class

- format
  - name
  - name: type
  - name: type = default_val
- instance scope
- class scope
- mutiplicity of attr

Other classes should not be used as the attribute types -> association.

## Operation of class

- format
  - name()
  - name(param:p_type,...): return_type
- instance scope
- class scope

## Object identity

- id: Interger

# Multiplicity

Definition: the number of times a given entity can occur in some context.

- 0..1
- n
- 0..*
- 1..*
- m..n

## Class multiplicity

Definition: the number of instances of the class that can exist.

- Default: 0..*

# Association

- association, role name, mutiplicity
- self-association

# Generalization and specialization

- super-class (ancestor)
- sub-class (descendant)
- generalization/specialization
- abstract class

# Association generalization

# Aggregation

- a kind of association: describe part/whole relationship
- properties when objs are linked to instances of their own class
  - anti-symmetry: no self-connection
  - transitivity

# Composite objects

- a strong form of association
  - part can only belong to one composite object
  - object is x, all its composite parts are x.

# Association classes

- associate data values with links
- UML notation
- applicability

An association class can have associations with other classes:

```
┌────────────┐                      ┌────────────┐
│            │                      │            │
│   Student  │                      │   Module   │
│            ├──────────┬───────────┤            │
│            │          │           │            │
│            │          │           │            │
└────────────┘          │           └────────────┘
                        │
                        │
                ┌───────┴────────┐
                │                │
                │   Registration │
                ├────────────────┤
                │ mark: Integer  │
                │                │
                └───────┬────────┘
                        │
                        │
                        │
                        │
               ┌────────┴──────────┐
               │                   │
               │     Class         │
               ├───────────────────┤
               │  semester: String │
               │                   │
               └───────────────────┘
```

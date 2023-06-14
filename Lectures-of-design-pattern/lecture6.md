# Inventory

- [Inventory](#inventory)
- [Lecture Outline](#lecture-outline)
- [The concept of design pattern](#the-concept-of-design-pattern)
- [Specific problem](#specific-problem)
- [Composite pattern](#composite-pattern)
- [Example: statement design](#example-statement-design)
- [Strategy pattern](#strategy-pattern)
- [Decorator pattern](#decorator-pattern)

# Lecture Outline

- description
- roles
- a case: design a document editor
    - compisite pattern (doc data)
    - strategy pattern (doc formatting)
    - decorator pattern (interface elements)

# The concept of design pattern

a problem + core solution

description of a pattern:

- name
- problem
- solution
- consequence
  - space and time trade-offs
  - impact on system's flexibility, extensibility, portability

roles of design pattern:

- application programs
  - reduce class dependencies
  - reduce platform dependencies
- toolkit
  - reduce code reuse
  - C++ STL
- framework

when not to use dp:

- Drawbacks of using design patterns
  - Complicate the design
  - Degrade the performance of the system, in terms of space and time requirements.
- Only use design patterns if you want:
  - Flexibility
  - Extensibility
  - portability

# Specific problem

A WYSIWYG document editor

design problesm:

- Document structure
- Formatting
- Embellishing the user interface
- Multiple look-and-feel standards
- User Operations
- Spelling checking and hyphenation

# Composite pattern

- applicability
  - part-whole
  - single and composite object
- structure
- participant
  - component
    - common interface
    - default behavior
    - access and manage its child components
    - access a component's parent

# Example: statement design

![statement](../.readme-imgs/statement.jpg)

# Strategy pattern

# Decorator pattern
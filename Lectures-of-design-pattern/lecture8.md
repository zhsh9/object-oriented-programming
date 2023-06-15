# Outline

- abstract factory pattern
  - pattern
  - implementation (singleton, make)
- iterator & visitor pattern
  - iterator
  - proxy pattern
  - pre-order traversing

# Abstract factory pattern

- motivation
  - change interface style at run-time
- first step
  - abstract widget class
  - concrete sub-class
- class diagram
  - abstract widget classes & their subclasses
  - factory classes & their products
  - make factory class extensible

# Iterator & visitor pattern

- on Lexi: spelling check and hyphenation
- for: create an iterator it for the list
- forget deleting it -> mem leakage -> proxy pattern

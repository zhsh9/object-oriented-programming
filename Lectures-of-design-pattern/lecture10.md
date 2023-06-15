# Builder pattern

- problem: convert RTF document into plain text, TeX, TextWidget formats
- example class diagram, general structure
- features
  - seperate converter from reader
  - hide details of creating and assembling a complex object
  - re-use parsing algorithm
- participants
  - builder
  - concrete builder
  - director
- sequence diagram

# Factory method pattern

- multiple document framwork (example)
  - open multiple documents
  - active document
  - windows: tile, cascade
  - close all
- class diagram

# Prototype pattern

- objects created on an existing prototype object
- editor for music scores
- implement
  - use a prototype manager
  - implement clone operation
    - shallow copy
    - deep copy

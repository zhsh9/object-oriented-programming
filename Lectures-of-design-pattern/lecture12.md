# Facade pattern

- compiler subsystem

# Chain of responsiblity

- context sensitive help
- specific help -> general help -> even general help
- example
  - specific -> general
  - help handler
  - handler

# Interpreter pattern

- for: implement operation defined in the base class
- example
  - boolean expression
- dependency analysis
  - example: expression inside a loop does not depend on local vars, it can be evaluated only once
  - effect caching
  - parallelism
  - lazy evaluation: compute nothing until it is explicitly asked for
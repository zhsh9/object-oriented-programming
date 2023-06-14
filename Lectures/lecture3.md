# Outline

- qualified associations
- multiple inheritance in UML
- mixin class
- discriminators
- implementation of class dirgam
  - uni-directional association
  - bi-directional association
  - implement qualifiers
  - implementation of association classes

# Qualified association

example: Unix file system

- each file has a unique internal indentifier
- each file can appear multiple times in different directories
- all names within a directory must be different from each other

details:

- definition: an association class which has properties which enable it to act as a key
- mapping from qualifier values to instances of the class at the other end of the association

## Qualifier and identifier

```
┌──────────────┐                     ┌────────────────┐
│              │                     │                │
│              ├─────────────┐       │    Student     │
│  University  │ id:Integer  ├───────┼────────────────┤
│              ├─────────────┘1     1│  name:String   │
│              │                     │                │
└──────────────┘                     └────────────────┘
```

# Multiple inheritance in UML

- capable
- attrs and operations of the common ancester are inherited only once

# Mixin class

- a mixin class: to provide an optional interface of functionality to other classes
- similar to an abstract classes in that it's not intended to be instantiated
- mixin classes require multiple inheritance

# Discriminator

# Implement associations

- uni-directional links
- bi-directional links
- both should be hidden from client code

# Implement association classes

- solution: transform the association class into a sample class linked to the two original classes
- interface of the two original classes (unchanged)
- constraints should be imposed


```
model -> registration(mark:Integer) -> student
```

```c++
class Registration {
    Student * pStudent;
    int mark; // the attr of the link
public:
    Registration(Student * st) {
        pStudent = st;
        mark = 0;
    }
}

class Module {
    vector<Registration*> regs;
public:
    void enrol(Student * st) {
        // interface remains.
        regs.push_back(new Registration(st));
    }
}
```
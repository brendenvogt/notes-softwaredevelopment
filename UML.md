# UML Notes
UML or the (Unified Modelling Language) is the a way to structure object data types
# Components 
- Class (Top entry of the UML Diagram)
  - the type or class of the object.
- Attributes (Middle section of the UML Diagram)
  - Definition:
    - A significant piece of data containing values that describe each instance of that class.
    - Also called fields, variables, properties.
    - Requires syntax `<visibility><name>: <type>`
  - Examples:
    - `-name: string`
    - `-id: int`
    - `-age: int`
- Methods (Bottom section of the UML Diagram)
  - Definition
    - Also called operations or functions
    - Allow you to specify any behavioral feature or a class.
    - Requires syntax `<visibility><name>()` or `<visibility><name>(<var>, <other var>)`
  - Examples:
    - `-setName()`
    - `-eat()`
# Visibility
`-` is private (only same class)
`+` is public (access by any other class)
`#` is protected (same class or its subclasses)
`~` is package/default (any other class inside the package)

# Quick examples
```
Animal
==============
-name: string
-id: int
-age: int
==============
-setName(name: string)
-eat()
```

```
Employee
==============
-name: string
-employeeId: int
-phone: string
-department: string
==============
+updatePhone(number: string)
```

# Relationships
### Inheritance
  - Definition:
    - An object can have an inherited structure such as a tortoise is an animal, and a zebra is an animal. We can create UML classes for the `Tortoise` and the `Zebra` and that both inherit from `Animal`
    - If there is an attribute or a method is needed in all subclasses then that can be changed in the superclass.
  - Syntax:
    - Solid line with white arrows (not filled in) from the child to the parent. Child is sometimes referred to as Subclass, and parent is sometimes referred to as the superclass. `A<--B`
  - Semantic:
    - `class B is a class A` or `class A is the parent of class B` or `class B is a child of class A`
  - Example:
    - `Dog is an Animal`
### Association 
  - Definition:
    - A simple relationship.
  - Syntax:
    - Single solid line. `A--B`
  - Semantic:
    - `a class A can be a part of class B`
  - Example:
    - `A Person can be a part of a Club`
### Aggregation
  - Definition:
    - In other words, representing ownership. The ownership relationship needs an owner. Without the owner, the component cannot survive.
  - Syntax:
    - Solid line with white diamond on the end of the owner. `A<>--B`
  - Semantic:
    - `class A can have a class B`
  - Example:
    - `Car can have an Engine` or `Car<>--Engine` this is because a `Car<>--ElectricMotor`
### Composition
  - Definition:
    - Represents a composite relationship. The part cannot be without the whole. 
  - Syntax:
    - Solid line with black diamond on the end of the owner. `A<X>--B`
  - Semantic:
    - `class A must have a class B`
  - Example
    - `Person must have a Head` or `Person<X>--Head`

# Multiplicity
- `0..0` - 	0	Collection must be empty
- `0..1` - 		No instances or one instance
- `1..1` - 	1	Exactly one instance
- `0..*` - 	*	Zero or more instances
- `1..*` - 		At least one instance
- `5..5` - 	5	Exactly 5 instances
- `m..n` - 		At least m but no more than n instances
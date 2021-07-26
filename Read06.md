# OOP Principles

## Inheritance

 Inheritance enables you to create new classes that reuse, extend, and modify the behavior defined in other classes.  
  The class whose members are inherited is called the base class, and the class that inherits those members is called the derived class

  ## Abstract Classes

  Classes can be declared as abstract by putting the keyword abstract before the class definition. For example:
  ``` cs
public abstract class A
{
    // Class members here.
}
  ```
  The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.

  ## Polymorphism

  - Considered third pillar of OOP.
  - greek word that means "many shaped"  
At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays.  
 When this polymorphism occurs, the object's declared type is no longer identical to its run-time type.  
Base classes may define and implement virtual methods, and derived classes can override them, which means they provide their own definition and implementation

## Basic OOP principles

### 4 Pillars
- Abstraction:  Modeling the relevant attributes and interactions of entities as classes to define an abstract representation of a system.
- Encapsulation: Hiding the internal state and functionality of an object and only allowing access through a public set of functions.
- Inheritance: Ability to create new abstractions based on existing abstractions.
- Polymorphism: Ability to implement inherited properties or methods in different ways across multiple abstractions, in other words - changing depending on the class that is calling the method or owning the prop.

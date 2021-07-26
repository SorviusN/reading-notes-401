# Interfaces

## Summary
1. An interface is like an abstract base class with only abstract members. A class or struct that implements the interface must implement all its members. 

2. An interface may define default implementations for some or all of its members. A class or struct that implements the interface doesn't have to implement members that have default implementations. 

3. An interface can't be instantiated directly. Its members are implemented by any class or struct that implements the interface.

## Back to basics

The basic problem an interface is trying to solve is to separate how we use something from how it is implemented. This is so that we can write code that can work with a variety of different implementations of some set of responsibilities without having to specifically handle each implementation.  
- Large takeaway: only use classes when needed.
- Interfaces are kind of a shortcut that allows us to get rid of gaving lots of dependencies in a class.

## Interfaces #2

- Implementation of an interface
<<<<<<< HEAD
=======

>>>>>>> 0f25559168ba6c05252db4f09e8bb46ae27c769a
``` cs
interface ISampleInterface
{
    void SampleMethod();
}

class ImplementationClass : ISampleInterface
{
    // Explicit interface member implementation:
    void ISampleInterface.SampleMethod()
    {
        // Method implementation.
    }

    static void Main()
    {
        // Declare an interface instance.
        ISampleInterface obj = new ImplementationClass();

        // Call the member.
        obj.SampleMethod();
    }
}
<<<<<<< HEAD
=======

>>>>>>> 0f25559168ba6c05252db4f09e8bb46ae27c769a
```

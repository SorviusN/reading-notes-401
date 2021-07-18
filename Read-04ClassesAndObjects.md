# Classes and Objects

## Classes
A type that is defined as a class is a reference type. 
``` cs
// Declaring object of type MyClass
MyClass mc = new MyClass();

// declaring another object of same type, assigning it value of first object.
MyClass mc2 = mc;
```
When an object is created, the appropriate amount of memory is allocated on the heap and the variable holds a reference to that said place in memory inside of the heap.  <br>
Types on the managed heap require overhead both when they are allocated and when they are reclaimed by automatic memory management (Common Language Runtime) or garbage collection.

### Declaring Classes
``` cs
public class Customer 
{
    // Fields, props  methods and events go here
}
```

### Creating Objects
### Classes and objects are different. A class defines a type of object but is not an object itself.
Objects can be created using new Keyword followed by the name of the class that the object will be based on. (think of class as a type.)
``` cs
Customer object1 = new Customer();

// You can also create a reference to another object which doesn't create a new place in memory.
Customer objectRef = object1
```

### Class inheritance
``` cs
public class Manager : Employee

// Employee fields, props, methods, events are inherited 
// New Manager fields, props and methods/ event go here.
```

## Constructors
``` cs
public class Person
{
    private string last; // Private meaning that it can only be accessed by things inside of the class.
    private string first;

    public Person(string lastName, firstName) 
    {
        last = lastName;
        first = firstName;
    }

    //remaining implementation of Person (methods, events e.t.c)
}
```

## Properties
- Proprties enable a class to expose a public manner of getting / setting values, while hiding implementation or verification code.

- Get is used to return the prop value
- Set is used to assign a value.
- Value is a keyword used to define the val being assigned by the set or init accessor. Write only properties are rare and most commonly used to restrict access to sensitive data.
``` cs
using System;

class TimePeriod
 {
     //GET: REFERENCE THE VALUE
     // SET: ALTER THE VALUE
     private double seconds;
     
     public double Hours;
     {
         get { return seconds / 3600; } // If someone wants TimePeriod.Hours, they will get back seconds / 3600.
         set 
         {
             if (value < 0 || value > 24) // make sure the hour variable is good.
             throw new ArgumentOutOfRangeException( // if not, then throw error that it is out of range.
                 $"{nameof(value)} must be between 0 and 24.");
             )

             seconds = value * 3600; // setting value of private prop seconds to the external value hours.
         }
     }
 }

 class Program
 {
    static void Main()
   {
       TimePeriod t = new TimePeriod();
       // The property assignment causes the 'set' accessor to be called.
       t.Hours = 24;

       // Retrieving the property causes the 'get' accessor to be called.
       Console.WriteLine($"Time in hours: {t.Hours}");
   }
 }
```
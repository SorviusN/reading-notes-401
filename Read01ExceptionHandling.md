# Exception Handling

### Debugging for beginners -
Two major points:
- What did you expect your code to do?
- What happened instead?
- Solve this with breakpoints and debug navigation.
- Use the Auto window @ bottom of code to view properties and detailed examination of types/objects/functions.

### Exception handling -
- Used to provide an error interface. There are many different types such as:
``` cs
throw Exception(e)
{
    exception statement
}

throw OutOfBoundsIndex(); // this will give a specific error back to the user if prompted.
```

### Therac-25/Ariane 5 -
The Therac-25 was a computer-controlled radiation therapy machine produced by Atomic Energy of Canada Limited (AECL) in 1982 after the Therac-6 and Therac-20 units (the earlier units had been produced in partnership with CGR of France). - Quoted from https://en.wikipedia.org/wiki/Therac-25


The Therac incident was quite fascincating. Software engineers failed to handle exception cases in the correct manner. They highlighted the dangers of software control for safety-critical systems (such as medical).


# Unit Testing & Documentation

## Unit Testing Best Practices
What unit testing is not:
- Unit tests don't deal with their environment and with external systms to the codebase.
- Unit tests don't count as other sorts of tests. If you create a test that throws thousands of requests for a service you've written that qualifies as a smoke test, not unit test.
- Unit tests don't exercise multiple components of your system and how they act. <br>

### These things above do have value, they just are not a unit test.

### So what is XUnit testing?
They isolate and exercise specific units of code.

Anatomy of a Unit Test 
``` cs
[TestClass]
public class CalculatorTests
{
    [TestMethod]
    public void Adding_4_And_3_Should_Return_7() {
        int calc = new Calculator();

        int res = calc.Add(4,3);

        Assert.Equals(7, res); // we assert that our result should equal 7, and pass if the test is true
    }
}
```

## Art of Readme
Etymology
- ReadMe dates back to at least 1970 and PDP-10. 
- The pattern of README appearing ina ll caps is consistent facet throughoout history. In addition to visual strikingness of all caps, UNIX systems would sort caps before lower case letters.

### The README: Your one-stop shop
A README is a module consumer's first -- and maybe only -- look into your creation. The consumer wants a module to fulfill their need, so you must explain exactly what need your module fills, and how effectively it does so. <br>
Job of the README is to:
- Tell them what the project is.
- Show them what it looks like in action
- Show them how they use it.
- Explain any other relevant details.

### The Checklist
1. One-liner explaining the purpose of the module
2. Necessary background context & links
3. Potentially unfamiliar terms link to informative sources
4. Clear, runnable example of usage
5. Installation instructions
6. Extensive API documentation
7. Performs cognitive funneling
8. Caveats and limitations mentioned up-front
9. Doesn't rely on images to relay critical information
10. License

Source: https://github.com/hackergrrl/art-of-readme
## ReadMe Best Practices

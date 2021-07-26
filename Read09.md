# LINQ

A query is an expression that retrieves data from a data source.  

All LINQ query ops consist of 3 distint actions:

1. Obtain data source

2. Create the query

3. Execute the query

``` cs
class IntroToLINQ // Sourced directly from https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries
{
    static void Main()
    {
        // The Three Parts of a LINQ Query:
        // 1. Data source.
        int[] numbers = new int[7] { 0, 1, 2, 3, 4, 5, 6 };

        // 2. Query creation.
        // numQuery is an IEnumerable<int>
        var numQuery =
            from num in numbers
            where (num % 2) == 0
            select num;

        // 3. Query execution.
        foreach (int num in numQuery)
        {
            Console.Write("{0,1} ", num);
        }
    }
}
```

## Basic LINQ Query Operators

In a LINQ query, the first step is to specify the data source.  
A var must be declared before it can be used. In a LINQ query, the 'from' clause comes first in order, followed by where and finally select.

The most common query operation is to apply a filter in the form of a Boolean expression. The filter causes the query to return only those elements for which the expression is true. The result is produced by using the where clause.  

You can use the familiar C# logical AND and OR operators to apply as many filter expressions as necessary in the where clause. For example, to return only customers from "London" AND whose name is "Devon" you would write the following code:

The orderby clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted

The group clause enables you to group your results based on a key that you specify

``` cs
//Filtering
    where cust.City == "London" && cust.Name == "Devon"

//Ordering
    var queryLondonCustomers3 =
    from cust in customers
    where cust.City == "London"
    orderby cust.Name ascending
    select cust;

// Grouping

// queryCustomersByCity is an IEnumerable<IGrouping<string, Customer>>
  var queryCustomersByCity =
      from cust in customers
      group cust by cust.City;

  // customerGroup is an IGrouping<string, Customer>
  foreach (var customerGroup in queryCustomersByCity)
  {
      Console.WriteLine(customerGroup.Key);
      foreach (Customer customer in customerGroup)
      {
          Console.WriteLine("    {0}", customer.Name);
      }
  }
```

Source - https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/basic-linq-query-operations





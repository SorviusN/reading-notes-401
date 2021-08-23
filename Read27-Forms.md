# Read 27 - Forms
## Views explained
In the Model-View-Controller (MVC) pattern, the view handles the app's data presentation and user interaction. A view is an HTML template with embedded Razor markup. Razor markup is code that interacts with HTML markup to produce a webpage that's sent to the client.

## How controllers specify views

Views are typically returned from actions as a ViewResult, which is a type of ActionResult.  
Your action method can create and return a ViewResult directly but not very common to do so.  
<br>
Since most controllers inherit from Controller, just use View helper method to return ViewResult.

### View Overloads

``` cs
// View helper method has a few overloads. You can specify:

// Explicit view to return
return View("orders");

// A model to pass the view
return View(Orders);

// both View and model
return View("Orders", Orders);
```

## Two ways to pass data to views
1. Strongly Typed: viewmodel
This is the most robust approach. Commonly referred to as viewmodel. 
You specify a model type in the view. You then pass an instance of the viewmodel type to the view from the action.

using viewmodel to pass data allows view to take advantage of strong type checking.

Example:
``` cs

//First, controller passes the view data as a parameter.
public IActionResult Contact()
{
    ViewData["Message"] = "Your contact page.";

    var viewModel = new Address()
    {
        Name = "Microsoft",
        Street = "One Microsoft Way",
        City = "Redmond",
        State = "WA",
        PostalCode = "98052-6399"
    };

    return View(viewModel);
}
```

``` html
<!-- Afterward, the data is displayed and taken directly from viewModel that is passed in via the object. -->
@model WebApplication1.ViewModels.Address

<h2>Contact</h2>
<address>
    @Model.Street<br>
    @Model.City, @Model.State @Model.PostalCode<br>
    <abbr title="Phone">P:</abbr> 425.555.0100
</address>

```

2. Weakly Typed

essentially means that you don't explicitly declare the type of data you're using. Can use the collection of weakly typed data for passing small amounts in and out of controllers/views.
The default behavior of View method is to return View() with same name as action method from which it's called (in the controller);



source: https://docs.microsoft.com/en-us/aspnet/core/mvc/views/overview?view=aspnetcore-2.2
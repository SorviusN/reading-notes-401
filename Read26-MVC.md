# Reading Notes 26 - MVC

### What is MVC?
MVC is a degisn pattern or architecture which helps in developing the web application in a most efficient way when compared with the trad ASP.Net Web app.

- In traditional ASP.NET web application approach, the user action and view (UI) are combined, i.e., the web page, say, Sample.aspx and code behind Sample.aspx.cs which has the action logic are both tightly coupled, whereas in MVC, the View only deals with UI of the page and the user actions are defined in Controller.
- In any web based application, a user initiates the requests which are nothing but actions. So, for action based requirement, ASP.NET Web Application follows the View based architecture which is not so efficient. MVC is action-based architecture. Based on the action, an appropriate View is displayed. The organization of the code inside MVC is very clean and organized.

<b>Model</b> <br>
    Represents the objects in the application. <br>
<b>View</b>  
    Has all HTML controls which define the UI of the app. In MVC, we use Razor Engine to show the view. <br>
<b>Controller</b> <br>
    Handles the reqs from the user. the "heart" of the application as everyone says. A controller is nothing but a class with a group of methods named "actions". Every action method returns a view with data from the model.

## Tag Helpers

Tag Helpers enable server-side code to participate in creating and rendering HTML elements in Razor files. Tag Helpers reduce the explicit transitions between HTML and C# in Razor views.  
source: https://docs.microsoft.com/en-us/aspnet/core/mvc/views/tag-helpers/intro?view=aspnetcore-2.1

## What do tag helpers provide?
- An HTML-friendly development experience.
- A rich IntelliSense environment for creating HTML and Razor markup.
- A way to make you more productive and able to produce more robust, reliable, and maintainable code using information only available on the server.  

``` cs
//quick example of how tag helpers would look within Views/_ViewImports.cshtml

@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, AuthoringTagHelpers

```
### source: https://docs.microsoft.com/en-us/aspnet/core/mvc/views/tag-helpers/intro?view=aspnetcore-2.1

## Bootstrap

Quickly design and customize responsive mobile-first sites with Bootstrap, the world’s most popular front-end open source toolkit, featuring Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful JavaScript plugin.  

Similar to react bootstrap - use it to create websites quickly.
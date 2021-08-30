# Reading Notes 32 - View Components

### As part of ASP.NET MVC 6, a new feature called view components has been introduced. View components are similar to child actions and partials views, allowing you to create reusable components with (or without) logic. Here's the summary from the ASP.NET documentation:
    View components include the same separation-of-concerns and testability benefits found between a controller and view. You can think of a view component as a mini-controller—it’s responsible for rendering a chunk rather than a whole response. You can use view components to solve any problem that you feel is too complex with a partial.

Like controllers, views must be public, non-tested and non-abstract classes that either:
- Derive from the ViewComponent class
- Are decorated with [ViewComponent] Attribute
- Have a name that ends with "ViewComponent" suffix

Example:
``` cs
public class Navigation : ViewComponent

```

# Rendering a View Component

``` cs
@Component.Invoke("Navigation");

// Above we're passing a magic string here. We can get more compile-time safety by replacing the hardcoded string literal with a nameof() expression that references our view component's class name - see below.

@Component.Invoke(nameof(Navigation));

// The last part of this is putting the components within the:
// _ViewImports.cshtml file

@using ViewComponents.Components

// You should now see the Navigation file appear.
```

# Summary

ASP.NET MVC 6 introduces view components, a component-oriented mixture of child actions and partial views. They can return various content, including Razor views, JSON, or plain text. View components can be rendered synchronously or asynchronously. Finally, they can integrate with the dependency injection system of ASP.NET Core through constructor injection.

Source: https://mariusschulz.com/blog/view-components-in-asp-net-core-mvc
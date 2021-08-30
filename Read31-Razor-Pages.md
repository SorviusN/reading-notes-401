# Reading Notes 31 - Razor Pages

## Razor Pages make coding page-focused scenarios easier and more productive than using only controllers and views.

### Adding Razor Pages to Startup.cs
``` cs
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Includes support for Razor Pages and controllers.
        services.AddMvc();
    }

    public void Configure(IApplicationBuilder app)
    {
        // Tells the app to use MVC framework.
        app.UseMvc();
    }
}
```

@page is the first thing that should be placed in front of cshtml pages.
``` cs
@page
@using RazorPagesIntro.Pages
@model IndexModel2

<h2>Separate page model</h2>
<p>
    @Model.Message
</p>
```

And the Index.cshtml.cs file should look something like this.
``` cs
using Microsoft.AspNetCore.Mvc.RazorPages;
using System;

namespace RazorPagesIntro.Pages
{
    public class IndexModel2 : PageModel
    {
        public string Message { get; private set; } = "PageModel in C#";

        public void OnGet()
        {
            Message += $" Server time is { DateTime.Now }";
        }
    }
}
```
### The associations of URL paths to pages are determined by the page's location in the file system. The following table shows a Razor Page path and the matching URL:

    /Pages/Index.cshmtl = / or /Index  
    /Pages/Contact.cshtml = /Contact  
    /Store/Index.cshtml = /Store or /Store/Index  




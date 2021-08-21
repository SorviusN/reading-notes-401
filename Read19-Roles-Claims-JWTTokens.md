# Reading Notes 19 - Roles, Claims and JWT Tokens

## Claims-based Authorization
When an identity is created it may be assigned one or more claims issued by a trusted party. A claim is a name value pair that represents what the subject is, not what the subject can do.  

For example, 
You may have a driver's license, issued by a local driving license authority. Your driver's license has your date of birth on it. In this case the claim name would be DateOfBirth, the claim value would be your date of birth, for example 8th June 1970 and the issuer would be the driving license authority. The door security officer would evaluate the value of your date of birth claim and whether they trust the issuer (the driving license authority) before granting you access. Think of claims as "properties" that a role has.

## Claims based authorization, at its simplest, checks the value of a claim and allows access to a resource based upon that claim value.

## An identity can contain multiple claims with multiple values and can contain multiple claims of the same type.

### Adding claims checks -
    Claim based auth checks are declarative - the dev embeds them within their code, against a controller or an action within a controller, specifiying claims which the current user must possess (optionally the val the claim must hold to access the requested resource).  
    The first step to this is building and registering the policy (within ConfigureServices)
``` cs
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddAuthorization(options =>
    {
        // Whenever this policy exists, a claim must be present within a role or exist within a user identity to be able to access the route.
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}

[Authorize(Policy = "EmployeeOnly")]
public IActionResult VacationBalance()
{
    return View();
}
```
In this case the EmployeeOnly policy checks for the presence of an EmployeeNumber claim on the current identity.
You then apply the policy using the Policy property on the AuthorizeAttribute attribute to specify the policy name;

source: https://docs.microsoft.com/en-us/aspnet/core/security/authorization/claims?view=aspnetcore-2.1
# JWT Auth
JSON Web Token is a means of representing claims to be transferred between two parties. The claims in a JWT are encoded as JSON object that is digitally signed using JSON web signature.  
## Simpler term: Just another way of encoding JSON object and use that object to access tokens for authentication from the server.

source: https://codeburst.io/jwt-to-authenticate-servers-apis-c6e179aa8c4e


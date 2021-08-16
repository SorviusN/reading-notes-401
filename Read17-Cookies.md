# Reading Notes 17 - Authentication, Authorization, Cookies

### HTTP Cookies

HTTP Cookie is a small piece of data that a server sends to user's web browser.
The browser may store it and send it back with later reqs to the same server.
- Typically used to tell if two reqs came from the same browser, which then keeps a user logged in for example.
- Essentially remembers stateful info for the stateless HTTP protocol.

Used for three purposes:

Session management

    Logins, shopping carts, game scores, or anything else the server should remember
Personalization

    User preferences, themes, and other settings
Tracking

    Recording and analyzing user behavior

Origin of cookies

    One of the biggest issues in the early days of the web was how to manage state. In short, the server had no way of knowing if two requests came from the same browser. The easiest approach, at the time, was to insert some token into the page when it was requested and get that token passed back with the next request. This required either using a form with a hidden field containing the token or to pass the token as part of the URL’s query string. Both solutions were intensely manual operations and prone to errors

What is a cookie?

    Quite simply, a cookie is a small text file that is stored by a browser on the user’s machine. Cookies are plain text; they contain no executable code. A web page or server instructs a browser to store this information and then send it back with each subsequent request based on a set of rules. Web servers can then use this information to identify individual users. Most sites requiring a login will typically set a cookie once your credentials have been verified, and you are then free to navigate to all parts of the site so long as that cookie is present and validated. Once again, the cookie just contains data and isn’t harmful in and of itself.

Creating Cookies:
After receiving an HTTP request, a server can send one or more Set-Cookie headers with the response. The cookie is usually stored by the browser, and then the cookie is sent with requests made to the same server inside a Cookie HTTP header. An expiration date or duration can be specified, after which the cookie is no longer sent. Additional restrictions to a specific domain and path can be set, limiting where the cookie is sent. For details about the header attributes mentioned below, refer to the Set-Cookie reference article.

``` cs
Set-Cookie: <cookie-name>=<cookie-value>
// Below shows the server sending headers to tell the client to store a pair of cookies
HTTP/2.0 200 OK
Content-Type: text/html
Set-Cookie: yummy_cookie=choco
Set-Cookie: tasty_cookie=strawberry

[page content]

```

Sources: 
- https://humanwhocodes.com/blog/2009/05/05/http-cookies-explained/
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
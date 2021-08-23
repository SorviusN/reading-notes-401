# Reading Notes 28 - Auth/Cookies
IMPORTANT ARTICLE: https://asp.mvc-tutorial.com/httpcontext/cookies/

## What are cookies?
A small piece of data that a server sends to user's web browser.  

Generally used to tell if two reqs came from the same browser (keeping user logged in, for example).

### Three purposes
- Session Management (Logins, shopping carts)
- Personalization
- Tracking

### Creating Cookies
After receiving an HTTP request, a server can send one or more Set-Cookie headers with the response. The cookie is usually stored by the browser, and then the cookie is sent with requests made to the same server inside a Cookie HTTP header.

The Set-Cookie HTTP response header sends cookies from the server to user agent. Looks something like this. Remember that this is passed in the header from server to client.
``` cs
Set-Cookie: <cookie-name>=<cookie-value>

// Also:
Set-Cookie: <em>value</em>[; expires=<em>date</em>][; domain=<em>domain</em>][; path=<em>path</em>][; secure]

// Shows something like this

//HTTP/2.0 200 OK
//Content-Type: text/html
//Set-Cookie: yummy_cookie=choco
//Set-Cookie: tasty_cookie=strawberry

[page content]
```

## Brief Origin
One of the biggest issues in the early days of the web was how to manage state. In short, the server had no way of knowing if two requests came from the same browser. The easiest approach, at the time, was to insert some token into the page when it was requested and get that token passed back with the next request. This required either using a form with a hidden field containing the token or to pass the token as part of the URL’s query string. Both solutions were intensely manual operations and prone to errors.

Lou Montulli, an employee of Netscape Communications at the time, is credited with applying the concept of “magic cookies” to web communication in 1994. The problem he was attempting to solve was that of the web’s first shopping cart, now a mainstay on all shopping sites. His original specification provides basic information about how cookies work, which was formalized in RFC 2109 (the reference for most browser implementations) and eventually evolved into RFC 2965. Montulli would also be granted a United States patent for cookies. Netscape Navigator supported cookies since its first version, and cookies are now supported by all web browsers.

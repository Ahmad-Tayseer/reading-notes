
***Read: Class 02 - Express-Routing-Middlewares***
***
***

**Classes**

***
*Definition:*

    Classes are a template for creating objects. They encapsulate data with code to work on that data. Classes in JS are built on prototypes but also have some syntax and semantics that are not shared with ES5 class-like semantics.

*The class syntax has two components:*

    Class declarations:
    
    It is a one way to define a class. To declare a class, use the class keyword with the name of the class.

![](./Class-02%20images/Screenshot_34.png)
    
    Class expressions:

    It is another way to define a class. Class expressions can be named or unnamed. The name given to a named class expression is local to the class's body. However, it can be accessed via the name property.

![](./Class-02%20images/Screenshot_35.png)

***

**Express Routing**

***
*Definition:*

    Routing refers to how an application’s endpoints (URIs) respond to client requests. For an introduction to routing.

*Route methods:*

    - A route method is derived from one of the HTTP methods, and is attached to an instance of the express class. 
    
    - There are four routing methods: get, post, put, delete.

    - There is a special routing method, app.all(), used to load middleware functions at a path for all HTTP request methods.

*Some examples of routing methods:*

![](./Class-02%20images/Screenshot_36.png)

![](./Class-02%20images/Screenshot_37.png)

***

**Route paths**

***

    - Route paths, in combination with a request method, define the endpoints at which requests can be made. Route paths can be strings, string patterns, or regular expressions.

    - The characters ?, +, *, and () are subsets of their regular expression counterparts. The hyphen (-) and the dot (.) are interpreted literally by string-based paths.

*Here are some examples of route paths based on strings:*

* This route path will match requests to the root route, /.

        app.get('/', (req, res) => {
        res.send('root')
        })

* This route path will match requests to /about.

        app.get('/about', (req, res) => {
        res.send('about')
        })

* This route path will match requests to /random.text.

        app.get('/random.text', (req, res) => {
        res.send('random.text')
        })

***

*Here are some examples of route paths based on string patterns:*

* This route path will match acd and abcd.

        app.get('/ab?cd', (req, res) => {
        res.send('ab?cd')
        })

* This route path will match abcd, abbcd, abbbcd, and so on.

        app.get('/ab+cd', (req, res) => {
        res.send('ab+cd')
        })

* This route path will match abcd, abxcd, abRANDOMcd, ab123cd, and so on.

        app.get('/ab*cd', (req, res) => {
        res.send('ab*cd')
        })

* This route path will match /abe and /abcde.

        app.get('/ab(cd)?e', (req, res) => {
        res.send('ab(cd)?e')
        })

***

*Examples of route paths based on regular expressions:*

* This route path will match anything with an “a” in it.

        app.get(/a/, (req, res) => {
        res.send('/a/')
        })

* This route path will match butterfly and dragonfly, but not butterflyman, dragonflyman, and so on.

        app.get(/.*fly$/, (req, res) => {
        res.send('/.*fly$/')
        })

***

**Response methods**

    The methods on the response object (res) in the following table can send a response to the client, and terminate the request-response cycle. If none of these methods are called from a route handler, the client request will be left hanging.

![](./Class-02%20images/Screenshot_38.png)

***

[README](README.md)
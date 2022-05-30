
***Read: Class 01 - TDD: Express and Node.js***
***
***

**Node (Node.js)**

***
*Definition:*

    It is an open-source, cross-platform runtime environment that allows developers to create all kinds of server-side tools and applications in JavaScript.

*Benefits:*

    - Great performance! Node was designed to optimize throughput and scalability in web applications and is a good solution for many common web-development problems.

    - Code is written in "plain old JavaScript", which means that less time is spent dealing with "context shift" between languages when you're writing both client-side and server-side code.

    - The node package manager (NPM) provides access to hundreds of thousands of reusable packages.

    - Node.js is portable. It is available on Microsoft Windows, macOS, Linux, Solaris, FreeBSD, OpenBSD, WebOS, and NonStop OS.

    - It is well-supported by many web hosting providers, that often provide specific infrastructure and documentation for hosting Node sites.

    - It has a very active third party ecosystem and developer community, with lots of people who are willing to help.
***

**Express**

***
*Definition:*

    It is the most popular Node web framework, and is the underlying library for a number of other popular Node web frameworks.

*It provides mechanisms to:*

    - Write handlers for requests with different HTTP verbs at different URL paths (routes).

    - Integrate with "view" rendering engines in order to generate responses by inserting data into templates.

    - Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response.

    - Add additional request processing "middleware" at any point within the request handling pipeline.

*Most Important Methods:*

    - POST.                        - PUT.
    - DELETE.                      - GET.
***

**NPM** 

***
*Definition:*

    It is the most popular Node web framework, and is the underlying library for a number of other popular Node web frameworks.

*Consists of three distinct components:*

    - The website.
    - The Command Line Interface (CLI).
    - The registry.

*Used to:*

    - Adapt packages of code for your apps, or incorporate packages as they are.

    - Download standalone tools you can use right away.

    - Run packages without downloading using npx.

    - Share code with any npm user, anywhere.

    - Restrict code to specific developers.

    - Create organizations to coordinate package maintenance, coding, and developers.

    - Form virtual teams by using organizations.

    - Manage multiple versions of code and code dependencies.

    - Update applications easily when underlying code is updated.

    - Discover multiple ways to solve the same puzzle.

    - Find other developers who are working on similar problems and projects.

***

**TDD**

***
*Definition:*

    “Test-driven development” refers to a style of programming in which three activities are tightly interwoven:

    **[Coding -- Testing -- Design]**

*Expected Benefits:*

    - Many teams report significant reductions in defect rates, at the cost of a moderate increase in initial development effort.

    - The same teams tend to report that these overheads are more than offset by a reduction in effort in projects’ final phases.

    - Although empirical research has so far failed to confirm this, veteran practitioners report that TDD leads to improved design qualities in the code, and more generally a higher degree of “internal” or technical quality, for instance improving the metrics of cohesion and coupling.
***

**CI/CD**

*Definition:*

    CI "Continuous Integration": is a workflow strategythat helps ensure everyone's changes will integrate with the current version of the project. This lets you catch bugs, reduce merge conflicts, and have confidence your software is working.
    ***
    CD "Continuous Delivery": is the practice of developing software in such a way that you could release it at any time. When coupled with CI, continuous delivery lets you develop features with modular code in more manageable increments.

[README](README.md)
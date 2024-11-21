
Pipes operate on the **arguments** to be processed by the route handler,
 just before the handler is called.

Pipes ca perform **Data transformation** or  **data validation.**

Pipes can return data - either original or modified - which will be passed on to the route handler.

Pipes can throw exceptions. Exceptions thrown will be handled by `NestJS` and parsed into an error response.

 Pipes can asynchronous.


# Default Pipes in NestJS

## `ValidationPipe`

## `ParseIntPipe`


# Custom Pipe Implementation


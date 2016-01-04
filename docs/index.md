---
layout: default
---

Introduction
============

Suave is a lightweight, non-blocking web server. The non-blocking I/O model is efficient and suitable for building fast, scalable network applications. In fact, Suave is written in a **completely non-blocking** fashion throughout. Suave **runs on Linux**, OS X and Windows flawlessly.

Suave is inspired in the simplicity of Happstack and born out of the necessity
of embedding web server capabilities in my own applications. Still in its early
stages Suave supports HTTPS, multiple TCP/IP bindings, Basic Access
Authentication, Keep-Alive and HTTP compression.

NuGet
-----

To install Suave, add the following to your
[paket](https://github.com/fsprojects/Paket).dependencies:

```dosbatch
source https://nuget.org/api/v2
nuget Suave
```

Or you can use the legacy NuGet command line [Package Manager
Console](http://docs.nuget.org/docs/start-here/using-the-package-manager-console):

```dosbatch
PM> Install-Package Suave
```

The simplest possible application: Hello World!
-----------------------------------------------

The simplest Suave application is a simple HTTP server that greets all visitors
with the string `"Hello World!"`

```fsharp
open Suave

startWebServer defaultConfig (Successful.OK "Hello World!")
```

The above statement will start a web server on default port 8083 over HTTP.
`startWebServer` takes a configuration record and the WebPart `(OK "Hello
World")` It's worth noting that with the above, your application will block on
the function call, until you cancel the `Async.DefaultCancellationToken`. If you
want to handle disposal of the async yourself, have a look at
`startWebServerAsync`.

In suave, we have opted to write a lot of documentation inside the code; so just
hover the function in your IDE or use an assembly browser to bring out the XML
docs. You can also browse [our API reference](/Suave.html).

# JAX-RS and REST



To know in detail about the theory of JAX-RS and how to design REST services there is an excellant tutorial available:
[javabrains-jax-rs](https://javabrains.io/courses/javaee_jaxrs)

**The examples in my tutorials use JAX-RS on Websphere (Apache Wink 2.0) but the general jax api and concepts remain the same.**



### REST: Introduction

**Representational state transfer** (REST) is a software architectural style consisting of a coordinated set of architectural constraints applied to components, connectors, and data elements, within a distributed hypermedia system.
It is a way to create, read, update or delete information on a server using simple HTTP calls.

Web service APIs that adhere to the REST constraints are called **RESTful**.
RESTful APIs are defined with these aspects:



- base URI, such as http://example.com/resources/
- an Internet media type for the data. This is often JSON but can be any other valid Internet media type (e.g. XML, Atom, microformats, images, etc.)
- standard HTTP methods (e.g., GET, PUT, POST, or DELETE)
- hypertext links to reference state
- hypertext links to reference related resources



RESTful webservice in the world of java is JAX-RS. JAX-RS is a specification.

There are a number of implementations available.



- Apache CXF, an open source Web service framework.
- Jersey, the reference implementation from Sun (now Oracle).
- RESTeasy, JBoss's implementation.
- Restlet, created by Jerome Louvel, a pioneer in REST frameworks
- Apache Wink, Apache Software Foundation Incubator project, the server module implements JAX-RS.
- WebSphere Application Server from IBM:
  Version 7.0: via the "Feature Pack for Communications Enabled Applications"
  Version 8.0 onwards: natively
- WebLogic Application Server from Oracle
- Apache Tuscany (http://tuscany.apache.org/documentation-2x/sca-java-bindingrest.html)
- Cuubez framework (http://www.cuubez.com)



JAX-RS works as a client-server model.
It is stateless as it's based on HTTP.
And cacheable too.
REST follows HATEOAS principle.
HATEOAS stands for Hypertext As The Engine Of Application State. It means that hypertext should be used to find your way through the API. - See more at: [RestCookBook](http://restcookbook.com/Basics/hateoas/#sthash.ouM1nheT.dpuf)

**Difference between Servlets and REST?**
REST is really an architectural pattern used when designing an API on a server. HttpServlets can be a method of implementing a RESTful web service in java.
REST describes a style where HTTP verbs like GET/POST/DELETE/etc. are used in a predictable way to interact with resources on a server.

**Websphere application server implementation**

The IBM implementation of JAX-RS is an extension of the base Apache Wink 1.1 runtime environment. IBM JAX-RS includes the following features:



- JAX-RS 1.1 server runtime
- Stand-alone client API with the option to use Apache HttpClient 4.0 as the underlying client
- Built-in entity provider support for JSON4J
- An Atom JAXB model in addition to Apache Abdera support
- Multipart content support
- A handler system to integrate user handlers into the processing of requests and responses



Note that there is no JAX-RS defined client API. Each implementation rolls out their own client API.
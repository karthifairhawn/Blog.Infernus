B.  SCA Concepts

B.1 Binding

**_Bindings_** are used by services and references.  References use bindings to describe the access mechanism used to call the service to which they are wired.  Services use bindings to describe the access mechanism(s) that clients use to call the service.

SCA supports multiple different types of bindings.  Examples include **_SCA service, Web service, stateless session EJB, database stored procedure, EIS service._** SCA provides an extensibility mechanism by which an SCA runtime can add support for additional binding types.

B.2 Component

**_SCA components_** are configured instances of **_SCA implementations_**, which provide and consume services. SCA allows many different implementation technologies such as Java, BPEL, C++. SCA defines an **_extensibility mechanism_** that allows you to introduce new implementation types. The current specification does not mandate the implementation technologies to be supported by an SCA runtime, vendors can choose to support the ones that are important for them. A single SCA implementation can be used by multiple Components, each with a different configuration.

The Component has a reference to an implementation of which it is an instance, a set of property values, and a set of service reference values.  Property values define the values of the properties of the component as defined by the component’s implementation. Reference values define the services that resolve the references of the component as defined by its implementation. These values can either be a particular service of a particular component, or a reference of the containing composite.

B.3 Service

**_SCA services_** are used to declare the externally accessible services of an **_implementation_**. For a composite, a service is typically provided by a service of a component within the composite, or by a reference defined by the composite. The latter case allows the republication of a service with a new address and/or new bindings. The service can be thought of as a point at which messages from external clients enter a composite or implementation.

A service represents an addressable set of operations of an implementation that are designed to be exposed for use by other implementations or exposed publicly for use elsewhere (e.g. public Web services for use by other organizations).  The operations provided by a service are specified by an Interface, as are the operations needed by the service client (if there is one).   An implementation can contain multiple services, when it is possible to address the services of the implementation separately.

A service can be provided **_as SCA remote services, as Web services, as stateless session EJB’s, as EIS services, and so on_**. Services use **_bindings_** to describe the way in which they are published. SCA provides an **_extensibility mechanism_** that makes it possible to introduce new binding types for new types of services.

B.3.1 Remotable Service

A Remotable Service is a service that is designed to be published remotely in a loosely-coupled SOA architecture. For example, SCA services of SCA implementations can define implementations of industry-standard web services. Remotable services use pass-by-value semantics for parameters and returned results.

Interfaces can be identified as remotable through the <interface /> XML, but are typically specified as remotable using a component implementation technology specific mechanism, such as Java annotations.  See the relevant SCA Implementation Specification for more information. As an example, to define a Remotable Service, a Component implemented in Java would have a Java Interface with the @Remotable annotation

B.3.2 Local Service

Local services are services that are designed to be only used “locally” by other implementations that are deployed concurrently in a tightly-coupled architecture within the same operating system process.

Local services can rely on by-reference calling conventions, or can assume a very fine-grained interaction style that is incompatible with remote distribution. They can also use technology-specific data-types.

How a Service is identified as local is dependant on the Component implementation technology used. See the relevant SCA Implementation Specification for more information. As an example, to define a Local Service, a Component implemented in Java would define a Java Interface that does not have the @Remotable annotation.

B.4 Reference

**_SCA references_** represent a dependency that an implementation has on a service that is provided by some other implementation, where the service to be used is specified through configuration. In other words, a reference is a service that an implementation can call during the execution of its business function. References are typed by an interface.

For composites, composite references can be accessed by components within the composite like any service provided by a component within the composite. Composite references can be used as the targets of wires from component references when configuring Components.

A composite reference can be used to access a service such as: an SCA service provided by another SCA composite, a Web service, a stateless session EJB, a database stored procedure or an EIS service**_,_** and so on. References use **_bindings_** to describe the access method used to their services. SCA provides an **_extensibility mechanism_** that allows the introduction of new binding types to references.

B.5 Implementation

An implementation is concept that is used to describe a piece of software technology such as a Java class, BPEL process, XSLT transform, or C++ class that is used to implement one or more services in a service-oriented application. An SCA composite is also an implementation. 

Implementations define points of variability including properties that can be set and settable references to other services. The points of variability are configured by a component that uses the implementation.  The specification refers to the configurable aspects of an implementation as its **_componentType_**.

B.6 Interface

Interfaces define one or more business functions.  These business functions are provided by Services and are used by components through References.  Services are defined by the Interface they implement.  SCA currently supports a number of interface type systems, for example:

- Java interfaces
- WSDL portTypes
- C, C++ header files

SCA also provides an extensibility mechanism by which an SCA runtime can add support for additional interface type systems.

Interfaces can be **_bi-directional_**.  A bi-directional service has service operations which are provided by each end of a service communication – this could be the case where a particular service demands a “callback” interface on the client, which it calls during the process of handing service requests from the client.

B.7 Composite

An SCA composite is the basic unit of composition within an SCA Domain. An **_SCA Composite_** is an assembly of Components, Services, References, and the Wires that interconnect them. Composites can be used to contribute elements to an **_SCA Domain_**.

A **_composite_** has the following characteristics:

- It can be used as a component implementation.  When used in this way, it defines a boundary for Component visibility. Components cannot be directly referenced from outside of the composite in which they are declared.   
- It can be used to define a unit of deployment. Composites are used to contribute business logic artifacts to an SCA Domain.

B.8 Composite inclusion

One composite can be used to provide part of the definition of another composite, through the process of inclusion.  This is intended to make team development of large composites easier.    Included composites are merged together into the using composite at deployment time to form a single logical composite.

Composites are included into other composites through <include…/> elements in the using composite.  The SCA Domain uses composites in a similar way, through the deployment of composite files to a specific location.

B.9 Property

**_Properties_** allow for the configuration of an implementation with externally set data values. The data value is provided through a Component, possibly sourced from the property of a containing composite.

Each Property is defined by the implementation.  Properties can be defined directly through the implementation language or through annotations of implementations, where the implementation language permits, or through a componentType file.  A Property can be either a simple data type or a complex data type.  For complex data types, XML schema is the preferred technology for defining the data types. 

B.10  Domain

An SCA Domain represents a set of Services providing an area of Business functionality that is controlled by a single organization.  As an example, for the accounts department in a business, the SCA Domain might cover all finance-related functions, and it might contain a series of composites dealing with specific areas of accounting, with one for Customer accounts, another dealing with Accounts Payable.

A Domain specifies the instantiation, configuration and connection of a set of components, provided via one or more composite files. A Domain also contains Wires that connect together the Components. A Domain does not contain promoted Services or promoted References, since promotion has no meaning at the Domain level.

B.11 Wire

**_SCA wires_** connect **_service references_** to **_services_**.

Valid wire sources are component references. Valid wire targets are component services.

When using included composites, the sources and targets of the wires don’t have to be declared in the same composite as the composite that contains the wire. The sources and targets can be defined by other included composites.  Targets can also be external to the SCA Domain.
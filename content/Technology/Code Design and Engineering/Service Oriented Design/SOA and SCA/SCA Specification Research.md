https://docs.oasis-open.org/opencsa/sca-assembly/sca-assembly-1.1-spec-cd03.html#_Toc225073572

SCA
- https://en.wikipedia.org/wiki/Service_Component_Architecture
- https://www.oasis-opencsa.org/sca
- https://docs.jboss.org/savara/methodology/1.0-M1/index.htm

Service Component Architecture (SCA) provides a programming model for building applications and solutions based on a Service Oriented Architecture.

![[Pasted image 20240508102316.png]]
![[Pasted image 20240508102242.png]]
# 1. Component Type
- **_Component type_** represents the configurable aspects of an implementation. 
- A component type consists of 
	- services that are offered
	- references to other services that can be wired
	- properties that can be set. 
- `The settable properties and the settable references to services are configured by a component that uses the implementation`
## 1.1 Service
- **_A Service_** represents an addressable interface of the implementation. The service is represented by a **_service element_** which is a child of the componentType element. There can be **_zero or more_** service elements in a componentType.
## 1.2 Reference
- A **_Reference_** represents a requirement that the implementation has on a service provided by another component. The reference is represented by a **_reference element_** which is a child of the componentType element. There can be **_zero or more_** reference elements in a component type definition.
## 1.3 Property
- **_Properties_** allow for the configuration of an implementation with externally set values. Each Property is defined as a property element.  The componentType element can have **_zero or more property elements_** as its children
## 1.4 Implementation
- **_Implementation_** represents characteristics inherent to the implementation itself, in particular intents and policies.  See the [Policy Framework specification [10]](http://docs.oasis-open.org/opencsa/sca-assembly/sca-assembly-1.1-spec-cd03.html#Ref10) for a description of intents and policies. The following snippet shows the component type pseudo-schema with the pseudo-schema for a implementation child element

# 2. Component
![[Pasted image 20240508103304.png]]
![[Pasted image 20240508103357.png]]
- **_Components_** are the basic elements of business function in an SCA assembly, which are combined into complete business solutions by SCA composites.
- **_Components_** are configured **_instances_** of **_implementations._** Components provide and consume services. More than one component can use and configure the same implementation, where each component configures the implementation differently.
## 2.1 Implementation
- A component element has **_zero or one implementation element_** as its child, which points to the implementation used by the component.  A component with no implementation element is not runnable, but components of this kind can be useful during a "top-down" development process as a means of defining the necessary characteristics of the implementation before the implementation is written.
- At runtime, an **_implementation instance_** is a specific runtime instantiation of the implementation – its runtime form depends on the implementation technology used.  The implementation instance derives its business logic from the implementation on which it is based, but the values for its properties and references are derived from the component which configures the implementation.
![[Pasted image 20240508102546.png]]
*Relationship of Component and Implementation*

## 2.2 Service
- The component element can have **_zero or more service elements_** as children which are used to configure the services of the component. The services that can be configured are defined by the implementation.

## 2.3 Reference
- The component element can have **_zero or more reference elements_** as children which are used to configure the references of the component. The references that can be configured are defined by the implementation.
# 3. Composite
- An SCA composite is used to assemble SCA elements in logical groupings. It is the basic unit of composition within an SCA Domain. An **_SCA composite_** contains a set of components, services, references and the wires that interconnect them, plus a set of properties which can be used to configure components.
- Components contain configured implementations which hold the business logic of the composite.
- Composite services is actually provided by one of the components within the composite.
## 3.1 Service
- The **_services of a composite_** are defined by promoting services defined by components contained in the composite. A component service is promoted by means of a composite **_service element_**.
- A composite service is represented by a **_service element_** which is a child of the composite element. There can be **_zero or more_** service elements in a composite.
- ![[Pasted image 20240508105013.png]]

## 3.2 Reference
- The **_references of a composite_** are defined by **_promoting_** references defined by components contained in the composite. Each promoted reference indicates that the component reference needs to be resolved by services outside the composite. A component reference is promoted using a composite **_reference element_**.
- A composite reference is represented by a **_reference element_** which is a child of a composite element. There can be **_zero or more_** _reference_ elements in a composite
## 3.3 Property
- **_Properties_** allow for the configuration of an implementation with externally set data values. A composite can declare zero or more properties.  Each property has a type, which is either simple or complex.  An implementation can also define a default value for a property. Properties can be configured with values in the components that use the implementation.

## 3.3 Wiring
- **_SCA wires_** within a composite connect **_source component references_** to **_target component services_**.
![[Pasted image 20240508105532.png]]

# 4. Inferface
# 5. Binding

# References
- https://simplicable.com/IT/services-vs-components
- https://docs.oasis-open.org/opencsa/sca-assembly/sca-assembly-1.1-spec-cd03.html#_Toc225073572
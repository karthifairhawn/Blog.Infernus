
## What is a entity ?
- An entity is something that exists as itself. It does not need to be of material existence. `source - wiki`
- So in our marketing plus bundle we can call Brand, Project, Roles, Budget etc,. as entity.
- Every entities has its own set of attributes and behaviours.
- So Entities definitions is same as Class definition ?
	- May be yes, But the term entitiy so not specific to Programming or Software Development.
	- But if we do relate Class-Object and Entity, yes those are same.
- There is another terminology like `Entity Class` to confuse us, this is very specific to software devlopment particularly which comes under ORM. Enitity Class is java POJO class where its attributes represents DB table row structure. `Thats what we call Object Relational Mapping (ORM).`  

## What is a service ?

- In simple terms, we can say a java class as service class when it serves functionalities of a enitity to the consumers.
	- What I mean by functionality is business use case operation.
	- What I mean by Consumer is those who use that business use case.
- In most cases services are dedicatedly created for a single entity. Sometimes for multiple entities when those entities are in strong association relationship.
- So Service are same as Util classes in our code base ?
	- In our code base we do name all services as utils so yes. `(ex: ProjectUtil)`
	- But the term `Util` has a complete diffirent meaning compare to `service`, Where service holds business logic whereas the utils are not that intelligent, `Utils` just  do some low level operations which helps services to do its job. Which help the Busniness Logic to always be completely seperated in Service Layer.
	- Other than terminology issue, We can say Our `ProjectsUtil.java` is a service.

## What is a View? 

- A view is request 

## What is a Controller ?

## What is a Dispatcher ?

## What is a Contract ?

Contract is one of mechanism to achieve loosely coupled communication b/w two services.

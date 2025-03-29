#Arch 

	Good architecture allows you to defer decisions to later.
	A good architect maximizes the number of decisions not made.


## Popular code separations
1. N-Layered Architecture
2. Domain Driven Design
3. Hexagonal ( Ports and Adapters )
4. Onion Arch.
5. Clean Arch.
6. BCE
7. DCI


**Framerworks**
- Never implement on a class from framework, which make our code couple with the framework.
- Create a interface and use it like a plugin instead.
- DI is need to abstracted to entry level layer, we might need to avoid explicit DI of framerworks in our business layer.
- 
**MVC** 
- Is a delivery pattern.
- The business application doesn't know anything about the MVC

**Cross Cutting Concerns**
- Treating CCC 
	- Infrastructure.
	- Domain
	- Decorators` (Wrappers)`

**ORM**
[Can i use ORM ?](https://stackoverflow.com/questions/194147/are-there-good-reasons-not-to-use-an-orm)

**Use Case Layer** `(Business layer) (Interactor)`  
- Are application specific business rules.
- Which on instansiation accepts a gateway `(of its boundary type)` to work. 
	- Boundaries`(interfaces)` are defined by(for) use case layer..
	- The gateway`(impl of boundary)` is expected to implement by(for) the data layer.
	- Which makes swap of data layer easy, thus achieves loose coupling.
- 
- Where do we put these second, lower level business rules? In the Entity object. The Interactor tells the Entity what to do.

**Boundaries**
- Boundaries are interfaces.
- Being defined by Business layers.

**Entities**
- Application independent business rules.
- There may be many entities involve in a particular use case`(user event)`

**DAO - Repositories (Adapters)**
- It lies on the outer most layer.
- Which acts as a plugin to the use case layer.


1. Web is an IO channel, and there is no need for our soruce architecture to show as for WEB. 
2. Service layer is need to be use case driven.
3. 
4. 


References 

1. [Evolution of arch](https://medium.com/@iamprovidence/backend-side-architecture-evolution-n-layered-ddd-hexagon-onion-clean-architecture-643d72444ce4)
2. [Clean Arch By Martin YT](https://www.youtube.com/watch?v=Nsjsiz2A9mg) 
3. [Clean Arch By Martin - Blog](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
4. [Clean Arch Impl in Java](https://medium.com/@rajeshvelmani/mastering-clean-architecture-in-java-creating-robust-and-maintainable-software-3e524ab79c9c)
5. [Clean Arch about databases](https://softwareengineering.stackexchange.com/questions/445104/where-to-place-a-common-database-connection-in-clean-architecture)
6. [Entity(Domain) can be shared across layers ?](https://medium.com/@gushakov/clean-architecture-domain-entities-and-interface-adapters-4152b9ee22d2)
7. [BCE](https://vaclavkosar.com/software/Boundary-Control-Entity-Architecture-The-Pattern-to-Structure-Your-Classes)
8. [Pack by features, not layers](https://hackernoon.com/package-by-features-not-layers-2d076df1964d)
9. [Cross Cutting Concerns](https://www.linkedin.com/advice/3/how-do-you-handle-cross-cutting-concerns-security#:~:text=Cross%2Dcutting%20concerns%20are%20aspects,%2C%20complexity%2C%20and%20maintenance%20issues.)
![[Screenshot_20231211_124156.png]]
### Rules of thumb
- [Abstract Factory](https://sourcemaking.com/design_patterns/abstract_factory "Provides a way to encapsulate a group of individual factories that have a common theme.")  
    Creates an instance of several families of classes
- [Builder](https://sourcemaking.com/design_patterns/builder "Separate the construction of a complex object from its representation so that the same construction process can create different representations.")  
    Separates object construction from its representation
- [Factory Method](https://sourcemaking.com/design_patterns/factory_method "Defines a separate method for creating the objects, which subclasses can then override to specify the derived type of product that will be created.")  
    Creates an instance of several derived classes
- [Object Pool](https://sourcemaking.com/design_patterns/object_pool "Avoid expensive acquisition and release of resources by recycling objects that are no longer in use")  
    Avoid expensive acquisition and release of resources by recycling objects that are no longer in use
- [Prototype](https://sourcemaking.com/design_patterns/prototype "Being cloned to produce new objects.")  
    A fully initialized instance to be copied or cloned
- [Singleton](https://sourcemaking.com/design_patterns/singleton "Restricts instantiation of a class to one object.")  
    A class of which only a single instance can exist
![[Screenshot_20231211_124218.png]][Adapter](https://medium.com/@akshatsharma0610/adapter-design-pattern-in-java-fa20d6df25b8) [example](https://pastebin.com/A9yUGH6w)
Bridge Design Pattern [example](https://pastebin.com/JK2r8wRi)
Fly Weight Pattern [example](https://pastebin.com/q4g8syF9)
Fascade [example](https://sourcemaking.com/design_patterns/facade/java/1)

![[Screenshot_20231211_174259.png]]

## Solid Principles
![[Pasted image 20240117123555.png | 500]]
Found this page interesting on SOLID: [open](https://okso.app/showcase/solid)

**Factory Vs DI**
1. https://www.reddit.com/r/javahelp/comments/15mcudc/is_dependency_injection_and_factory_pattern_the/
2. Clean Code: Page 188
Fundametal OO concepts  - https://github.com/herrera-ignacio/oopnotes?tab=readme-ov-file#fundamentals---composition

## Why not worry inheritance in the beginning !

As inheritance is central in the object-oriented method, so is a good inheritance structure -- more accurately, a good modular structure, including both inheritance and client relations -- essential to the quality of a design. But inheritance is only relevant as a relation among well-understood abstractions. When you are still looking for the abstractions, it is too early to devise the inheritance hierarchy.
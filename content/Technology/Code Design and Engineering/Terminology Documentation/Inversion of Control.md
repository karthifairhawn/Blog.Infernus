Inversion of Control is a key part of what makes a framework different to a library.
- A library is a set of functions that you can call,  Each call does some work and returns control to the client.
- A framework embodies some abstract design, with more behavior built in. In order to use it you need to insert your behavior into various places in the framework either by subclassing or by plugging in your own classes. The framework's code then calls your code at these points.

Ref :
https://martinfowler.com/bliki/InversionOfControl.html
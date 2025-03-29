## What is a DTO ?
- A Data Transfer Object is an object that is used to encapsulate data, and send it from one layer/system to another.
- It reduces the amount of data that needs to be sent across the layer.
- When we prefer not to send Domain objects to the consuming service we choose DTO with selected data to filter out unnecassary data to prevent it from being shared.

[Martin Fowler POV on DTO](https://martinfowler.com/bliki/LocalDTO.html)
- DTOs are called Data Transfer Objects because their whole purpose is to shift data in expensive remote calls
- Some people argue for them as part of a [Service Layer](https://martinfowler.com/eaaCatalog/serviceLayer.html) API because they ensure that service layer clients aren't dependent upon an underlying [Domain Model](https://martinfowler.com/eaaCatalog/domainModel.html). While that may be handy, I don't think it's worth the cost of all of that data mapping. As my contributor Randy Stafford says in [P of EAA](https://martinfowler.com/books/eaa.html) `Don't underestimate the cost of [using DTOs].... It's significant, and it's painful`
- 
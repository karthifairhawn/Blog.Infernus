## Sample Request Flow
	**Controllers -> Services -> DAO -> Mickey -> DB**

1. **Controllers** 
	1. Recieve incoming request from dispatcher 
	2. Converts the request data to POJO's
	3. Api specific authorisation
	4. Invoking service layer api's and return data to the dispatcher which dispatches to network
2. **Services**
	1. Services are actuall business logic of the event
	2. Services do communicate with bean implementations to retrieve data from DB and does some manipulation in it and returns to the Controllers.
3. **Data Access Object**
	1. DAO's are implementation of Beans 
	2. Bean implementation are DAO's which service layer expect to do db operations.
	3. DAO's are most sensitive area where it doesn't do any authorisation on the invoke.
	4. DAO's methods are completely event driven where the events are performed on DB without any second verification.
4. **Beans**
	1. Beans are registered with its transaction level in configuration.
	2. The ownership of bean is of service layer,
		1. Service layer gets the instance of the bean from factory.
		2. The factory is expected to provide the instance using the configuration done.
		3. So the service layer donnow the implementation`(dao)` of bean, which ensures that always implementing the bean solves the requirement and thus loose coupling is maintained across the Service <-> DAO layer.
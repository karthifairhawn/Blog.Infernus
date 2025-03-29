By leveraging the concept of composition, we can build specialised layers of services. Each layer can abstract a specific aspect of our solution.

The three layers of abstraction
- Application Service Layer
- Business Service Layer
- Orchestration Service Layer

![[Pasted image 20240812120206.png]]
## 💎 Application Service
Their purpose is to provide reusable functions related to processing data within new or legacy application environments.

**Key Points**
- To abstract legacy environment.
- Solution-agnostic.
- Generic and re-usable
- Highest degree of autonomy

Typical examples of application services are called as Utility Application service and Wrapper services.

Application services are composed by business services, but also can exist as hybrid services that contain both business and application logic.
## 💎 Business Service 
When application logic is abstracted into a separate application service layer, It is more than likely that business services will act as controllers to compose available application service to execute business logic with business rules in it.

One of main intention of business service layer is to represent business logic in purest form possible.

📍When a separate business service layer is exists, there is a strong motivation to turn all application services into generic utility.

📍When  separate business service layer not exist, application services may be required to implement service models more associated with the business service and will be called as business service or hybrid application service. `It was intentionally not following proper abstraction, as the requirement may be minimal`

In Business Service, it leads to two further models.
- Task Centric Business Service
- Entity Centric Business Service

_Task Centric Business Service_
- A service that encapsulates business logic specific to task or business requirement.
- It has limited reuse potential.

_Entity Centric Business Service_
- This service are useful for creating highly reusable and business process-agnostic services 
- That are composed by an orchestration layer or by a service layer consisting of task-centric business services (or both).

## 💎 Orchestration Service Layer
The orchestration service layer introduces a parent level of abstraction that alleviates the need for other services to manage interaction details within our workflow logic.

📍**What is Orchestration ?** abstracts business rules and service execution sequence logic from other services, promoting agility and re-usability.

📍**Why ?** One of the driving requirements behind the creation of these solutions was to accommodate the merging of large business processes

📍Orchestration can significantly reduce the complexity of solution environments.


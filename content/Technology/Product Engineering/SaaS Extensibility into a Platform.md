Making our SaaS product to the need of every customer is neither simple nor inexpensive. This is where extensibility comes in. It serves us and our consumers by enabling extensibility & connectivity with other applications natively into our application

## Extensibility 
It is an ability of a SaaS application to support extension and customisation of features for consumer specific requirements.

When a SaaS supports extensibility which solves all the business requirements for the consumers means, Then it is more than a SaaS which we call it as platform.

	SaaS application are Ui-driven, where we put our maximum effor to provide the best user experience. Whereas a plarform app open this up and provides customization and extensibility over the user experience.

**How we do extensibility ?**
Extensibility can be provided with number of feature which consumers use to solve their process. We can call the features that opens up extensibility as **extenders**. 

## Extenders (Or Building Blocks)
Extenders are features provided by SaaS which makes the Application into a Platform. Extenders are considered as a non-core feature of SaaS and we  keep it separated from our core solution and features thus ensuring our SaaS solution doesn't overlap with platform features.

**Extenders** 
- ***API and Webhooks***
- Triggers
- Workflows (Business Process Automation) 
- Functions
- SDK's (Software Development Kits)
- Marketplace - Plugins and Extensions
- Customisable User Interfaces

## API's and Web hooks
This is fundamental extender for a platform, as this serves as a building block for almost every other extenders. API's makes the customers to integrate our application into any other third party which simply can make API calls for any operation. Similarly, we can provide Web-Hooks that customer can configure for any application behaviour.

## Triggers 
Triggers are occurred when certain rule met which are configured by the user for specific event happens in the application. This trigger are configured to do a follow up task which are very specific to the consumer.

A trigger can be any state change in the application or a action explicitly done on the application/data by user or the system.

Technically triggers are categorised into two 
- Server Side Triggers - noticeable by our server environment
- Client Side Triggers - only noticeable in our client environment 

Actions
Whenever a configured rule met it makes the trigger get on and then it executes the ***Action*** which is configured for that trigger. A action is vast term, I mean a action can be anything, even customer can create their own action through custom functions. Workflows, Functions are also considered to be an action.

## Business Process Automation - Workflows
Workflows are sequence of process being executed with predefined conditions when a trigger was made. So workflows are considered to be an action which is need to be configured for a trigger.

A action in workflow can be a custom function, API call, Mail, In-app notification etc,. 

## Functions
Functions are custom code written in a programming language by the user which runs in a sand-boxed environment with data given by the *caller*.

A caller is one which initiates the function. usually a trigger, workflow, or the explicit user with a state.

Function will be written in programming language so user can do any type of operation in it like  calculation, API calls, etc,.

## SDK
Software Development Kits are things that we give to the developers, Who are users, partners, developers owned by the customers and our in-house extensibility development team. 

SDK's makes the communication with with our SaaS app more easy with language specific extender abstraction. For example: We give a Java SDK as jar for customers which takes care of all api communication and authorisation which the devlopers need.

 So the user can natively work on their own programming environment without worrying much about the api formats, parsing, authorisation etc,.

## Marketplace and Plugins
Now the community zone. The workflows, custom functions, plugins developed by the community can be shared with others too, This is must be a challanging part as it involves more of security and complaince to cop-up with. 

The plugins are built with one or many extenders that we provided. 

For example: A plugin or extension uses funtions, api's, workflows to completely built up a plugin to solve a use-case.

## Customisable User Interfaces
SaaS are majorly driven by UI and User Experience, But when it comes to extensibility part we also have to open up this area to the consumer, So they can customise the views the way they want. 

Other extenders are straight forward, But this one is an idea where we need to find the right set of extender for our SaaS domain. Also this comes with a complex engineering effort on the client side.

For example, When into comes to CRM as SaaS user need an option to customise the way the see cards of a lead, So one consumer can prioritise the mail add whereas the other can do for phone numbers.

Another example is, When creating a lead one consume needs a single form based form, Where another may have it as step of 4 (lazy process) which needs a custom wizard based form for lead generation.


 1. there are two types of classes available in Magento 2. 
 	- Injectible 
 	- Non-injectible.


// SERVICE CONTRACT

datainterface
	- holds data types by function
service cantract
	- define datainterface
	- hides business logic from the requestor

Service interfaces
Service interfaces include several interface subtypes:
	- Repository interfaces
	- Management interfaces
	- Metadata interfaces

// DI
	- allows an object A to declare its dependencies to an external object B that supplies those dependencies.

	abstraction Layer
	low level
	high level

	// High-level modules should not depend on low-level modules. Both should depend on abstractions.
	// Abstractions should not depend on details. Details should depend on abstractions.
	High Level Classes --> Abstraction Layer --> Low Level Classes

	class Manager --> Interface IWorker --> 	

// OBJECT MANAGER
	Responsibilities
	The object manager has the following responsibilities:

	- Object creation in factories and proxies
	- Implementing the singleton pattern by returning the same shared instance of a class when requested
	- Dependency management by instantiating the preferred class when a constructor requests its interface
	- Automatically instantiating parameters in class constructors


// PROXY
	Factory Class vs. Proxy Class in magento2
	https://magento.stackexchange.com/questions/104522/factory-class-vs-proxy-class-in-magento2	

// generated code 
	When is code generated?
	- The Magento application generates code to create non-existent classes. 
	- not generated on production mode
	- code is generated when the Magento application cannot find a class when executing code.	

	factory, plugin, interceptor


	// interceptor
	https://magento.stackexchange.com/questions/123920/magento-2-what-are-the-interceptors-file-in-var-generation

// Attributes
	2 types of aatributes
		- Custom 
		- Entity-Attribute-Value

		// extension attributes appear on admin?
			- it do not appear on admin







			
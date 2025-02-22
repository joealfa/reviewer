## SOLID Principles
These principles provide a way for developers to organize their code and create software that is flexible, easy to change, and testable. Applying SOLID principles can lead to code that is more modular, maintainable, and extensible, and it can make it easier for developers to work collaboratively on a codebase.

- **Single Responsibility Principle (SRP)** states that a class should have only one reason to change, or in other words, it should have only one responsibility. This means that a class should have only one job to do, and it should do it well.
- **Open-Closed Principle (OCP)** states that software entities (classes, modules, functions, and so on) should be open for extension but closed for modification. This means that the behavior of a software entity can be extended without modifying its source code.
- **Liskov Substitution Principle (LSP)** states that any instance of a derived class should be substitutable for an instance of its base class without affecting the correctness of the program. In other words, a derived class should behave like its base class in all contexts. In more simple terms, if class A is a subtype of class B, you should be able to replace B with A without breaking the behavior of your program. The importance of the LSP lies in its ability to ensure that the behavior of a program remains consistent and predictable when substituting objects of different classes. Violating the LSP can lead to unexpected behavior, bugs, and maintainability issues.
- **Interface Segregation Principle (ISP)** focuses on designing interfaces that are specific to their client's needs. It states that no client should be forced to depend on methods it does not use. The principle suggests that instead of creating a large interface that covers all the possible methods, it's better to create smaller, more focused interfaces for specific use cases. This approach results in interfaces that are more cohesive and less coupled.
- **Dependency Inversion Principle (DIP)** states that high-level modules should not depend on low-level modules, but both should depend on abstractions. Abstractions should not depend on details – details should depend on abstractions. This principle aims to reduce coupling between modules, increase modularity, and make the code easier to maintain, test, and extend.

## Design Patterns
Reusable solutions for typical software design challenges are known as design patterns. Expert object-oriented software engineers use these best practices to write more structured, manageable, and scalable code. Design patterns provide a standard terminology and are specific to particular scenarios and problems. Design patterns are not finished code but templates or blueprints only.

**Creational Design Patterns** focus on the process of object creation or problems related to object creation. They help in making a system independent of how its objects are created, composed and represented.
  - Factory Method Design Pattern
    - This pattern is typically helpful when it's necessary to separate the construction of an object from its implementation.
    - With the use of this design pattern, objects can be produced without having to define the exact class of object to be created.
  - Abstract Factory Method Design Pattern
    - Abstract Factory pattern is almost similar to Factory Pattern and is considered as another layer of abstraction over factory pattern.
    - Abstract Factory patterns work around a super-factory which creates other factories. 
  - Singleton Method Design Pattern
    - Of all, the Singleton Design pattern is the most straightforward to understand. 
    - It guarantees that a class has just one instance and offers a way to access it globally. 
  - Prototype Method Design Pattern
    - Prototype allows us to hide the complexity of making new instances from the client.
    - The concept is to copy an existing object rather than creating a new instance from scratch, something that may include costly operations. 
  - Builder Method Design Pattern
    - To "Separate the construction of a complex object from its representation so that the same construction process can create different representations." Builder pattern is used
    - It helps in constructing a complex object step by step and the final step will return the object.

**Structural Design Patterns** solves problems related to how classes and objects are composed/assembled to form larger structures which are efficient and flexible in nature. Structural class patterns use inheritance to compose interfaces or implementations.
  - Adapter Method Design Pattern
    - The adapter pattern convert the interface of a class into another interface clients expect.
    - Adapter lets classes work together that couldn’t otherwise because of incompatible interfaces. 
  - Bridge Method Design Pattern
    - The bridge pattern allows the Abstraction and the Implementation to be developed independently.
    - The client code can access only the Abstraction part without being concerned about the Implementation part.
  - Composite Method Design Pattern
    - As a partitioning design pattern, the composite pattern characterizes a collection of items that are handled the same way as a single instance of the same type of object.
    - The intent of a composite is to “compose” objects into tree structures to represent part-whole hierarchies.
  - Decorator Method Design Pattern
    - It allows us to dynamically add functionality and behavior to an object without affecting the behavior of other existing objects within the same class.
    - We use inheritance to extend the behavior of the class. This takes place at compile-time, and all the instances of that class get the extended behavior. 
  - Facade Method Design Pattern
    - Facade Method Design Pattern provides a unified interface to a set of interfaces in a subsystem.
    - Facade defines a high-level interface that makes the subsystem easier to use.
  - Flyweight Method Design Pattern
    - This pattern provides ways to decrease object count thus improving application required objects structure.
    - Flyweight pattern is used when we need to create a large number of similar objects. 
  - Proxy Method Design Pattern
    - Proxy means ‘in place of’, representing’ or ‘in place of’ or ‘on behalf of’ are literal meanings of proxy and that directly explains Proxy Design Pattern.
    - Proxies are also called surrogates, handles, and wrappers. They are closely related in structure, but not purpose, to Adapters and Decorators.

**Behavioral Patterns** are concerned with algorithms and the assignment of responsibilities between objects. Behavioral patterns describe not just patterns of objects or classes but also the patterns of communication between them. These patterns characterize complex control flow that’s difficult to follow at run-time.

#### Benefits of Design Patterns
- **Reusability:** Patterns can be applied to different projects and problems, saving time and effort in solving similar issues.
- **Standardization:** They provide a shared language and understanding among developers, helping in communication and collaboration.
- **Efficiency:** By using these popular patterns, developers can avoid finding the solution to same recurring problems, which leads to faster development.
- **Flexibility:** Patterns are abstract solutions/templates that can be adapted to fit various scenarios and requirements.

## Dependency Injection
Dependency injection is a programming technique in which an object or function receives other objects or functions that it requires, as opposed to creating them internally. Dependency injection aims to separate the concerns of constructing objects and using them, leading to loosely coupled programs. The pattern ensures that an object or function that wants to use a given service should not have to know how to construct those services. Instead, the receiving "client" (object or function) is provided with its dependencies by external code (an "injector"), which it is not aware of. Dependency injection makes implicit dependencies explicit and helps solve the following problems:

- How can a class be independent from the creation of the objects it depends on?
- How can an application, and the objects it uses support different configurations?
	
## REST
Representational State Transfer (REST) is a software architecture that imposes conditions on how an API should work. REST was initially created as a guideline to manage communication on a complex network like the internet. You can use REST-based architecture to support high-performing and reliable communication at scale. You can easily implement and modify it, bringing visibility and cross-platform portability to any API system.

## API
An application programming interface (API) defines the rules that you must follow to communicate with other software systems. Developers expose or create APIs so that other applications can communicate with their applications programmatically. For example, the timesheet application exposes an API that asks for an employee's full name and a range of dates. When it receives this information, it internally processes the employee's timesheet and returns the number of hours worked in that date range.
	
You can think of a web API as a gateway between clients and resources on the web.

## RESTful API
RESTful API is an interface that two computer systems use to exchange information securely over the internet. Most business applications have to communicate with other internal and third-party applications to perform various tasks. For example, to generate monthly payslips, your internal accounts system has to share data with your customer's banking system to automate invoicing and communicate with an internal timesheet application. RESTful APIs support this information exchange because they follow secure, reliable, and efficient software communication standards.

## CRUD
CRUD is an acronym from the world of computer programming and refers to the four functions considered necessary to implement a persistent storage application: create, read, update and delete.

## OOP
Object-Oriented Programming is defined as a programming paradigm (and not a specific language) built on the concept of objects, i.e., a set of data contained in fields, and code, indicating procedures – instead of the usual logic-based system. This article explains the fundamental concepts of OOP and its most significant advantages. 

The four pillars of Object-Oriented Programming (OOPS) are:
- Abstraction
- Encapsulation
- Inheritance
- Polymorphism

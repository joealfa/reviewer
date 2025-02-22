## SOLID Principles
These principles provide a way for developers to organize their code and create software that is flexible, easy to change, and testable. Applying SOLID principles can lead to code that is more modular, maintainable, and extensible, and it can make it easier for developers to work collaboratively on a codebase.

- **Single Responsibility Principle (SRP)** states that a class should have only one reason to change, or in other words, it should have only one responsibility. This means that a class should have only one job to do, and it should do it well.
- **Open-Closed Principle (OCP)** states that software entities (classes, modules, functions, and so on) should be open for extension but closed for modification. This means that the behavior of a software entity can be extended without modifying its source code.
- **Liskov Substitution Principle (LSP)** states that any instance of a derived class should be substitutable for an instance of its base class without affecting the correctness of the program. In other words, a derived class should behave like its base class in all contexts. In more simple terms, if class A is a subtype of class B, you should be able to replace B with A without breaking the behavior of your program. The importance of the LSP lies in its ability to ensure that the behavior of a program remains consistent and predictable when substituting objects of different classes. Violating the LSP can lead to unexpected behavior, bugs, and maintainability issues.
- **Interface Segregation Principle (ISP)** focuses on designing interfaces that are specific to their client's needs. It states that no client should be forced to depend on methods it does not use. The principle suggests that instead of creating a large interface that covers all the possible methods, it's better to create smaller, more focused interfaces for specific use cases. This approach results in interfaces that are more cohesive and less coupled.
- **Dependency Inversion Principle (DIP)** states that high-level modules should not depend on low-level modules, but both should depend on abstractions. Abstractions should not depend on details – details should depend on abstractions. This principle aims to reduce coupling between modules, increase modularity, and make the code easier to maintain, test, and extend.

## Design Patterns
Reusable solutions for typical software design challenges are known as design patterns. Expert object-oriented software engineers use these best practices to write more structured, manageable, and scalable code. Design patterns provide a standard terminology and are specific to particular scenarios and problems. Design patterns are not finished code but templates or blueprints only.

**1. Creational Design Patterns** focus on the process of object creation or problems related to object creation. They help in making a system independent of how its objects are created, composed and represented.
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

**2. Structural Design Patterns** solves problems related to how classes and objects are composed/assembled to form larger structures which are efficient and flexible in nature. Structural class patterns use inheritance to compose interfaces or implementations.
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

**3. Behavioral Patterns** are concerned with algorithms and the assignment of responsibilities between objects. Behavioral patterns describe not just patterns of objects or classes but also the patterns of communication between them. These patterns characterize complex control flow that’s difficult to follow at run-time.
  - Chain of Responsibility – Passes requests along a chain of handlers until one of them handles it.
  - Command – Encapsulates a request as an object, allowing parameterization and queuing of requests.
  - Interpreter – Defines a grammar and interprets sentences in that language.
  - Iterator – Provides a way to traverse a collection without exposing its underlying structure.
  - Mediator – Defines a central object that manages communication between objects, reducing dependencies.
  - Memento – Captures an object's state so it can be restored later.
  - Observer – Defines a dependency where objects (observers) get notified when another object (subject) changes.
  - State – Allows an object to change its behavior when its internal state changes.
  - Strategy – Encapsulates different algorithms and makes them interchangeable.
  - Template Method – Defines the skeleton of an algorithm in a base class, allowing subclasses to override specific steps.
  - Visitor – Lets you add new operations to existing object structures without modifying them

#### Benefits of Design Patterns
- **Reusability:** Patterns can be applied to different projects and problems, saving time and effort in solving similar issues.
- **Standardization:** They provide a shared language and understanding among developers, helping in communication and collaboration.
- **Efficiency:** By using these popular patterns, developers can avoid finding the solution to same recurring problems, which leads to faster development.
- **Flexibility:** Patterns are abstract solutions/templates that can be adapted to fit various scenarios and requirements.

## Dependency Injection
Dependency injection is a programming technique in which an object or function receives other objects or functions that it requires, as opposed to creating them internally. Dependency injection aims to separate the concerns of constructing objects and using them, leading to loosely coupled programs. The pattern ensures that an object or function that wants to use a given service should not have to know how to construct those services. Instead, the receiving "client" (object or function) is provided with its dependencies by external code (an "injector"), which it is not aware of. Dependency injection makes implicit dependencies explicit and helps solve the following problems:

- How can a class be independent from the creation of the objects it depends on?
- How can an application, and the objects it uses support different configurations?

## HTTP verbs
HTTP verbs (also known as HTTP methods) define the actions that can be performed on a resource in a RESTful API. Here are the most commonly used HTTP verbs:

**1. GET**
  - Retrieves data from a specified resource.
  - **Idempotent** (multiple requests have the same effect).
  - **Example:**  
    ```http
    GET /users/123
    ```
**2. POST**  
  - Creates a new resource.
  - **Not idempotent** (multiple requests may create multiple resources).
  - **Example:**  
    ```http
    POST /users
    ```
**3. PUT**  
  - Updates or replaces a resource completely.
  - **Idempotent** (same request produces the same result).
  - **Example:**  
    ```http
    PUT /users/123
    ```
**4. PATCH**  
  - Partially updates a resource.
  - **Not necessarily idempotent**.
  - **Example:**  
    ```http
    PATCH /users/123
    ```
**5. DELETE**  
  - Removes a resource.
  - **Idempotent** (repeated requests have the same result).
  - **Example:**  
    ```http
    DELETE /users/123
    ```
**6. HEAD**  
  - Similar to GET but only returns headers, not the body.
  - Used to check if a resource exists.
  - **Example:**  
    ```http
    HEAD /users/123
    ```
**7. OPTIONS**  
  - Returns supported HTTP methods for a resource.
  - **Example:**  
    ```http
    OPTIONS /users
    ```
**8. TRACE**  
  - Used for debugging, returns what was received.
  - **Example:**  
    ```http
    TRACE /users
    ```
**9. CONNECT**  
  - Establishes a tunnel (e.g., for HTTPS).
  - **Example:**  
    ```http
    CONNECT www.example.com:443
    ```

## REST
Representational State Transfer (REST) is a software architecture that imposes conditions on how an API should work. REST was initially created as a guideline to manage communication on a complex network like the internet. You can use REST-based architecture to support high-performing and reliable communication at scale. You can easily implement and modify it, bringing visibility and cross-platform portability to any API system.

## RESTful API
RESTful API is an interface that two computer systems use to exchange information securely over the internet. Most business applications have to communicate with other internal and third-party applications to perform various tasks. For example, to generate monthly payslips, your internal accounts system has to share data with your customer's banking system to automate invoicing and communicate with an internal timesheet application. RESTful APIs support this information exchange because they follow secure, reliable, and efficient software communication standards.

## API
An application programming interface (API) defines the rules that you must follow to communicate with other software systems. Developers expose or create APIs so that other applications can communicate with their applications programmatically. For example, the timesheet application exposes an API that asks for an employee's full name and a range of dates. When it receives this information, it internally processes the employee's timesheet and returns the number of hours worked in that date range.
	
You can think of a web API as a gateway between clients and resources on the web.

## CRUD
CRUD stands for Create, Read, Update, Delete - the four basic operations of persistent storage.

## CQRS
CQRS (Command Query Responsibility Segregation) is a pattern that separates read and write operations into different models.

## CORS
CORS (Cross-Origin Resource Sharing) is a mechanism that allows restricted resources on a web page to be requested from another domain.

## DTO and POCO
- **DTO (Data Transfer Object)**: An object that carries data between processes.
- **POCO (Plain Old CLR Object)**: Simple objects created in .NET without any special attributes or behavior.

## Microservices
Microservices architecture involves designing an application as a collection of loosely coupled services, each implementing a specific business capability.

## OOP
Object-Oriented Programming is defined as a programming paradigm (and not a specific language) built on the concept of objects, i.e., a set of data contained in fields, and code, indicating procedures – instead of the usual logic-based system. This article explains the fundamental concepts of OOP and its most significant advantages. 

The four pillars of Object-Oriented Programming (OOPS) are:
1. **Encapsulation**:
  - Encapsulation is the mechanism of restricting access to some of the object's components and protecting the object's internal state from unauthorized access and modification. This is typically achieved using access modifiers like private, protected, and public.
    - Example:
      ```java
      public class Person {
          private String name;
          private int age;

          public String getName() {
              return name;
          }

          public void setName(String name) {
              this.name = name;
          }

          public int getAge() {
              return age;
          }

          public void setAge(int age) {
              this.age = age;
          }
      }
      ```

2. **Inheritance**:
  - Inheritance is a mechanism where a new class inherits the properties and behavior (methods) of an existing class. The existing class is called the "base" or "parent" class, and the new class is called the "derived" or "child" class.
    - Example:
      ```java
      public class Animal {
          public void eat() {
              System.out.println("This animal eats food.");
          }
      }

      public class Dog extends Animal {
          public void bark() {
              System.out.println("The dog barks.");
          }
      }
      ```

3. **Polymorphism**:
  - Polymorphism allows objects to be treated as instances of their parent class rather than their actual class. The most common use of polymorphism is when a parent class reference is used to refer to a child class object.
    - Example:
      ```java
      public class Animal {
          public void makeSound() {
              System.out.println("Some generic animal sound");
          }
      }

      public class Dog extends Animal {
          @Override
          public void makeSound() {
              System.out.println("Bark");
          }
      }

      public class Cat extends Animal {
          @Override
          public void makeSound() {
              System.out.println("Meow");
          }
      }

      public class Main {
          public static void main(String[] args) {
              Animal myDog = new Dog();
              Animal myCat = new Cat();

              myDog.makeSound(); // Outputs: Bark
              myCat.makeSound(); // Outputs: Meow
          }
      }
      ```

4. **Abstraction**:
  - Abstraction is the concept of hiding the complex implementation details and showing only the essential features of the object. It helps in reducing programming complexity and effort.
    - Example:
      ```java
      abstract class Animal {
          public abstract void makeSound();
      }

      public class Dog extends Animal {
          @Override
          public void makeSound() {
              System.out.println("Bark");
          }
      }

      public class Main {
          public static void main(String[] args) {
              Animal myDog = new Dog();
              myDog.makeSound(); // Outputs: Bark
          }
      }
      ```

These principles help in creating modular, reusable, and maintainable code.

## Event-Driven Architecture
Event-driven architecture in .NET involves designing systems where the flow of the program is determined by events such as user actions, sensor outputs, or messages from other programs.

## Clean Architecture
Clean Architecture is a software design philosophy that emphasizes separation of concerns, making the system easier to maintain and test. It involves organizing code into layers, such as presentation, application, domain, and infrastructure.

## Browser Request for a Web Page
When a browser requests a web page, it sends an HTTP request to the server, which processes the request and sends back an HTTP response containing the requested resource.

**1. URL Input and DNS Resolution**
  - The user enters a URL (e.g., `https://www.example.com`) in the browser.
  - The browser checks its cache for the IP address of `www.example.com`.
  - If not found, it queries a **Domain Name System (DNS)** server to resolve the domain name into an IP address.

**2. Establishing a Connection**
  - Once the IP address is obtained, the browser establishes a **TCP (Transmission Control Protocol) connection** with the web server.
  - If HTTPS is used, a **TLS/SSL handshake** occurs to secure the connection.

**3. Sending an HTTP Request**
  - The browser sends an **HTTP request** (GET, POST, etc.) to the web server.
  - The request includes headers like:
    - **User-Agent** (browser type)
    - **Cookies** (if any)
    - **Referer** (previous page)

**4. Server Processing**
  - The web server receives the request and processes it.
  - If the page is dynamic (e.g., PHP, Python, or Node.js), the server may generate the page dynamically.
  - The server retrieves necessary data from databases or other resources.

**5. Server Response**
  - The server sends an **HTTP response** back to the browser.
  - The response contains:
    - **Status Code** (e.g., 200 OK, 404 Not Found, 500 Internal Server Error)
    - **Headers** (e.g., Content-Type, Cache-Control)
    - **Body** (HTML, CSS, JavaScript, JSON, etc.)

**6. Rendering the Page**
  - The browser parses the **HTML** and builds the **DOM (Document Object Model)**.
  - It fetches additional resources (CSS, JS, images, etc.).
  - The **CSSOM (CSS Object Model)** is created, and styles are applied.
  - JavaScript is executed.
  - The page is **rendered and displayed** to the user.

**7. User Interaction and Additional Requests**
  - If the user interacts with the page (e.g., clicks a link or submits a form), new requests may be sent.
  - JavaScript may make **AJAX** or **fetch API** requests for dynamic content updates.

This process happens in milliseconds to seconds, depending on network speed and server performance. 🚀

## Caching
Caching involves storing data in memory to improve performance by reducing the need to fetch data from a slower source.

## Middleware
Middleware are components that are used to handle requests and responses in an ASP.NET Core application pipeline.

## BDD and TDD in
- **BDD (Behavior-Driven Development)**: An extension of TDD that focuses on the behavior of an application.
- **TDD (Test-Driven Development)**: A development process where tests are written before the code that needs to pass the tests.

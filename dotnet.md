## CLI and CLR
- **CLI (Common Language Infrastructure)**: A platform for running .NET programs, providing a language-neutral environment.
- **CLR (Common Language Runtime)**: The virtual machine component of .NET that manages the execution of .NET programs.

## EF, LINQ, and ADO.NET
- **EF (Entity Framework)**: An ORM (Object-Relational Mapper) for .NET, enabling developers to work with a database using .NET objects.
- **LINQ (Language Integrated Query)**: A set of features in .NET that provides query capabilities directly in C# and VB.NET.
- **ADO.NET**: A set of classes that expose data access services for .NET Framework programmers.

## Extension Method
Extension methods allow you to add methods to existing types without modifying them. To create an extension method:
```csharp
public static class StringExtensions
{
    public static bool IsNullOrEmpty(this string str)
    {
        return string.IsNullOrEmpty(str);
    }
}
```

## Dependency Injection
Dependency Injection (DI) is a design pattern used to implement IoC (Inversion of Control), allowing the creation of dependent objects outside of a class and providing those objects to a class in various ways. Example:
```csharp
public interface IService { }
public class Service : IService { }
public class Client
{
    private readonly IService _service;
    public Client(IService service)
    {
        _service = service;
    }
}
```

## Generics
Generics allow you to define a class or method with a placeholder for the type of data it stores or uses. Example:
```csharp
public class GenericClass<T>
{
    public T Data { get; set; }
}
```

## Derived Class
A derived class is a class that inherits from another class. You can identify it by the `:` symbol. Example:
```csharp
public class BaseClass { }
public class DerivedClass : BaseClass { }
```

## async and await
Async and await are used for asynchronous programming. Example:
```csharp
public async Task<int> GetDataAsync()
{
    await Task.Delay(1000);
    return 42;
}
```

## virtual
The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow it to be overridden in a derived class. Example:
```csharp
public class BaseClass
{
    public virtual void Display() { }
}
public class DerivedClass : BaseClass
{
    public override void Display() { }
}
```

## Authorization and Authentication
- **Authentication**: Verifying the identity of a user.
- **Authorization**: Determining if a user has permission to perform an action.

## Abstraction
Abstraction involves hiding the complex implementation details and showing only the necessary features of an object.

## sealed Class
A sealed class cannot be inherited. Example:
```csharp
public sealed class SealedClass { }
```

## class and struct
- **Class**: A reference type that supports inheritance.
- **Struct**: A value type that does not support inheritance.

## abstract Class and interface
- **Abstract Class**: A class that cannot be instantiated and may contain abstract methods.
- **Interface**: A contract that defines a set of methods and properties that implementing classes must provide.

## Task and Thread
- **Task**: Represents an asynchronous operation.
- **Thread**: Represents a thread of execution.

## const and readonly
- **Const**: A compile-time constant.
- **Readonly**: A runtime constant that can only be assigned in the constructor.

## Access Modifier
Access modifiers define the visibility of a class and its members. Examples include `public`, `private`, `protected`, and `internal`.

## IEnumerable, ICollection, IList, and IQueryable
- **IEnumerable**: Represents a collection of objects that can be iterated.
- **ICollection**: Represents a collection of objects that can be counted and modified.
- **IList**: Represents a collection of objects that can be accessed by index.
- **IQueryable**: Represents a collection of objects that can be queried.

## yield
The `yield` keyword is used to return each element one at a time in an iterator method. Example:
```csharp
public IEnumerable<int> GetNumbers()
{
    yield return 1;
    yield return 2;
    yield return 3;
}
```

## static Class and Regular Class
- **Static Class**: A class that cannot be instantiated and can only contain static members.
- **Regular Class**: A class that can be instantiated and can contain both static and instance members.

## Constructor
A constructor is a special method that initializes an object. Types include default, parameterized, and static constructors.

## Destructor
A destructor is a method that is called when an object is destroyed. It is used to release unmanaged resources.

## Garbage Collector
The garbage collector automatically manages memory by reclaiming memory occupied by objects that are no longer in use.

## Method overriding and overloading
- **Overriding**: Redefining a base class method in a derived class.
- **Overloading**: Defining multiple methods with the same name but different parameters.

## delegate
A delegate is a type that represents references to methods with a specific parameter list and return type. Example:
```csharp
public delegate void MyDelegate(string message);
```

## Boxing and Unboxing
- **Boxing**: Converting a value type to an object type.
- **Unboxing**: Converting an object type back to a value type.

## Managed and Unmanaged
- **Managed Code**: Code that runs under the control of the CLR.
- **Unmanaged Code**: Code that runs outside the control of the CLR.

## Unit Test
Unit tests are automated tests that verify the correctness of a small piece of code. Frameworks include MSTest, NUnit, and xUnit.

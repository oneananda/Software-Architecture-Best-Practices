# Interface-Driven Development - IDD

#### `Interface-Driven Development - IDD` is a Software development design approach that emphasis on using interfaces to define contracts or boundaries between different components of the system.

The principle is, the components should interact each other using well defined interfaces which leads to 

- Modularity
- Flexiblity
- Testablity
- Maintainablity

## Key Concepts

### Interface as a contract

An interface defines a contract and the classes which implement those should comply with the same,

That means if an interface is having a method called `Print()` in C# like this

```
public interface IPrint
{
	void Print();
}
```

The implementing class should comply with the contract that it is implementing the method `Print()`

```
public class Process : IPrint
{
	public void Print()
	{
		// Print logic
	}
}
```

But there is a catch here:

`IPrint` is insisting the implementation should use the method `Print()` but in reality there is no necessity to implement the printing functionality inside the `Print()` function, we can choose to write any other logic inside the `Print()`, the interface has no control over this.

The `Print()` method in the Process class could include logic to print something to the console, save a file, or even do nothing at all. The implementation inside the `Print()` method is up to the developer.

This means that while the interface guarantees that the method `Print()` is available in the Process class, it doesn't ensure that the method performs any specific action related to printing. The method could theoretically do something entirely unrelated, like calculating a sum or logging data.

_The interface only ensures the method signature (i.e., the name, return type, and parameters) but has no control over the actual code inside the method._


### Decoupling

IDD encourages decoupling between components, Since components interact through interfaces, they don’t need to know about each other's concrete implementations. This reduces dependencies and allows for easier changes and maintenance.

But there is a catch here too

Using decoupling may lead to 

- Over-Decoupling

`Over-decoupling` can lead to a situation where the system becomes excessively fragmented. This means introducing too many layers or abstractions between components can make the system harder to understand and navigate. It can also introduce unnecessary complexity without significant benefits.

**Scenario:** Suppose you have a simple application that reads and writes user data to a database. To achieve maximum decoupling, you create separate classes and interfaces for every tiny aspect of the application: one class for data access, one for validation, one for transformation, and so on.

```
public interface IUserDataAccess
{
    void SaveUser(User user);
}

public class UserDataAccess : IUserDataAccess
{
    public void SaveUser(User user) { /* Save logic */ }
}

public interface IUserValidator
{
    bool Validate(User user);
}

public class UserValidator : IUserValidator
{
    public bool Validate(User user) { /* Validation logic */ }
}
```

_Problem: Managing and understanding the interactions between these highly decoupled components can become cumbersome, especially for a small application where simpler designs might be more appropriate._

### Interface Proliferation

Overusing interfaces can lead to a proliferation of small, fine-grained interfaces. This can make the system harder to manage and understand, and it may lead to a situation where you have many interfaces with single methods or tightly focused responsibilities.

### Difficulty in Testing

While interfaces make mocking easier, they can also complicate testing if not used properly. For example, a test might need to deal with multiple interfaces and their implementations, increasing the setup complexity for unit tests.
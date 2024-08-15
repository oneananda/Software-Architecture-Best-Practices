# Interface-Driven Development - IDD

### `Interface-Driven Development - IDD` is a Software development design approach that emphasis on using interfaces to define contracts or boundaries between different components of the system.

The principle is, the components should interact using well defined interfaces which leads to 

- Modularity
- Flexiblity
- Testablity
- Maintainablity

## Key Concepts

### Interface as a contract

An interface defines a contract and the classes which implement those should comply with the same,

That means if an interface is having a method called Print() in C# like this

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




# C# Language Guidelines
This is the guideline I follow for working with C# language. My goal with this guideline is to help others achieve *conciseness*, *readability* and *simplicity* in thier code.

## Table of Contents
- [Nomenclature](#Nomenclature)
    + [Namespaces](#Namespaces)
    + [Classes & Structs](#Classes--Structs)
    + [Interfaces](#Interfaces)
    + [Methods](#Methods)
    + [Fields](#Fields)
    + [Properties](#Properties)
    + [Parameters](#Parameters)
    + [Constants](#Constants)
    + [Events & Delegates](#Events--Delegates)
    + [Misc](#Misc)
- [Code Style](#Code--Style)
    + [Brace Style](#Brace-Style)
    + [Spacing & Indentation](#Spacing--Indentation)
    + [Statements & Declarations](#Statements--Declarations)
    + [Implicitly Typed Local Variables](#Implicitly-Typed-Local-Variables)
    + [Delegates](#Delegates)
    + [Exceptions](#Exceptions)
    + [Event Handling](#Event-Handling)
    + [Disposable Classes](#Disposable-Classes)
- [Code Documentation](#Code-Documentation)

## Nomenclature
Nomenclature should be as per language guideline per [C# Coding Convention article by Microsoft](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions). This section contains some do and don'ts related to nomenclature.

### Namespaces
Namespaces should be all **Pascal Case**, without the use of hyphens (-) or underscores (_). The only exception to this rule are acronyms like GUI or HTTP.

**DO:**
```csharp
namespace Zen.Infrastructure.Core
```

```csharp
namespace ZenInfrastructure.Core
```

```csharp
namespace Zen.Infrastructure.GUI
```

**DONT:**
```csharp
namespace zen.infrastructure.core
```

```csharp
namespace Zen.Infrastructure.gui
```

```csharp
namespace zen_infrastructure.core
```

```csharp
namespace zenInfrastructure.core
```
### Classes & Structs
Class and struct names should always be **Pascal Case** and should always be **Nouns** to denote that it is an entity. For Example
- TemplateParser
- MySpecialClass

### Interfaces
Interface names should follow same convention as class and struct, but should be prefixed by capital letter I. For example
- ITemplateParser
- IMySpecialClass

### Methods
Method names should always be **Verbs** to denote that some work is being done by it. Method naming should follow following conventions
- `public`, `internal` & `protected` method names should be written using **Pascal Case**
- `private` method names should be written using **Camel Case**

Same rules should be applied to `static` counterparts.

**DO:**
```csharp
public void DoSomething()
{

}
```

```csharp
public static void DoSomething()
{

}
```

```csharp
internal void DoSomething()
{

}
```

```csharp
protected void DoSomething()
{

}
```

```csharp
private void doSomething()
{

}
```

**DONT:**
```csharp
public void doSomething()
{

}
```

```csharp
public void do_something()
{

}
```

```csharp
private void _doSomething()
{

}
```

```csharp
private static void _do_something()
{

}
```
### Fields
All field names should be written using **Camel Case**. This should also be applied to all public or static fields. For example
```csharp
public class MyClass
{
    public int myIntegerField;
    public static string myStaticString;
    int myPackagedField;
    private int myPrivateInteger;
    protected DateTime myProtectedDateTime;
}
```
**DO:**
```csharp
public int myPublicIntegerField;
```

```csharp
public static string firstName;
```

```csharp
private string lastName;
```

**DONT:**
```csharp
private int _myInteger;
```

```csharp
public int MyInteger;
```

```csharp
public static int MY_INTEGER;
```

### Properties
All property names should be written using **Pascal Case**. For example
```csharp
class MyClass
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public string FullName { get => FirstName + LastName; }
    // Property with backing field
    private int pageNumber;
    public int PageNumber
    {
        get { return pageNumber; }
        set { pageNumber = value; }
    }
}
```

### Parameters
All parameter names should be written in **Camel Case**. For example
```csharp
public class MyClass
{
    public MyClass(string firstName)
    {

    }

    private void doSomething(string inputVariable)
    {

    }

    public void DoSomethingElse(string myVariable)
    {

    }
}
```
### Constants
All constant names should be in **CAPITAL SNAKE CASE**. For example
```csharp
public const string SQS_QUEUE = "SQS_QUEUE";
public const string MY_CONSTANT = "My Directory";
```

**DO:**
```csharp
public const string MY_CONSTANT = "My Directory";
```
**DONT:**
```csharp
public const string MyConstant = "My Directory";
```

### Events & Delegates
Delegates and events should follow same guidelines as Methods. For example

```csharp
public delegate void DoSomething(string value);
private delegate void doSomething(string value);

public event Action<int> IntegerValueChanged;
private event Action<string> stringValueChanged;
```
### Misc
Aside from namespaces, Acrnoyms should be treated as normal words. For example
```csharp
public XmlHttpRequest request;
String url;
```
**DO:**
```csharp
class XmlHttpRequest
{

}
```

```csharp
public string Url { get; set; } 
```

**DONT:**
```csharp
class XMLHTTPRequest
{
    
}
```

```csharp
public string URL { get; set; } 
```

Avoid using random names for variables, classes and methods etc. Use concise variable names which are readable and easy to understand.

**DO:**
```csharp
int row, column;
var array = new int[row][column];
```

**DONT:**
```csharp
int i, j;
var arr = new int[i][j];
```

## Code Style
This section covers the code styling guidelines to make the code more readable and understandable. 

### Brace Style
All braces should get their own lines as per C# convention

**DO:**
```csharp
class MyClass
{
    void DoSomething(bool input)
    {
        if(input)
        {

        }
        else
        {

        }
    }
}
```

**DONT:**
```csharp
class MyClass {
    void DoSomething(bool input) {
        if(input) {

        }
        else {

        }
    }
}
```

### Spacing & Indentation
Spacing and indentation should be consistent througout the code. Tab size should use **4 spaces** and indentation should use tabs over spaces for better readability

**DO:**
```csharp
class MyClass
{
    void DoSomething()
    {

    }
}
```

**DONT:**
```csharp
class MyClass
{
  void DoSomething()
  {

  }
}
```

### Statements & Declarations
Write only one statement per line

**DO:**
```csharp
doSomething();
doSomethingElse();
```

**DONT:**
```csharp
doSomething(); doSomethingElse();
```

Write only one declaration per line
**DO:**
```csharp
string firstName;
string lastName;
```

**DONT:**
```csharp
string firstName, lastNmae;
```

### Implicitly Typed Local Variables
Use `var` for local variables declaration when type of the variable is obvious from the right side of the assignment. 
**DO:**
```csharp
var firstName = "John";
var number = 1;
```

Don't use var when type is not apparent from the right side of the assignment. 
**DONT:***
```csharp
int result = ExampleClass.CalculateResult();
```
Don't rely on variable name to specify the type of variable. For example, in the following example, number is a string rather than an int.
**DONT:***
```csharp
var number = Console.ReadLine()
```
### Delegates
Use [built-in delegate types](https://docs.microsoft.com/en-us/dotnet/standard/delegates-lambdas) `Func<>`, `Action<>` and `Predicate<>` instead of defining custom delegate types. 
**DO:**
```csharp
Action<string> print = value => Console.WriteLine($"Value is {value}"); 
```
### Exceptions
C# provides a whole slew of built in exception types. Try to use these exception types whenever appropriate. 
**DO:**
```csharp
void DoSomething(string input)
{
    if(string.IsNullOrWhiteSpace(input))
    {
        throw new ArgumentNullException(nameof(input));
    }
}
```

In certain cases, the built in exceptions do not do enough for you or make sense of what you are trying to do. C# provides ability to create custom exceptions by extending from `Exception` class. So you should create custom exceptions which make sense in your business application.
**DO:**
```csharp
class TransactionNotFoundException : Exception
{
    public TransactionNotFoundException(Guid id) : base($"Transaction not found for id: {id}")
    {
        
    }
}
public async Task<Transaction> GetTransactionAsync(Guid id)
{
    Transaction transaction = await api.GetTransactionAsync(id);
    if(transaction is null)
        throw new TransactionNotFoundException(id); 
}
```
### Event Handling
If you're defining an event handler that you don't need to remove later, use a lambda expression.
**DO:**
```csharp
public MyWorker()
{
    this.OnApplicationStop = (sender, event) => 
    {
        try
        {
            connection.Dispose();
        }
        catch (ObjectDisposedException)
        {
        }
    }
}
```

### Disposable Classes
Properly deallocate resources by using `using` statement with disposable classes. 
**DO:**
```csharp
using(MemoryStream stream = new MemoryStream())
{
    // work with memory stream
}
```

If you do not want to dispose the class readily, then you can call dispose function later on. When using `Dispose()` function, be sure to catch `ObjectDisposedException` just in case the object has been disposed off by external entity. This can happen when using Dependency Inection containers.

```csharp
try
{
    connection.Dispose();
}
catch (ObjectDisposedException)
{
}
```
## Code Documentation
TODO
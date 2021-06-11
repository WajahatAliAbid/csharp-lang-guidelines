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
Method names should always be **Verbs** to denote that some work is being done by it. Method naming must follow following conventions
- `public`, `internal` & `protected` method names must be written using **Pascal Case**
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
All constant names must be in **CAPITAL SNAKE CASE**. For example
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
### Misc
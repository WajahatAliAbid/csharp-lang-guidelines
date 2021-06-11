# C# Language Guidelines
This is the guideline I follow for working with C# language. My goal with this guideline is to help others achieve *conciseness*, *readability* and *simplicity* in thier code.

## Table of Contents
- [Nomenclature](#Nomenclature)

## Nomenclature
Nomenclature should be as per language guideline per [C# Coding Convention article by Microsoft](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions). This section contains some do and don'ts related to nomenclature.

### Namespaces
Namespaces should be all *Pascal Case*, without the use of hyphens (-) or underscores (_). The only exception to this rule are acronyms like GUI or HTTP.

**DO:**
```csharp
Zen.Infrastructure.Core
```

```csharp
ZenInfrastructure.Core
```

```csharp
Zen.Infrastructure.GUI
```

**DONT:**
```csharp
zen.infrastructure.core
```

```csharp
Zen.Infrastructure.gui
```

```csharp
zen_infrastructure.core
```

```csharp
zenInfrastructure.core
```

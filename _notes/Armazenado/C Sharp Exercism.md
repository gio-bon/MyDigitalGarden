---
title : C# Exercism
---

## About Basics

C# is a statically-typed language, which means that everything has a type at compile-time. Assigning a value to a name is referred to as defining a variable. A variable can be defined either by explicitly specifying its type, or by letting the C# compiler infer its type based on the assigned value (known as *type inference*). Therefore, the following two variable definitions are equivalent:

```csharp
int explicitVar = 10; // Explicitly typed
var implicitVar = 10; // Implicitly typed

```

Updating a variable's value is done through the `=` operator. Once defined, a variable's type can never change.

```csharp
var count = 1; // Assign initial value
count = 2;     // Update to new value

// Compiler error when assigning different type
// count = false;

```

C# is an [object-oriented language](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/object-oriented-programming) and requires all functions to be defined in a *class*. The `class` keyword is used to define a class. Objects (or *instances*) are created by using the `new` keyword.

```csharp
class Calculator
{
    // ...
}

var calculator = new Calculator();

```

A function within a class is referred to as a *method*. Each method can have zero or more parameters. All parameters must be explicitly typed, there is no type inference for parameters. Similarly, the return type must also be made explicit. Values are returned from methods using the `return` keyword. To allow a method to be called by code in other files, the `public` access modifier must be added.

```csharp
class Calculator
{
    public int Add(int x, int y)
    {
        return x + y;
    }
}
```

Methods are invoked using dot (`.`) syntax on an instance, specifying the method name to call and passing arguments for each of the method's parameters. Arguments can optionally specify the corresponding parameter's name.

```csharp
var calculator = new Calculator();
var sum_v1 = calculator.Add(1, 2);
var sum_v2 = calculator.Add(x: 1, y: 2);

```

Scope in C# is defined between the `{` and `}` characters.

C# supports two types of comments. Single line comments are preceded by `//` and multiline comments are inserted between `/*` and `*/`.

### Learn More

[Operadores lógicos boolianos - referência do C#](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/operators/boolean-logical-operators)

## About Extension Methods

Extension methods allow adding methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type. They are defined as static methods but are called by using instance method syntax. Their first parameter is preceded by the `this` modifier, and specifies which type the method operates on, and are brought into scope at the namespace level.

```csharp
public static int WordCount(this string str)
{
    return str.Split().Length;
}

"Hello World".WordCount();
// => 2

```

[Métodos de extensão - Guia de Programação em C#](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)

Extension methods are brought into scope at the namespace level. This means that if you are in different namespace to the one the extension method is defined in, it's namespace must be in a `using` directive first; For example, if we wanted to use the above example in our code, we would first need a `using MyExtensions` directive. If you are in the same namespace as the one the extension method is defined in, you can use the extension methods without a `using` directive.

A well-known example of extension methods are the [LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/) standard query operators that add query functionality to the existing IEnumerable types. To bring these into scope we need a `using System.Linq;` directives.

## About Tuples

In C#, a tuple is a data structure which organizes data, holding two or more fields of any type.

A tuple is typically created by placing 2 or more expressions separated by commas, within a set of parentheses.

```csharp
string boast = "All you need to know";
bool success = !string.IsNullOrWhiteSpace(boast);
(bool, int, string) triple = (success, 42, boast);

Console.WriteLine(triple.Item2); //42
```

A tuple can be used in assignment and initialization operations, as a return value or a method argument.

Fields are extracted using dot syntax. By default, the first field is `Item1`, the second `Item2`, etc. Non-default names are discussed below.

```csharp
// initialization
(int, int, int) vertices = (90, 45, 45);

// assignment
vertices = (60, 60, 60);

//  return value
(bool, int) GetSameOrBigger(int num1, int num2)
{
    return (num1 == num2, num1 > num2 ? num1 : num2);
}

// method argument
int Add((int, int) operands)
{
    return operands.Item1 + operands.Item2;
}

```

Field names `Item1` etc. do not make for readable code. The code below shows 2 ways to name the fields of tuples. Note also, in the code below, that `var` can be used with tuples and the type inferred. This works equally well for tuples with named and unnamed fields.

```csharp
// name items in declaration
(bool success, string message) results = (true, "well done!");
bool mySuccess = results.success;
string myMessage = results.message;

// name items in creating expression
var results2 = (success: true, message: "well done!");
bool mySuccess2 = results2.success;
string myMessage2 = results2.message;

```

[Tipos de tupla - referência de C#](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/value-tuples#tuples-as-method-return-values)

## About Classes

The primary object-oriented construct in C# is the *class*, which is a combination of data (*fields*) and behavior (*methods*). The fields and methods of a class are known as its *members*.

Access to members can be restricted through access modifiers, the two most common ones being:

- `public`: the member can be accessed by any code (no restrictions).
- `private`: the member can only be accessed by code in the same class.

You can think of a class as a template for creating instances of that class. To create an instance of a class (also known as an *object*), the `new` keyword is used:

```csharp
class Car
{
}

// Create two car instances
var myCar = new Car();
var yourCar = new Car();

```

Fields have a type and a name (defined in camelCase) and can be defined anywhere in a class (defined in PascalCase):

```csharp
class Car
{
    // Accessible by anyone
    public int weight;

    // Only accessible by code in this class
    private string color;
}

```

One can optionally assign an initial value to a field. If a field does *not* specify an initial value, it wll be set to its type's default value. An instance's field values can be accessed and updated using dot-notation.

```csharp
class Car
{
    // Will be set to specified value
    public int weight = 2500;

    // Will be set to default value (0)
    public int year;
}

var newCar = new Car();
newCar.weight; // => 2500
newCar.year;   // => 0

// Update value of the field
newCar.year = 2018;

```

Private fields are usually updated as a side-effect of calling a method. Such methods usually don't return any value, in which case the return type should be `void`:

```csharp
class CarImporter
{
    private int carsImported;

    public void ImportCars(int numberOfCars)
    {
        // Update private field from public method
        carsImported = carsImported + numberOfCars;
    }
}
```

[Classes](https://docs.microsoft.com/pt-br/dotnet/csharp/fundamentals/types/classes#creating-objects)

[Campos - Guia de Programação em C#](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/classes-and-structs/fields)

## About Constructors

Creating an instance of a *class* is done by calling its *constructor* through the `new` operator. A constructor is a special type of method whose goal is to initialize a newly created instance. Constructors look like regular methods, but without a return type and with a name that matches the classes' name.

```csharp
class Library
{
    private books;

    public Library()
    {
        // Initialize the books field
        this.books = 10;
    }
}

// This will call the constructor
var library = new Library();

```

Like regular methods, constructors can have parameters. Constructor parameters are usually stored as (private) fields to be accessed later, or else used in some one-off calculation. Arguments can be passed to constructors just like passing arguments to regular methods.

```csharp
class Building
{
    private int numberOfStories;
    private int totalHeight;

    public Building(int numberOfStories, double storyHeight)
    {
        this.numberOfStories = numberOfStories;
        this.totalHeight = numberOfStories * storyHeight;
    }
}

// Call a constructor with two arguments
var largeBuilding = new Building(55, 6.2)
```

## About Datetimes

A `DateTime` in C# is an immutable object that contains both date *and* time information. `DateTime` instances are manipulated by calling their methods. Once a `DateTime` has been constructed, its value can never change. Any methods that appear to modify a `DateTime` will actually return a new `DateTime`.

The textual representation of dates and times is dependent on the *culture*. Consider a `DateTime` with its date set to March 28 2019 and its time set to 14:30:59. Converting this `DateTime` to a `string` when using the `en-US` culture (American English) returns `"3/28/19 2:30:59 PM"`. When using the `fr-BE` culture (Belgian French), the same code returns a different value: `"28/03/19 14:30:59"`.

Understanding which `DateTime` methods are culture-dependent is important to know. In general, any `DateTime` method that deals with `string`s (either as input or output) will be dependent on the current culture.

[Converter cadeias de caracteres em DateTime](https://docs.microsoft.com/pt-br/dotnet/standard/base-types/parsing-datetime)

[DateTime Estrutura (System)](https://docs.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-6.0)
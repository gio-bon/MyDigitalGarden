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

## About Booleans

Booleans in C# are represented by the `bool` type, which values can be either `true` or `false`.

C# supports three boolean operators: `!` (NOT), `&&` (AND), and `||` (OR).

### Learn More

[Operadores lógicos boolianos - referência do C#](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/operators/boolean-logical-operators)

## About Strings

A `string` in C# is an object that represents immutable text as a sequence of Unicode characters (letters, digits, punctuation, etc.). Double quotes are used to define a `string` instance:

```csharp
string fruit = "Apple";
```

Strings are manipulated by calling the string's methods. Once a string has been constructed, its value can never change. Any methods that appear to modify a string will actually return a new string.

Multiple strings can be concatenated (added) together. The simplest way to achieve this is by using the `+` operator.

```csharp
string name = "Jane";
"Hello " + name + "!";
// => "Hello Jane!"

```

For any string formatting more complex than simple concatenation, string interpolation is preferred. To use interpolation in a string, prefix it with the dollar (`$`) symbol. Then you can use curly braces (`{}`) to access any variables inside your string.

```csharp
string name = "Jane";
$"Hello {name}!";
// => "Hello Jane!"

```

[Como concatenar várias cadeias de caracteres (Guia do C#)](https://docs.microsoft.com/pt-br/dotnet/csharp/how-to/concatenate-multiple-strings)

[Como Pesquisar cadeias de caracteres (guia C#)](https://docs.microsoft.com/pt-br/dotnet/csharp/how-to/search-strings#where-does-the-sought-text-occur-in-a-string)

[Como modificar o conteúdo da cadeia de caracteres - Guia do C#](https://docs.microsoft.com/pt-br/dotnet/csharp/how-to/modify-string-contents)

[Alterando o caso no .NET](https://docs.microsoft.com/pt-br/dotnet/standard/base-types/changing-case)

[Como comparar cadeias de caracteres - Guia do C#](https://docs.microsoft.com/pt-br/dotnet/csharp/how-to/compare-strings)

### Métodos

*Split é usado para quebrar uma cadeia de caracteres delimitada em subcadeias de caracteres.* - [String.Split Método \(System\) - Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/api/system.string.split?view=net-6.0)

*Retorna uma nova cadeia de caracteres na qual todas as ocorrências à esquerda e à direita de um conjunto de caracteres especificados da cadeia de caracteres atual são removidas.* - [String.Trim Método \(System\) - Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/api/system.string.trim?view=net-6.0)

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

## About If Statements

In this exercise you must conditionally execute logic. The most common way to do this in C# is by using an `if/else` statement:

```csharp
int x = 6;

if (x == 5)
{
    // Execute logic if x equals 5
}
else if (x > 7)
{
    // Execute logic if x greater than 7
}
else
{
    // Execute logic in all other cases
}
```

The condition of an `if` statement must be of type `bool`. C# has no concept of *truthy* values.

### Switch

Forma de se usar switch:

```csharp
public static double SuccessRate(int speed) => speed switch
    {
        0 => 0,
        <= 4 => 1.0,
        <= 8 => 0.9,
        <= 9 => 0.8,
        _ => 0.77,
    };
```

Que substitui isso:

```csharp
public static double SuccessRate(int speed)
    {
        if(speed == 10){
            return 0.77;
        }else if(speed == 9){
            return 0.8;
        }else if(speed >=5 && speed <=8){
            return 0.9;
        }else if(speed >= 1 && speed <=4){
            return 1;
        }else{
            return 0;
        }
    }
```

## About Numbers

One of the key aspects of working with numbers in C# is the distinction between integers (numbers with no digits after the decimal separator) and floating-point numbers (numbers with zero or more digits after the decimal separator).

The two most commonly used numeric types in C# are `int` (a 32-bit integer) and `double` (a 64-bit floating-point number).

```csharp
int i = 123;
double d = 54.29;

```

Both integers and floating-point numbers can use the `_` character as a *digit separator*, which can help when defining large numbers:

```csharp
int largeInt = 1_000_000;
// => 1000000

double largeDouble = 9_876_543.21;
// => 9876543.21

```

Arithmetic is done using the standard [arithmetic operators](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/arithmetic-operators) (`+`, `-`, `*`, etc.). Numbers can be compared using the standard [comparison operators](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/comparison-operators) (`<`, `>=`, etc.) and the [equality-](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/equality-operators) operator (`==`) and [inequality](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/equality-operators) operator (`!=`).

```csharp
5 * 6;
// => 30

1.2 > 0.8
// => true

2 != 4
// => true

```

## Conversões

When converting between numeric types, there are two types of numeric conversions:

1. Implicit conversions: no data will be lost and no additional syntax is required.
2. Explicit conversions: data could be lost and additional syntax in the form of a *cast* is required.

As an `int` has less precision than a `double`, converting from an `int` to a `double` is safe and is thus an implicit conversion. However, converting from a `double` to an `int` could mean losing data, so that requires an explicit conversion.

```csharp
int i = 9;
double d = 2.66;

// Safe conversion, thus implicit conversion
double fromInt = i;

// Potentially unsafe conversion, thus explicit conversion
int fromDouble = (int)d;

```

Converte a representação de cadeia de caracteres especificada de um número em um inteiro com sinal de 32 bits equivalente. [Convert.ToInt32 Método \(System\) - Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/api/system.convert.toint32?view=net-6.0)

[Coerções e conversões de tipo - Guia de Programação em C#](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/types/casting-and-type-conversions)

## LINQ

[Visão geral do LINQ - .NET](https://docs.microsoft.com/pt-br/dotnet/standard/linq/)

## About Nullability

In C#, the `null` literal is used to denote the absence of a value. A *nullable* type is a type that allows for `null` values.

Prior to C# 8.0, reference types were always nullable and value types were not. A value type can be made nullable though by appending it with a question mark (`?`).

```csharp
string nullableReferenceType = "hello";
nullableReferenceType = null; // Valid as type is nullable

int nonNullableValueType = 5;
nonNullableValueType = null; // Compile error as type is not nullable

int? nullableValueType = 5; // Define nullable value type
nullableValueType = null;   // Valid as type is nullable

```

Accessing a member of a variable which value is `null` will compile fine, but result in a `NullReferenceException` being thrown at runtime:

```csharp
string sentence = null;

// Throws NullReferenceException at runtime
sentence.Length;

```

To counter this common type of mistake, C# 8 allows one to opt-into a feature that makes reference types non-nullable by default:

```csharp
string nonNullableReferenceType = "book";
nonNullableReferenceType = null; // Compile warning (no error!)

string? nullableReferenceType = "movie";
nullableReferenceType = null; // Valid as type is nullable

```

To safely work with nullable values, one should check if they are `null` before working with them:

```csharp
string NormalizedName(string? name)
{
    if (name == null)
    {
        return "UNKNOWN";
    }
    else
    {
        // Value is not null at this point, so no compile warning
        // and no runtime NullReferenceException being thrown
        return name.ToUpper();
    }
}

NormalizedName(null); // => "UNKNOWN"
NormalizedName("Elisabeth"); // => "ELISABETH"

```

The `??` operator allows one to return a default value when the value is `null`:

```csharp
string? name1 = "John";
var test1 = name1 ?? "Paul"; // => "John"

string? name2 = null;
var test2 = name2 ?? "George"; // => "George"

```

The `?.` operator allows one to call members safely on a possibly `null` value:

```csharp
string? fruit = "apple";
fruit?.Length; // => 5

string? vegetable = null;
vegetable?.Length; // => null

```

## **About Do While Loops**

A less commonly used alternative to the above syntax is a `do-while` loop:

```csharp
int x = 23;

do
{
// Execute logic if x > 10
    x = x - 2;
} while (x > 10)
```

## **About While Loops**

In this exercise you may also want to use a loop. There are several ways to write loops in C#, but the `while` loop is most appropriate here:

```csharp
int x = 23;

while (x > 10)
{
// Execute logic if x > 10
    x = x - 2;
}
```

## ****About Floating Point Numbers****

A floating-point number is a number with zero or more digits behind the decimal separator. Examples are `-2.4`, `0.1`, `3.14`, `16.984025` and `1024.0`.

Different floating-point types can store different numbers of digits after the digit separator - this is referred to as its precision.

C# has three floating-point types:

- `float`: 4 bytes (~6-9 digits precision). Written as `2.45f`.
- `double`: 8 bytes (~15-17 digits precision). This is the most common type. Written as `2.45` or `2.45d`.
- `decimal`: 16 bytes (28-29 digits precision). Normally used when working with monetary data, as its precision leads to less rounding errors. Written as `2.45m`.

As can be seen, each type can store a different number of digits. This means that trying to store PI in a `float` will only store the first 6 to 9 digits (with the last digit being rounded).

## **About Randomness**

In C# randomness is achieved with the help of `System.Random`. Typically, you create an instance and then call one of its `Next()` or `NextDouble()` methods, possibly multiple times depending on the use-case.

```csharp
Random rand = new Random();
var aleatorio1 = rand.Next(100, 300); //Next(int maxValue, int maxValue)
Console.WriteLine(aleatorio1); //164
var aleatorio2 = rand.NextDouble();
Console.WriteLine(aleatorio2); //0,8545950217190631
```

Retorna um número inteiro aleatório não negativo menor que o máximo especificado ou retorna um inteiro aleatório que está dentro do intervalo especificado. - [Random.Next Método \(System\) - Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/api/system.random.next?view=net-6.0)

Retorna um número de ponto flutuante aleatório maior ou igual a 0,0 e menor que 1.0. - [Random.NextDouble Método \(System\) - Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/api/system.random.nextdouble?view=net-6.0)

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
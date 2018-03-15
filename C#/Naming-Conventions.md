# C# Naming Conventions
The following naming conventions are consistent with the Microsoft's .NET Framework and easy to read.

## Namespaces
Use **PascalCasing** for namespaces and try to match the name to the directory location. Always start the namespace with the project or company and then project name.

```c#
namespace Sabre.Domain.Sales
{
	
}
```

## Classes & Structs
Use **PascalCasing** for class and struct names and never use abbreviations. Acronyms are sometimes acceptable if they are well defined, but must follow the pascal casing convention (e.g. HtmlDocument, CssDocument or HttpRequest etc). Use noun or noun phrases to name a class. Make the file name the same as the class name and only put one class or struct in each file.

```c#
public class HtmlDocument
{
	
}
```

Be sure to use the [Ubiquitous Language](https://martinfowler.com/bliki/UbiquitousLanguage.html) when deciding on class or struct names, but try to keep the names short and concise.

## Enums
Use **PascalCasing** for enum names but DO NOT suffix enum names with **Enum**. Use singular names, except bit field enums.

Why: consistent with the Microsoft's .NET Framework and makes the code more natural to read. Plural flags because enum can hold multiple values (using bitwise 'OR').

```c#
// Correct
public enum Color
{
    Red,
    Green,
    Blue,
    Yellow,
    Magenta,
    Cyan
}
 
// Exception
[Flags]
public enum Dockings
{
    None = 0,
    Top = 1, 
    Right = 2, 
    Bottom = 4,
    Left = 8
}
```

Make the file name the same as the enum name and only put one enum in each file.

## Interfaces
The convention for naming interfaces is the same as classes except they must be pre-pended with a capital **I**.  Interface names are noun (phrases) or adjectives.

```c#
public interface IDictionary
{
	
}
```

## Variables & Arguments
Use **camelCasing** for method arguments and variable names. Avoid using abbreviations and only use acronyms where they are well defined. Make use of the Ubiquitous Language and avoid names that do not provide any context (e.g. use customerId instead of just id).

Try to use names that describe the assigned type.

```c#
var firstName = "Code";
var lastName = "Change";
var isEmployed = true;
var salary = 20000;
var birthDate = new DateTime(1980, 02, 05);
```

**DO NOT** use [Hungarian notation](https://en.wikipedia.org/wiki/Hungarian_notation) or any other type identification in identifiers.

```c#
// DO NOT DO THIS!
var strFirstName = "Code";
var boolEmployed = true;
var decSalary = 20000;
```

**DO NOT** use underscores in identifiers. Exception: prefix private class level variables with an underscore.

```c#
// Correct
public DateTime appointmentDate;
public TimeSpan timeLeft;

// Avoid
public DateTime appointment_Date;
public TimeSpan time_Left;

// Exception
private DateTime _registrationDate;
```

## Properties
Use **PascalCasing** for property names and follow the variable naming conventions thereafter.

```c#
public string FirstName { get; private set; }
public string LastName { get; private set; }
public string IsEmployed { get; private set; }
public decimal Salary { get; private set; }
public DateTime? BirthDate { get; private set; }
```

## Constants
Follow the same naming conventions as for properties. DO NOT use capital letters as this grabs too much attention.

```c#
// Correct
public static const string ShippingType = "DropShip";
 
// Avoid
public static const string SHIPPINGTYPE = "DropShip";
```

## Methods
Use **PascalCasing** for method names and make the name descriptive as to what its purpose is. Make use of the Ubiquitous Language and give an indication of what the method will do and return.

For CRUD type methods, make use of the Add, Get, Update and Remove name prefixes.

```c#
public void AddAddress
	(
		Address address
	)
{
	\\ ...
}

public int CalculateAge
	(
		DateTime birthDate
	)
{
	\\ ...
}
```

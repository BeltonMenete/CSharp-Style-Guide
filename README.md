# C#-Style-Guide

## Class Names

<mark>Do not</mark> use **PascalCasing** for class names and method names.

````csharp
public class ClientActivity
{
    public void ClearStatistics()
    {
        //...
    }
    public void CalculateStatistics()
    {
        //...
    }
}
````

> Why: consistent with the Microsoft's .NET Core, and easy to read.

## Variable Names

<mark>Do</mark>  use **camelCasing** for local variables and method arguments.

````csharp
public class UserLog
{
  public void Add(LogEvent logEvent)
  {
      int itemCount = logEvent.Items.Count;
      // ...
  }
}
````

> Why: consistent with the Microsoft's .NET Core, and easy to read.

## Identifiers
<mark>Do not</mark>  use **Hungarian** notation or any other type identification in identifiers

````csharp
// Good
int counter;
string name;
 
// Bad
int iCounter;
string strName;
````

> Why: consistent with the Microsoft's .NET Core. In addition, the Visual Studio IDE makes it very easy to determine the type of a variable (via tooltips). It is best to avoid type indicators in identifiers.

## Constants

<mark>Do not</mark>  use Screaming Caps for constants or readonly variables

````csharp
// Good
public static const string ShippingType = "DropShip";
 
// Bad
public static const string SHIPPINGTYPE = "DropShip";
````

> Why: consistent with the Microsoft's .NET Core. Caps grap too much attention

## Abbreviations

<mark>avoid</mark> using Abbreviations.
Exceptions: abbreviations commonly used as names, such as **Id, Xml, Ftp, Uri**

````csharp
// Good
UserGroup userGroup;
Assignment employeeAssignment;
 
// Bad
UserGroup usrGrp;
Assignment empAssignment;
 
// Exceptions
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
````

> Why: consistent with the Microsoft's .NET Core. It prevents inconsistent abbreviations by different developers.

## Abbreviation Casing

<mark>Do</mark> use **PascalCasing** for abbreviations 3 characters or more (2 chars are both uppercase)

````csharp
HtmlHelper htmlHelper;
FtpTransfer ftpTransfer;
UIControl uiControl;
````
> Why: consistent with the Microsoft's .NET Core. Caps would grap visually too much attention.

## No Underscores

<mark>Do not</mark> use Underscores in identifiers.
Exception: you can prefix private static variables with an underscore.

````csharp
// Good
public DateTime clientAppointment;
public TimeSpan timeLeft;
 
// Bad
public DateTime client_Appointment;
public TimeSpan time_Left;
 
// Exception
private DateTime _registrationDate;
````
> Why: consistent with the Microsoft's .NET Core. It makes code more natural to read (without 'slur'). Also avoids underline stress, i.e. inability to see underline.

## Type Names

<mark>Do</mark> use predefined type names instead of system type names like Int16, Single, UInt64, etc

````csharp
// Good
string firstName;
int lastIndex;
bool isSaved;
 
// Bad
String firstName;
Int32 lastIndex;
Boolean isSaved;
````
> Why: consistent with the Microsoft's .NET Core. It makes code more natural to read.

## Implicit Types

<mark>Do</mark> use implicit type **var** for local variable declarations.
Exception: primitive types (int, string, double, etc) use predefined names.

````csharp
var stream = File.Create(path);
var customers = new Dictionary();
 
// Exceptions
int index = 100;
string timeSheet;
bool isCompleted;
````
> Why: removes clutter, particularly with complex generic types. Type is easily detected with Visual Studio tooltips.

## Noun Class Names

<mark>Do</mark> use noun or noun phrases to name a class.

````csharp
public class Employee
{
}
public class BusinessLocation
{
}
public class DocumentCollection
{
}
````
> Why: consistent with the Microsoft's .NET Core. Makes classes easy to remember.

## Interfaces

<mark>Do</mark> prefix interfaces with the letter `I` .  Interface names are noun (phrases) or adjectives.

````csharp
public interface IShape
{
}
public interface IShapeCollection
{
}
public interface IGroupable
{
}
````

> Why: consistent with the Microsoft's .NET Core.

## File Names

<mark>Do</mark> name source files according to their main classes. Exception: file names with partial classes reflect their source or purpose, e.g. **designer, generated, etc.**

````csharp
// Located in Task.cs
public partial class Task
{
    //...
}
// Located in Task.generated.cs
public partial class Task
{
    //...
}
````

> Why: consistent with the Microsoft practices. Files are alphabetically sorted and partial classes remain adjacent.

## Namespaces

<mark>Do</mark> organize namespaces with a clearly defined structure

````csharp
// Examples
namespace Company.Product.Module.SubModule
namespace Product.Module.Component
namespace Product.Layer.Module.Group
````

> Why: consistent with the Microsoft's .NET Core. Maintains good organization of your code base.

## Curly Brackets

<mark>Do</mark> vertically align curly brackets.

// Good
class Program
{
    static void Main(string[] args)
    {
    }
}

> Why: Microsoft has a different standard, but developers have overwhelmingly preferred vertically aligned brackets.

## Member Variables

<mark>Do</mark> declare all member variables at the top of a class, with static variables at the very top.

````csharp
// Good
public class Account
{
    public static string BankName;
    public static decimal Reserves;
 
    public string Number {get; set;}
    public DateTime DateOpened {get; set;}
    public DateTime DateClosed {get; set;}
    public decimal Balance {get; set;}
 
    // Constructor
    public Account()
    {
        // ...
    }
}
````

> Why: generally accepted practice that prevents the need to hunt for variable declarations.

## Enums

<mark>Do</mark> use singular names for enums. Exception: bit field enums.

````csharp
// Good
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
````

> Why: consistent with the Microsoft's .NET Core, and makes the code more natural to read. Plural flags because enum can hold multiple values (using bitwise 'OR').

## Enum Types

<mark>Do not</mark> explicitly specify a type of an enum or values of enums (except bit fields)

````csharp
// Bad
public enum Direction : long
{
    North = 1,
    East = 2,
    South = 3,
    West = 4
}
 
// Good
public enum Direction
{
    North,
    East,
    South,
    West
}
````
> Why: can create confusion when relying on actual types and values.

## Enum Suffix

<mark>Do not</mark> suffix enum names with Enum

````csharp
// Bad
public enum CoinEnum
{
    Penny,
    Nickel,
    Dime,
    Quarter,
    Dollar
}
 
// Good
public enum Coin
{
    Penny,
    Nickel,
    Dime,
    Quarter,
    Dollar
}
````
> Why: consistent with the Microsoft's .NET Core, and consistent with prior rule of no type indicators in identifiers.


## License

[MIT License](http://BeltonMenete.mit-license.org/) © Belton Menete

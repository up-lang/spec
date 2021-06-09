# Defining objects

## Namespaces

Generally one namespace is used per program, however this may not be the case as it can be broken down into smaller chunks - for example `MyApp:Core`, `MyApp:Cli`, and `MyApp:Gui` as three separate namespaces.

They are defined with the `namespace` keyword, then the name of it, then opening a scope.

If the namespace declaration only contains a single class or enum then the braces can be ommitted.

### Example

```up
namespace MyAwesomeNamespace
{
	~ stuff goes in here
}

~ if a namespace only has one class / enum it needs no scope defining
namespace AnotherAwesomeNamespace class MyAwesomeClass {}
```

## Classes

Namespaces lead nicely onto classes: these contain variables, methods, etc. These are usually used for data types, and for smaller components of a program.

They are defined with the `class` keyword, then the name of it, then opening a scope.

Unlike namespaces, the scope can never be ommitted.

### Example

```up
class MyAmazingClass
{
	~ stuff goes in here
}
```

## Enums

Enums are used to store a list of possible values. They are often used to store states etc.

They are defined with the `enum` keyword, then the name of it, then opening a scope.

Unlike classes and namespaces, they do not contain other objects, they simply contain the names of the available options, separated by `;`.

These options are later available via `EnumName.OptionName`.

### Example

```up
enum Vehicles
{
	Car; Bike; Bus;
	Van; Train; Plane
}
```

## Class members

Class members are declared with their accessibility, then name, then type.

### Example

```up
class Person
{
	public  Name String;
	private age  Int32;
}
```

## Methods and functions

Methods and functions (private methods) are declared with their accessibility, then name, then (in parentheses) the parameters in the format name then type, then the return type (or `void`), then finally a scope.

### Example

```up
class Door
{
	private open Bit;
	
	public Open()  void { open = true;  }
	public Close() void { open = false; }
	
	public IsOpen()            Bit  { return open; }
	public SetOpen(isOpen Bit) void { open = isOpen; }
}
```

## Local variables

Local variables are defined with `var` then their name, then type. They can have a value assigned inline.

### Example

```up
var myInt    Int32;
var myString String = "Hello there!";
```


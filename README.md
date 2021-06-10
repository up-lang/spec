# UP

A programming language made for fun by [Cain Atkinson](https://github.com/yellowsink).

Its syntax is inspired by C# with some other random ideas thrown in.

## Basic Concepts

The typing and organisation in UP are heavily influenced by .NET's type system, with some differences of course.

Nothing is nullable by default, however a variable can be made nullable by prepending the type name with `?`.

`namespace`s contain `class`es - classes are used to define types, and are subject to UP's type system.

Namespaces can also contain `struct`s - these are not subject to UP's type system, are dealt with by the interpreter / compiler, and are used exclusively in the [*language essentials*](https://github.com/up-lang/spec/blob/master/language_essentials.md).

## Entrypoints

The acceptable entry-point for your program is `namespace.Program.Main()`, which returns `void`, is `public`, and can optionally take a type convertible to `upcore.primitivearray<upcore:types.string>`, in most cases this is `stdlib.Array<stdlib.String>`.

The args array does not contain `argv[0]` - by convention the command used to execute a program on the command line.

### Example

```up
with stdlib;

namespace MyApp class Program
{
	public Main(args Array<String>) void
	{
		Console.WriteLine(args[0]);
	}
}
```

### Expected output

```
$ up MyApp/Program.up test
test
```

## Other important information

The suggested file extension is `.up`

### Naming convention

| Item                      | Convention                 | Example                       |
| ------------------------- | -------------------------- | ----------------------------- |
| Namespace                 | Pascal case                | `MyAwesomeNamespace`          |
| Class                     | Pascal case                | `MyAwesomeClass`              |
| Public class member       | Pascal case                | `MyAwesomePublicClassMember`  |
| Enum option               | Pascal case                | `MyAwesomePublicEnumOption`   |
| Private class member      | Camel case                 | `myAwesomePrivateClassMember` |
| Local variables           | Camel case                 | `myLocalVariable`             |
| Method (public)           | Snake case                 | `my_awesome_method`           |
| Function (private method) | Underscore then snake case | `_my_awesome_function`        |

These naming conventions are not enforced by the reference interpreter but are recommended as they help tell things apart easily. The only exception to these rules within UP's standard set of included objects is `upcore` ([language essentials](https://github.com/up-lang/spec/blob/master/language_essentials.md)).
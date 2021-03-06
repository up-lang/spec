# Syntax

## Defining objects

See [defining objects](https://github.com/up-lang/spec/blob/master/syntax/defining_objects.md).

## Literals

See [literals](https://github.com/up-lang/spec/blob/master/syntax/literals.md).

## Operators

### Arithmetic

See [arithmetic](https://github.com/up-lang/spec/blob/master/syntax/arithmetic.md).

### Comparisons

See [comparison](https://github.com/up-lang/spec/blob/master/syntax/comparison.md).

### Binary & Logic

See [logic](https://github.com/up-lang/spec/blob/master/syntax/logic.md).

### Defining operators for your types

Add a function to your class, though instead of specifying an accessibility modifier, use `operator`, and then use the following names for redefining operators.

| `+`     | `-`     | `*`     | `/`     | `//`       | `%`     |
| ------- | ------- | ------- | ------- | ---------- | ------- |
| `add()` | `sub()` | `mul()` | `div()` | `intdiv()` | `mod()` |

| `|`    | `||`     | `|||`   | `&`     | `&&`      | `!`     | `===`     | `==`   |
| ------ | -------- | ------- | ------- | --------- | ------- | --------- | ------ |
| `or()` | `orSc()` | `xor()` | `and()` | `andSc()` | `not()` | `eqBin()` | `eq()` |

#### Example

```up
with stdlib;

namespace MyApp
{
	class CustomClass
	{
		public FirstInt  Int32;
		public SecondInt Int32;
		
		operator add(first CustomClass, second CustomClass) CustomClass
		{
			var new CustomClass = new CustomClass();
			new.FirstInt = first.FirstInt + second.FirstInt;
			new.SecondInt = first.SecondInt + second.SecondInt;
			return new;
		}
	}
	
	class Program
	{
		public Main() void
		{
			var first CustomClass = new CustomClass();
			first.FirstInt = 6;
			first.SecondInt = 7;
			var second CustomClass = new CustomClass();
			second.FirstInt = 9;
			second.SecondInt = -2;
			
			var final CustomClass = first + second; ~ uses our custom operator!
			~ final.FirstInt = 15
			~ final.SecondInt = 5
		}
	}
}
```

## Misc

### Instantiating types

Create a class with `new Type()`, which calls a constructor defined on the type using `constructor` in place of an accessibility modifier. Structs and classes both have a default constructor with no arguments that uses all default values, though this is disabled once you define a custom constructor.

### Whitespace

UP ignores whitespace. The largest and only unit of whitespace that UP cares about is a single space ` `, which is used often for things. One of the first steps of parsing UP code would include collapsing all whitespace down to single spaces.

### Comments

**Line comments** are declared with a tilde character: `~`. The comment lasts for the entire line, and will take priority over block comments starts, but will be ignored inside them. This is best shown with an example so here:

```up
~ ~~~ This will not make a block comment due to the line comment

some code goes here

~ ~~~ This does not start a new block comment due to the line comment,
    ~ however if the previous one did not have a line comment,
    ~ then this would not close it, as the line comment is inside the block comment and therefore ignored
```

**Block comments** are declared with a triple tilde: `~~~`. This will start a block comment, or if one was already active end it. Block comments ignore newlines and *just keep going*.

### Scopes

Scopes are used for lots of things. They are used to declare the body of functions and methods, and contents of a namespace, class, or enum. They can also be defined arbritrarily. They are declared using curly braces `{}`.

### Indexing

Indexing uses square brackets `[]`. Indexing is available for any type with the `index()` private method. It can take any single parameter of any type and return any type of value.

### Accessing objects

Accessing the items in a namespace or accessing a sub-namespace is done with the `:` character. Accessing members of a class or options in an enum is done with the `.` character.

Importing a namespace for use is done with the `with` keyword, which makes its members available for the remainder of that scope.

### True and False

`true` and `false` are keywords that simply produce a `upcore:types.bit` with `1` or `0`.

This is almost always instantly converted to `stdlib.Bit`.

### Discard

If you ever wish you could compute a value and then simply ignore it (why I don't know but okay), then set the value of `_` to it.

`_` is available everywhere and cannot be read from.

### Compound assignment

Any logical / binary or arithmetic operator can be followed by a `=` to place the result back into the left operand.

Note that this does help create a very confusing situation of 4 different but similar looking operators:

| Operator | Purpose                                                      |
| -------- | ------------------------------------------------------------ |
| `=`      | Assign a value to a variable or member                       |
| `==`     | Check if two objects are equal                               |
| `===`    | Binary equal - see [logic](https://github.com/up-lang/spec/blob/master/syntax/logic.md#-2) |
| `====`   | `a ==== b` is equivalent to `a = a === b`. Yep. It's confusing. |

```up
var a Int = 5;
a += 4; ~ 9
a *= 3; ~ 27
```

### Increment and Decrement

`++` and `--` increment and decrement a value by one.

Appending them returns their value and then modifies them, prepending modifies them and then returns them.

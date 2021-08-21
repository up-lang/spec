# Literals

## Integer literals

Any numbers in code are parsed as integers, using `upcore:types.si32` by default, but switching to `si64` then `sibig` if required.

In most cases this is instantly converted to a `stdlib.Int32`.

## Decimal literals

Any numbers in code containing a decimal place `.` are parsed as floats, using `upcore:types.f64`.

In most cases this is instantly converted to a `stdlib.Float64`.

## Text literals

Character literals are defined with single quotations `''` containing a single character. They are parsed using `upcore:types.uchar`.

In most cases this is instantly converted to a `stdlib.Char`.

String literals are defined with double quotations `""` containing a string. They are parsed using `upcore:types.string`.

In most cases this is instantly converted to a `stdlib.String`.

### Example

```up
with stdlib;
var myChar Char = 'a'; ~ three things are actually happening here:
                       ~ a upcore:types.uchar is created with a as the value,
                       ~ then it is converted to a stdlib.Char,
                       ~ and finally is assigned to the myChar variable

var myString String = "Hello, World!"; ~ three things are also happening here:
                                       ~ a upcore:types.string is created for Hello World!,
                                       ~ then it is converted to a stdlib.String
                                       ~ and finally is assigned to the myString variable
```

## Binary and hexadecimal literals

Binary literals are created by starting with `0b`, and then following up with a series of `1`s and `0`s, automatically picking the smallest value that can hold it from `upcore:types.byte` all the way up to `upcore:types.sibig`.

Hexadecimal literals are created by starting with `0x`, and then following up with a series of hex numbers (0-9 and a-f), automatically picking the smallest value that can hold it just like binary literals.

### Example

```up
with stdlib;
var myBinaryValue Byte = 0b10010010; ~ equal to 146 (if my mental arithmetic holds up!)
var myHexValue    Byte = 0xA3;       ~ equal to 10100011, or 163 (again, ^^^ this)
```

## Arrays

Array literals follow the following syntax: `new []` then a type then `{}` either containing nothing, or a comma separated list of expressions:

```up
with stdlib;
var myEmptyArray  = new []String{};
var myCoolArray   = new []?String{ "hello", null, "world" };
var arrayOfArrays = new [][]String
{
  new []String{ "Hello, ", "World!" },
  new []String{ "Another ", "array" }
};
```

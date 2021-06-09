# [Language essentials](https://github.com/up-lang/spec/blob/master/language_essentials.md) => [Basic Types](https://github.com/up-lang/spec/tree/master/essentials/basic_types) => Binary & Boolean

**Note about booleans**: In UP, booleans are represented using the `bit` type, but this is functionally identical to a `bool` in other languages.

## `bit`

`bit` represents a single bit. In UP a `bit` can either be used with arithmetic operators with other numbers, as it technically just stores `1` and `0`, though due to the way binary logic operators are implemented this works just like boolean logic for `bit`s.

## `byte`

`byte` is as basic as it gets - a single byte to do with as you please. It can be used like any other integer, storing any number from `0` - `255`, or can be used for bit manipulation - the interpreter / compiler is expected to provide support for indexing on this type: using the `[]` operator can fetch or set a single `bit` easily.

### Example of indexed bit manipulation

```up
with upcore:types;

var exampleByte byte = 0b10010011;
var fourthBit   bit  = exampleByte[3]; ~ 1
~ set the fifth bit, which is 0, to a 1
exampleByte[4] = 1; ~ new value: 10011011
```

## `sbyte`

`sbyte` is essentially a byte, except when used for arithmetic - where the first bit is a sign bit, allowing storing any value from `-128` to `127`.

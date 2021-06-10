# [Language essentials](https://github.com/up-lang/spec/blob/master/language_essentials.md) => [Basic Types](https://github.com/up-lang/spec/tree/master/essentials/basic_types) => Binary & Boolean

**Note about booleans**: In UP, booleans are represented using the `bit` type, but this is functionally identical to a `bool` in other languages.

## `bit`

`bit` represents a single bit. In UP a `bit` can either be used with arithmetic operators with other numbers, as it technically just stores `1` and `0`, though due to the way binary logic operators are implemented this works just like boolean logic for `bit`s.

## `byte`

`byte` is as basic as it gets - a single byte to do with as you please. It can be used like any other integer, storing any number from `0` - `255`.

## `sbyte`

`sbyte` is essentially a byte, except when used for arithmetic - where the first bit is a sign bit, allowing storing any value from `-128` to `127`.

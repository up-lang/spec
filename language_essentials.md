# Language Essentials

The interpreter or compiler is expected to provide a namespace called `upcore` which contains the essential basics on which everything, including the standard library is built.

Note that is it recommended to use the types provided by the standard library, however.

The items included here are purposefully kept to a minimum as the main bulk of provided tools should be provided by the standard library. The existence of `upcore` is just so that the standard library isn't magical and tied to the interpreter - you can theoretically write your own replacement for it entirely in UP.

## Included items

### Basic data types

This should be exposed under the `types` class.

- [binary & boolean](https://github.com/up-lang/spec/blob/master/essentials/basic_types/binary.md)
- [integers](https://github.com/up-lang/spec/blob/master/essentials/basic_types/integers.md)
- [decimals](https://github.com/up-lang/spec/blob/master/essentials/basic_types/decimal.md)
- [text](https://github.com/up-lang/spec/blob/master/essentials/basic_types/text.md)
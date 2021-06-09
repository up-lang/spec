# [Language essentials](https://github.com/up-lang/spec/blob/master/language_essentials.md) => [Basic Types](https://github.com/up-lang/spec/tree/master/essentials/basic_types) => Decimals

## `f16`

`f16` is a 16-bit floating point number. It can represent any number between `-65_504` - `65_504`, however it can store the decimal part of a number too. As the number moves away from 0, more bits are used up and therefore less precision is available for the decimal part of the number.

## `f32`

`f32` is a 32-bit floating point number. It can represent any number in the range `-3.402823e38` - `3.402823e38`. It is useful for values that are often either extremely small or large, AND where some inaccuracy is acceptable.

### `f64`

`f64` is a 64-bit floating point number. It can represent any number in the range `-1.79769313486232e308` - `1.79769313486232e308`. It is the recommended type for storing non integer values. It is useful for values that are often incredibly small or large and where accuracy is not crucial.

Just like with `si64` and `ui64`, even if the target platform is 32-bit, the interpreter or compiler is still expected to provide this type.
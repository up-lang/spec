# [Language essentials](https://github.com/up-lang/spec/blob/master/language_essentials.md) => [Basic Types](https://github.com/up-lang/spec/tree/master/essentials/basic_types) => Integers

## General information

Integers are `struct` values - they are provided by the interpreter / compiler and are not defined using UP code.

When defining integer literals in UP, it is acceptable to add place value separators. The separator accepted is `_`.

For 8-bit types you want to be looking at the docs for [binary types](https://github.com/up-lang/spec/blob/master/essentials/basic_types/binary.md).

## Unsigned

###  `ui16`

`ui16` is a 16-bit unsigned integer. It can store values in the range `0` - `65_535`.

### `ui32`

`ui32` is a 32-bit unsigned integer. It can store values in the range `0` - `4_294_967_295`.

### `ui64`

`ui64` is a 64-bit unsigned integer. It can store values in the range `0` - `18_446_744_073_709_551_615`.

Even if the target platform is 32-bit the interpreter / compiler is expected to provide this type anyway, using two 32-bit values to emulate 64-bit integers.

### `uibig`

`uibig` is an unsigned bigint type - it can store every integer value greater than 0. Note that bigint math is computationally expensive (this isn't exclusive to UP by the way!).

## Signed

### `si16`

`si16` is a 16-bit signed integer. It can store values in the range `-32_768` - `32_767`.

### `si32`

`si32` is a 32-bit signed integer. It can store values in the range `-2_147_483_648` - `2_147_483_647`.

### `si64`

`si64` is a 64-bit signed integer. It can store values in the range `−9_223_372_036_854_775_808` - `9_223_372_036_854_775_807`.

### `sibig`

`sibig` is a signed bigint type - it can store literally any integer value for the VERY rare case where apparently you're dealing with numbers larger than 9 quintillion in `si64` (18 quintillion for `ui64`). Note that bigint math is computationally expensive (this isn't exclusive to UP by the way!).
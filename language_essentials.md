# Language Essentials

The interpreter or compiler is expected to provide a namespace called `upcore` which contains the essential basics on which everything, including the standard library is built. This namespace exists "magically" - it doesn't technically exist as any UP code you'd import, but the interpreter / compiler makes it work to give this language the raw basics to do things.

**NOTE: as of now there are some types that could be implemented in UP - for example non-`byte` int types, but for simplicity they are provided by `upcore` at least for now**

Note that is it recommended to use the types provided by the standard library, however.

The items included here are purposefully kept to a minimum as the main bulk of provided tools should be provided by the standard library. The existence of `upcore` is just so that the standard library isn't "magical" like `upcore` is - I'd rather have as little as possible be done this way, and also it means you can theoretically write your own replacement for `stdlib` entirely in UP if you wished.

## Included items

### Basic data types

This should be exposed under the `upcore:types` namespace.

- [binary & boolean](https://github.com/up-lang/spec/blob/master/essentials/basic_types/binary.md)
- [integers](https://github.com/up-lang/spec/blob/master/essentials/basic_types/integers.md)
- [decimals](https://github.com/up-lang/spec/blob/master/essentials/basic_types/decimals.md)
- [text](https://github.com/up-lang/spec/blob/master/essentials/basic_types/text.md)

### [STDIO](https://github.com/up-lang/spec/blob/master/essentials/stdio.md)

This should be exposed under the `upcore.stdio` class.

### Filesystem

This should be exposed under the `upcore:filesystem` namespace.

- [file](https://github.com/up-lang/spec/blob/master/essentials/filesystem/file.md)
- [directory](https://github.com/up-lang/spec/blob/master/essentials/filesystem/directory.md)
- [fs_object](https://github.com/up-lang/spec/blob/master/essentials/filesystem/fs_object.md)
- [io](https://github.com/up-lang/spec/blob/master/essentials/filesystem/io.md)

### Misc

- `upcore.primitivearray<T>` is a generic array that is VERY primitive. It can only be read by querying indexes and cannot be wriiten to from inside of UP. It is used purely for `upcore` functions that need to return multiple items.

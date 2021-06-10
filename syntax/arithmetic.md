# Arithmetic

## `+`

`+` will add two numbers, or concatenate two strings.

### Example

```up
_ = 5 + 6;                ~ 11
_ = "Hello, " + "World!"; ~ "Hello, World!"
```

## `-`

`-` will subtract two numbers.

### Example

```up
_ = 11 - 4; ~ 7
_ = 4 - 6; ~ -2
```

## `*`

`*` will multiply two numbers, or repeat a string a set number of times.

### Example

```up
_ = 5 * 3;      ~ 15
_ = "test" * 4; ~ "testtesttesttest"
```

## `/`

`/` will divide two numbers, returning an `upcore:types.f64`.

### Example

```up
_ = 5 / 3; ~ 1.66666666666...
_ = 3 / 6; ~ 0.5
```

## `//`

`//` will divide two numbers, returning an `upcore:types.si32`.

### Example

```up
_ = 4 / 2; ~ 2
_ = 6 / 5; ~ 1
```

## `%`

`%` will compute the modulo / MOD of two numbers, returning an `upcore:types.si32`.

### Example

```up
_ = 4 % 2; ~ 0
_ = 6 % 5; ~ 1
```
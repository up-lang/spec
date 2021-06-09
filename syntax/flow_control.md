# Flow control

## `if`

The `if` statement takes a `upcore:types.bit` in parenthesis and if the value is `1`, runs the code in the following scope.

### Example

```up
if (5 > 6) ~ false
{
	~ code here won't be run
}

if (5 != 9) ~ true
{
	~ code here will be run
}
```

## `else`

The else statement must be placed directly after closing the scope of an `if` or an `elseif`, and will be run only as long as the `if `statement contents are not run.

### Example

```up
if (5 > 6) ~ false
{
	~ code here won't be run
}
else
{
	~ code here will be run
}
```

## `elseif`

Only runs if the above `if` or `elseif` does not. Only runs if the bit passed is `1`. Can be chained together nicely.

### Example

```up
if (6 > 5) ~ true
{
	~ code here will be run
}
elseif (5 != 9) ~ true
{
	~ code here won't be run
}
else
{
	~ code here also won't be run
}
```

## `for`

`for` will optionally create a variable, then check the value of a bit each time to determine whether to continue, then perform a single statement, usually affecting that variable, each loop. It runs the contents of its scope until the bit is `0`.

### Example

```up
var a Int = 2;
for (var i Int = 0; i < 5; i++)
{
	a += i;
}

~~~
| i | a  |
|---|----|
| 0 |  2 |
| 1 |  3 |
| 2 |  5 |
| 3 |  8 |
| 4 | 12 |
|---|----|
then at 5, i < 5 no longer evaluates true and the loop exits, leaving a = 12
~~~
```

## `while`

A `while` loop simply repeats the contents of its scope until the bit passed to it is no longer `1`.

### Example

```up
var a Int = 2;
while (a < 5) { a += 2; }
~~~
- first loop:  4
- second loop: 6
- loop breaks leaving 6
~~~
```

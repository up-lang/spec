# STDIO

`upcore.stdio` provides functions for communicating with the input and output of the program. When ran interactively, this is console input and output, when used in a pipe (example with bash: `cat input.txt | up Program.up > output.txt`), this is the items passed to and sent from the program.

## `stdout(output upcore:types.string)`

The `stdout` function outputs to the standard out stream.

### Example

UP code:

```up
with upcore;
stdio.stdout("Hello, World!");
```

Console output:

```
Hello, World!
```

## `stdin_char() upcore:types.uchar`

The `stdin_char` function reads a single character from stdin.

### Example

UP code:

```up
with upcore;
var a uchar = stdio.stdin_char();
var b uchar = stdio.stdin_char();
~ a = 'f' and b = 'g'
```

Console input:

```
fg
```

## `stdin_line() upcore:types.string`

The `stdin_line` function reads a single line from stdin.

### Example

UP code:

```up
with upcore;
var a string = stdio.stdin_line();
var b string = stdio.stdin_line();
var c string = a + b;
~ c = "Hello, World!"
```

Console input:

```
Hello,
 World!
```

## `stderr(output upcore:types.string)`

The `stderr` function outputs to the standard error stream.

This function is to be used for errors, where it is more appropriate than `stdout`.

### Example

UP code:

```up
with upcore;
stdio.stderr("Hello, World!");
```

Console output (stderr):

```
Hello, World!
```
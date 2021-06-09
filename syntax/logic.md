# Binary and logic

Any "logic" operators are actually just binary operators. When acting on bits they act as logic operators.

## `!`

This is the logical NOT - it flips every single bit in the number.

### Example:

```up
_ = !0b10111011; ~ 01000100
_ = !true; ~ false
```

## `&` / `&&`

This is the logical AND - for each bit in both numbers, AND is performed and a number with the results returned.

This operator will evaluate both bits every time, however the short circuiting `&&` won't bother reading the second value if the first is `0` as the result is guaranteed to be `0`. This should be considered if you are comparing two `Bit` objects returned from a function with side effects.

### Example

```up
_ = 0b101110 && 0b100101; ~ 100100 (yes I know this is a weird number of bits but that's irrelevant)
_ = true && false; ~ false
_ = true && true;  ~ true
```

### A neat trick

If you have a binary number, say `10010110`, and you wished to set a bit to `0` (though this should be possible via byte indexing), then you can generate a byte with every bit except the one you wish to set `0` as `1` and perform AND with it. This byte can be created with a binary shift and NOT.

```up
var exampleByte Byte = 0b10010110;
exampleByte        &&= !(1 << 4);

~ exampleByte now contains 10000110, with the 5th bit from the right set to 0
```

## `|` / `||`

This is the logical OR - for each bit in both numbers, OR is performed and a number with the results returned.

This operator will evaluate both bits every time, however the short circuiting `||` won't bother reading the second value if the first is `0` as the result is guaranteed to be `0`. This should be considered if you are comparing two `Bit` objects returned from a function with side effects.

### Example

```up
_ = 0b00110100 || 0b11001101; ~ 11111101
_ = true  || false; ~ true
_ = false || false; ~ false
```

### A neat trick

If you have a binary number, say `10010110`, and you wished to set a bit to `1` (though this should be possible via byte indexing), then you can generate a byte with the bit you wish to set as `1` and perform OR with it. This byte can be created with a binary shift.

```up
var exampleByte Byte = 0b10010110;
exampleByte        &&= 1 << 5;

~ exampleByte now contains 10110110, with the 6th bit from the right set to 0
```

## `|||`

This is the logical XOR - for each bit in both numbers, XOR is performed and a number with the results returned.

This operator will evaluate both bits every time.

### Example

```up
_ = 0b00110100 ||| 0b10101101; ~ 10011001
_ = true  ||| false; ~ true
_ = false ||| false; ~ false
_ = true  ||| true;  ~ false
```

## `===`

**NOT TO BE CONFUSED WITH `==`** (though for `Bit` it is technically interchangeable)

This operator checks if the bits in both numbers are equal and returns the results per bit

### Example

```up
_ = 0b01110001 === 0b01111100; ~ 11110010
```




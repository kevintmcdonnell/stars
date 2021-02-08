This debugger is loosely based on the GDB debugger.

# How to run:

### Command line:
* see **README.md**

### Changing settings:
* navigate to **settings.py** and set the debug field to `True`
* now all programs will automatically run in debug mode

# Commands:
* `[h]elp`             Prints the usage for the debugger
* `[b]reak <filename> <line_no>`        Adds a breakpoint at line `<line_no>` in file `<filename>`
* `[n]ext`              Continues execution until the next line of code
* `[c]ontinue`          Continues execution until the next breakpoint or the end of execution
* `[i]nfo b`            Prints all the breakpoints
* `[p]rint <reg> <format>`      Prints the value of register `<reg>`
* `[p]rint <flag>`      Prints the condition flag of number `<flag>`
* `[p]rint <label> <data_type> <length> <format>`     Prints the memory at the address that `<label>` points to in memory. If `data_type` is `f` or `d`, `format` is not needed.
* `[q]uit`                Terminates the program and debugger
* `[r]everse`           Takes one step back in the program

### Possible formats:
These are only relevant for data types `w`, `h`, and `b` (or registers).
*  `i`  decimal (signed)
*  `u`  decimal (unsigned)
*  `x`  hexadecimal
*  `b`  binary

These are only relevant for floating point registers.
*  `f`  float
*  `d`  double (only for even numbered registers)

### Possible data types:
*  `b`  byte
*  `h`  half word (2 bytes)
*  `w`  word (4 bytes)
*  `f`  float (4 bytes)
*  `d`  double (8 bytes)
*  `c`  character
*  `s`  string

### `print` examples:
#### Printing registers:
* Suppose the `$t0` register contains 42.
* `print $t0 i` would print `42`.
* `print $t0 x` would print `0x2A`.

#### Printing data in memory:
*  Suppose the data section contains `.byte nums: 48, 49, 50, 0`.
*  `print nums c 3` would print `0, 1, 2`.
*  `print nums b 3 x` would print `0x30 0x31 0x32`.
*  `print nums s` would print `012`.
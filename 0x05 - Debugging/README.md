# Debugging

## GDB

GDB is a debugger, is a portable debugger that runs on many Unix-like systems and works for many programming languages, including Ada, C, C++, Objective-C, Free Pascal, Fortran, Go, and partially others.

_Source: https://en.wikipedia.org/wiki/GNU_Debugger_

### Basic commands

#### Setup
```
disassemble <location>              Disassemble a specified section of memory
set disassembly-flavor <flavor>     Set the disassembly flavor to either intel or att (default)
set disassemble-next-line on        Disassemble next source line or insn when execution stops
```

#### Navigation
```
set args <args>                     Set arguments to pass to program to be debugged
r[un] <args>                        Execute the program with specified arguments
k[ill]                              Kill the running program
n[ext]i                             Single-step instruction without descending into functions
fin[ish]                            Finish current function, loop, etc.
c[ontinue]                          Continue to next breakpoint or end
up	                                Go up one context level on stack (to caller)
down	                            Go down one context level on stack (if up was used)
l[ist]	                            Show lines of code surrounding the current point
```

#### Print
```
p[rint] <location>                  Print value of variable called <location>
p[rint] *<location>                 Print what is pointed to by <location>
p/x <location>                      Print value of <location> in hex format
p[rint] <location> @ <n>            Print <n> values starting at <location>
```

#### Stacktrace
```
backtrace                           Show callstack
backtrace full                      Show callstack with local variable in each frame
frame <frame#>                      Select a specific frame
```

#### Breakpoint
```
b[reak] <location>                  Add a breakpoint to a specific location
delete <breakpoint #>               Remove a breakpoint to a specific location
i[nfo] b                            List all breakpoints
```

#### Registers
```
i[nfo] registers                    List all registers
set $<register>=<value>             Update a register value
```

_Source: https://darkdust.net/files/GDB%20Cheat%20Sheet.pdf_

## Alternative debuggers

* Hopper v4: https://www.hopperapp.com/ _(for Linux or Mac)_
* IDA: https://www.hex-rays.com/products/ida/main-differences-between-ida-editions/ _(for Windows, Linux or Mac)_
* Radare2 & Cutter: https://rada.re/n/ & https://cutter.re/ _(multi-platform)_


### Radare2

#### Basic commands

```
<command>?      Show help for the current command
aaa             Analyse the provided binary
afl             Print all functions
s <location>    Seek location
pdf             Print disassembly of the current location
VV              Enable visual mode (control graph)
db              Add a breakpoint to the current location
dc              Run the program
```

_For more detail about the visual mode: https://monosource.gitbooks.io/radare2-explorations/content/intro/visual_graphs.html_
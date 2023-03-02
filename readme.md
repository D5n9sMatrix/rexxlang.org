# welcome language rexx org
software language rexx org active IBM 

```rexx
/*
.
├── language-rexx
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   └── admin.n
│   │       ├── host
│   │       │   └── rexx.zrx
│   │       ├── ini
│   │       │   └── admin.ini
│   │       ├── lib
│   │       │   └── server.zln
│   │       ├── router
│   │       │   └── imp.zrx
│   │       ├── src
│   │       │   └── startup.zrx
│   │       ├── sys
│   │       │   └── config.sys
│   │       ├── test
│   │       │   └── admin.n
│   │       └── txt
│   │           └── zocevent.txt
│   ├── readme.md
│   ├── zocrexx.zrx
│   ├── zocrouter.zrx
│   ├── zocserver.zrx
│   └── zocworker.zrx
├── license
├── readme.md
├── rexx-dev
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── devtools.zrx
│   │       │   ├── macrexx.zrx
│   │       │   └── toolrun.zrx
│   │       ├── lib
│   │       │   └── dev.zrx
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
├── rexx-icms
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── icms.zrx
│   │       │   ├── ppi.zrx
│   │       │   └── stf.zrx
│   │       ├── lib
│   │       │   └── icms.zcfg
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
├── rexx-ipca
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── abin.zrx
│   │       │   ├── ibge.zrx
│   │       │   └── ipkit.zrx
│   │       ├── lib
│   │       │   └── ir.zcfg
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
├── rexx-lcd
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── ipca.zrx
│   │       │   ├── ntn-b.zrx
│   │       │   └── tlp.zrx
│   │       ├── lib
│   │       │   └── tlps.zcfg
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
├── rexx-selic
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── bc.zrx
│   │       │   ├── pis.zrx
│   │       │   └── pl.zrx
│   │       ├── lib
│   │       │   └── copom.zcfg
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
├── rexx-tool
│   ├── license
│   ├── matrix
│   │   └── gnu
│   │       ├── bin
│   │       │   ├── icms.zrx
│   │       │   ├── ppi.zrx
│   │       │   └── stf.zrx
│   │       ├── lib
│   │       │   └── icms.zcfg
│   │       └── test
│   │           └── drop.zrx
│   └── readme.md
└── rexx-types
    ├── license
    ├── matrix
    │   └── gnu
    │       ├── bin
    │       │   ├── intro.zrx
    │       │   ├── nutshell.zrx
    │       │   └── who.zrx
    │       ├── lib
    │       │   └── top.zrx
    │       └── test
    │           └── drop.zrx
    └── readme.md
*/    
```

## Language Elements

Rexx consists of only two dozen instructions, augmented by the power of some 70 built-in functions.
Figure 2-1 below pictorially represents the key components of Rexx. It shows that the instructions and
functions together compose the core of the language, which is then surrounded and augmented by other
features. A lot of what the first section of this book is about is introducing the various Rexx instructions
and functions.
Elements of Rexx
Operators
Arithmetic
Comparison
Logical
String
2 dozen Instructions
70 Built-in
Functions
Other language components & features
Figure 2-1
Of course, this book also provides a language reference section in the appendices, covering these and
other aspects of the language. For example, Appendix B is a reference to all standard Rexx instructions,
while Appendix C provides the reference to standard functions.
24Language Basics
The first sample program illustrated the use of the instructions say, pull, and if. Rexx instructions are
typically followed by one or more operands, or elements upon which they operate. For example, say is
followed by one or more elements it writes to the display screen. The pull instruction is followed by a
list of the data elements it reads.
The sample script illustrated one function, random. Functions are always immediately followed by
parentheses, usually containing function arguments, or inputs to the function. If there are no arguments,
the function must be immediately followed by empty parentheses () . Rexx functions always return a
single result, which is then substituted into the expression directly in place of the function call. For
example, the random number returned by the random function is actually substituted into the statement
that follows, on the right-hand side of the equals sign, then assigned to the variable the_number:

```rexx
the_number = random(1,10)
```
Variables are named storage locations that can contain values. They do not need to be declared or defined
in advance, but are rather created when they are first referenced. You can declare or define all variables
used in a program at the beginning of the script, but Rexx does not require this. Some programmers like
to declare all variables at the top of their programs, for clarity, but Rexx leaves the decision whether or
not to do this up to you.
All variables in Rexx are internally stored as variable-length strings. The interpreter manages their
lengths and data types. Rexx variables are “typeless” in that their contents define their usage. If strings
contain digits, you can apply numeric operations to them. If they do not contain strings representing
numeric values, numeric operations don’t make sense and will fail if attempted. Rexx is simpler than
other programming languages in that developers do not have to concern themselves with data types.
Variable names are sometimes referred to as symbols. They may be composed of letters, digits, and charac-
ters such as . ! ? _ . A variable name you create must not begin with a digit or period. A simple variable
name does not include a period. A variable name that includes a period is called a compound variable and
represents an array or table. Arrays will be covered in Chapter 4. They consist of groups of similar data
elements, typically processed as a group.
If all Rexx variables are typeless, how does one create a numeric value? Just place a string representing a
valid number into a Rexx variable. Here are assignment statements that achieve this:

```rexx
whole_number_example = 15
decimal_example = 14.2
negative_number = -21.2
exponential_notation_example  = 14E+12
```

A number in Rexx is simply a string of one or more digits with one optional decimal point anywhere in
the string. Numbers may optionally be preceded by their sign, indicating a postive or a negative num-
ber. Numbers may be represented very flexibly by almost any common notation. Exponential numbers
may be represented in either engineering or scientific notation (the default is scientific). The following
table shows examples of numbers in Rexx.

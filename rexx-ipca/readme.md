# welcome rexx ipca
software rexx ipca active IBM Rexx Language

```rexx
/*
.
├── license
├── matrix
│   └── gnu
│       ├── bin
│       │   ├── abin.zrx
│       │   ├── ibge.zrx
│       │   └── ipkit.zrx
│       ├── lib
│       │   └── ir.zcfg
│       └── test
│           └── drop.zrx
└── readme.md
*/
```

Character strings are any set of characters occurring between a matched set of either single quotation
marks (‘) or double quotation marks (“).
What if you want to encode a quote within a literal? In other words, what do you do when you need to
encode a single or double quote as part of the character string itself? To put a single quotation mark
within the literal, enclose the literal with double quotation marks:

```rexx
say "I'm thinking of number between 1 and 10. What is it?"
```
To encode double quotation marks within the string, enclose the literal with single quotation marks:

```rexx
say 'I am "thinking" of number between 1 and 10. What is it?'
```
Rexx is a free-format language. The spacing is up to you. Insert (or delete) blank lines for readability, and
leave as much or as little space between instructions and their operands as you like. Rexx leaves the cod-
ing style up to you as much as a programming language possibly can.
For example, here’s yet another way to encode the if statement:

```rexx
IF the_number = the_guess THEN
ELSE
SAY "You guessed it!"
SAY "Sorry, my number was: " the_number
```
About the only situation in which spacing is not the programmer’s option is when encoding a Rexx func-
tion. A function is a built-in routine Rexx provides as part of the language; you also may write your own
functions. This program invokes the built-in function random to generate a random number between 1
and 10 (inclusive). The parenthesis containing the function argument(s) must immediately follow the
function name without any intervening space. If the function has no arguments, code it like this:

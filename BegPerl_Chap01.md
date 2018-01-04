# Chap01
## Perl as a programming language
1. Machine codes are for computers, while source code for humans. 
2. "Byte-compiled" languages Perl and Java.
3. Perl compiler: translate source codes into native machine ones, and run the latter.
4. Bytecode: used in a "virtual machine"-pretended program, source code -(compiler)- bytecode -(interpreter)- machine code.
So Perl is strictly neither a compiled language nor interpreted one.
5. CPAN (the Comprehensive Perl Archive Network): http://www.perl.com/CPAN/
6. Perl's motto is _"There is more than one way to do it"_.
7. Version number: x.y.z. Cases when z is more than 0 are maintenance releases issued to fix overwhelming bugs. Odd ys are on  development track between stable ones.
8. Patch pumpkin holder (Pumpking): a quality controller which coordinates releases.
9. Topaz project: an attempt to rewrite the entirety of Perl in C++.

## Hello World
First line must be:  
**#! usr/bin/env perl -w**  
(Or Linux: **#! usr/bin/perl -w**)  
#! tells how the file should be run. Use flag -w to turn on additional warning reporting.  

For Perl 5.6.x and higher:  
**#! usr/bin/env perl  
use warning;**  
  
## Program structure
10. **Keywords** come in several classes called **functions** (_"verbs"_).
11. **Statements** (_"sentences"_): end with a semicolon "**;**".
12. Statement **blocks** (_"paragraphs"_): surrounded with braces "**{...}**". (Internal indentation allowed.)
13. **Pass** multiple **arguments** to a function. Limit them with brackets "**()**".

## Character set
14. ASCII: consists of 1 Octet (Byte) = 8 bit (thus 2^8 = 256, running from 0 to 255).
15. (**Perl 5.6+**) Unicode: UTF8 for 2 Octet (Byte) = 16 bit (thus 2^(2*8) = 65536, running from 0(0000) to 65535(FFFF)).

## Common escape sequences
\t \- tab  
\n \- newline (start a new line)  
\b \- backspace (back up one character)  
\a \- alarm (ring system bell)  
\x{1F18} \- hexadicimal (Unicode character)  

## White space
Free for tabs, spaces and new lines. Very flexible.  

## Number systems
Binary numbers start with **0b**. (e.g. 0b11111111, gives decimal 255)  
Octal numbers start with **0**. (e.g. 01101, gives decimal 577)  
Hexadicimal numbers start with **0x**. (e.g. 0xBEEF, gives decimal 48879)  

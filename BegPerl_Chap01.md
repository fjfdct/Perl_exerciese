# Chap01
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
**#! usr/bin/env perl -w**
(Or Linux: #! usr/bin/perl -w)
#! tells how the file should be run. Use flag -w to turn on additional warning reporting.

For Perl 5.6.x and higher
**#! usr/bin/env perl
use warning;**

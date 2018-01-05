# Chap02 Working with Simple Values

## Scalar literal constant: numbers 
1. Number systems: use **oct("\*")** to convert anyone below into decimal.
- Binary numbers start with **0b**. (e.g. 0b11111111, gives decimal 255)  
- Octal numbers start with **0**. (e.g. 01101, gives decimal 577)  
- Hexadicimal numbers start with **0x**. (e.g. hex("0xBEEF") gives decimal 48879)  
2. Large integers can be split up with underscore **\"_\"** instead of commas, for example, print 250_000_000, "/n".
3. Bareword: a series of characters outside of a string that Perl doesn't recognize.  

## Scalar literal constant: strings
4. Processing interpolation and delimiters (quote-like operator):
- Single-quoted (not interpolated) or q//, q||, q(), q(), etc.: no processing is done within, except backslash \\\ or \\'.  
- Double-quoted (interpolated) or qq//, qq||, qq(), qq(), etc.: variable names inside are replaced by their contents.  
5. **Backwhacking**: operation of escaping, using a backslash to turn off any special effect a character may have.  
  
e.g.1  
#! usr/bin/env perl -w  
use warnings;  
print "C:\\WINNT\\Profiles\\\n.";  
**(\n needs a separate double-quotes to make it interpolate.)**  
print 'C:\WINNT\Profiles\ ', "\n";  
**(Do not leave off the white space! Otherwise Perl will treat it as backslash \\' and return error message saying "can not find string terminator ' anywhere before EOF(End Of File)".)**  
  
gives:  
C:\WINNT\Profiles\  
C:\WINNT\Profiles\  

e.g.2  
#! usr/bin/env perl -w  
use warnings;  
print "\'\\"Hi,\\" said Jack. \\"Have you read Slashdot today?\\"\'\n";  
print '"Stop!" He cried.', "\n";  

gives:  
'"Hi," said Jack. "Have you read Slashdot today?"'  
"Stop!" He cried.  
  
6. **Here-document**: specified large amount of string. Start with **\"<<\"** directly followed by custom label and no space between. End marker in the name of custom label is found at the beginning at a line. By default it works like a doube-quoted string. In order to make it work like a single-quoted string, surround the **label** (not the end marker!) in single quotes. Do not put a semicolon after the end marker.

e.g.3  
#! usr/bin/env perl -w  
use warnings;  
print<<'Marker';  
This is a short text for testing here-document.  
Attention: end marker should not be surrounded by single quotes or followed by a semicolon.  
**Marker**  

gives:  
This is a short text for testing here-document.  
Attention: end marker should not be surrounded by single quotes or followed by a semicolon.  

## Operator precedence
(From high to low)  
1. ->
2. \*\*
3. ! ~ \\
4. =~ !~
5. \* / % x
6. \+ \- \.
7. << >>
8. < > <= >= lt gt le ge
9. == != <=> eq ne cmp
10. &
11. | ^
12. &&
13. ||
14. .. ...
15. ?:
16. , =>
17. not
18. and
19. or xor  

## Numeric operators
1. Ordinary arithmetic precedence: high to low.
- \**\(exponentiation)
- -(unary minus)
- \*(multiplying), \\\(dividing),  %(modulo/remainder)
- +(adding), -(subtracting)  
  
e.g.4  
#! usr/bin/env perl -w  
use warnings;  
\# print (3 + 7) \* 15, "\n"; Print is itself an operator with highest precedence. This statement will get a warning and return 10.
print ((3 + 7) \* 15), "\n";  
  
gives: 150  
  
e.g.5  
#! usr/bin/env perl -w  
use warnings;  
print -2\*\*4, "\n"  
  
gives: -16
  
2. Bitwise: work from **right(LSB, Least Significant Bit) to left(MSB, Most Significant Bit)**. Can be used to dealing with low-level file access and so on. &(and), |(or), ^(exclusive or), ~(not).  
e.g.6 51(0b00110011) & 85(0b01010101) = 17(0b00010001), 204 | 85 = 221, 204 ^ 170 = 102, ~85 = 170

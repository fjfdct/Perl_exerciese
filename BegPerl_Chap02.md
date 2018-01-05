# Chap02 Working with Simple Values

## Scalar literal constant: numbers and number systems
1. Binary numbers start with **0b**. (e.g. 0b11111111, gives decimal 255)  
2. Octal numbers start with **0**. (e.g. 01101, gives decimal 577)  
3. Hexadicimal numbers start with **0x**. (e.g. 0xBEEF, gives decimal 48879)  
4. Bareword: a series of characters outside of a string that Perl doesn't recognize.  

## Scalar literal constant: strings
5. Processing interpolation and delimiters (quote-like operator):
- Single-quoted (not interpolated) or q//, q||, q(), q(), etc.: no processing is done within, except backslash \\\ or \\'.  
- Double-quoted (interpolated) or qq//, qq||, qq(), qq(), etc.: variable names inside are replaced by their contents.  
6. **Backwhacking**: operation of escaping, using a backslash to turn off any special effect a character may have.  
  
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
  
7. **Here-document**: specified large amount of string. Start with **\"<<\"** directly followed by custom label and no space between. End marker in the name of custom label is found at the beginning at a line. By default it works like a doube-quoted string. In order to make it work like a single-quoted string, surround the label in single quotes.



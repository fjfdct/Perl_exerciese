# Chap02 Working with Simple Values

## Scalar literal constant: numbers and number systems
1. Binary numbers start with **0b**. (e.g. 0b11111111, gives decimal 255)  
2. Octal numbers start with **0**. (e.g. 01101, gives decimal 577)  
3. Hexadicimal numbers start with **0x**. (e.g. 0xBEEF, gives decimal 48879)  
4. Bareword: a series of characters outside of a string that Perl doesn't recognize.  

## Scalar literal constant: strings
5. Processing interpolation:
- Single-quoted (not interpolated): no processing is done within, except backslash \\\ or \\'.  
- Double-quoted (interpolated): variable names inside are replaced by their contents.  
6. **Backwhacking**: operation of escaping, using a backslash to turn off any special effect a character may have.  

  
e.g.1  
#! usr/bin/env perl -w  
use warnings;  
print "C:\\WINNT\\Profiles\\\n.";  
print 'C:\WINNT\Profiles\ ', "\n";  
**(Do not leave off the white space! Otherwise Perl will treat it as backslash \\' and return error message saying "can not find string terminator ' anywhere before EOF".)**  
  
gives:  
C:\WINNT\Profiles\  
C:\WINNT\Profiles\  

e.g.2  
#! usr/bin/env perl -w  
use warnings;  
print "\'\\"Hi,\\" said Jack. \\"Have you read Slashshot today?\\"\'\n";  
print '"Stop!" He cried.', "\n";  

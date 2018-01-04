# Chap02 Working with Simple Values

## Scalar literal constant: numbers and number systems
1. Binary numbers start with **0b**. (e.g. 0b11111111, gives decimal 255)  
2. Octal numbers start with **0**. (e.g. 01101, gives decimal 577)  
3. Hexadicimal numbers start with **0x**. (e.g. 0xBEEF, gives decimal 48879)  

## Scalar literal constant: strings
4. Processing interpolation:
- Single-quoted (not interpolated): no processing is done within, except backslash \\\ or \\'.  
- Double-quoted (interpolated): variable names inside are replaced by their contents.  
5. **Backwhacking**: operation of escaping, using a backslash to turn off any special effect a character may have.  
  
e.g.  
#! usr/bin/env perl -w  
use warnings;  
print "C:\\WINNT\\Profiles\\\n.";
print 'C:\WINNT\Profiles\ ', "\n";  
  
gives
C:\WINNT\Profiles\  
C:\WINNT\Profiles\  

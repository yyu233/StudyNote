**CR** is a bytecode for carriage return. (OS: Windows, DOS)    
**LF** is a btyecode for line feed. (OS: UNIX, Mac OS, Linux)   


The concepts of line feed (LF) and carriage return (CR) are closely associated, and can be considered either separately or together. In the physical media of typewriters and printers, two axes of motion, "down" and "across", are needed to create a new line on the page. Although the design of a machine (typewriter or printer) must consider them separately, the abstract logic of software can combine them together as one event. This is why a newline in character encoding can be defined as LF and CR combined into one (commonly called CR+LF or CRLF).  
  
## Problem ##

The different newline conventions cause text files that have been transferred between systems of different types to be displayed incorrectly.

Text in files created with programs which are common on Unix-like or classic Mac OS, appear as a single long line on most programs common to MS-DOS and Microsoft Windows because these do not display a single line feed or a single carriage return as a line break.

Conversely, when viewing a file originating from a Windows computer on a Unix-like system, the extra CR may be displayed as a second line break, as ^M, or as <cr> at the end of each line.

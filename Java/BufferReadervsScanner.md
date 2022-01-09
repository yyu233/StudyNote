A BufferedReader is a simple class meant to efficiently read from the underling stream. Generally, each read request made of a Reader like a FileReader causes a corresponding read request to be made to underlying stream. Each invocation of read() or readLine() could cause bytes to be read from the file, converted into characters, and then returned, which can be very inefficient. Efficiency is improved appreciably if a Reader is warped in a BufferedReader.   

BufferedReader is synchronous while Scanner is not. BufferedReader should be used if we are working with multiple threads.    
BufferedReader has significantly larger buffer memory than Scanner.   
The Scanner has a little buffer (1KB char buffer) as opposed to the BufferedReader (8KB byte buffer), but it’s more than enough.    
BufferedReader is a bit faster as compared to scanner because scanner does parsing of input data and BufferedReader simply reads sequence of characters.    

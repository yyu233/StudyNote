According to the Java documentation, String.valueOf() returns:

if the argument is null, then a string equal to "null"; otherwise, the value of obj.toString() is returned.

So there shouldn't really be a difference except for an additional method invocation.

Also, in the case of Object#toString, if the instance is null, a NullPointerException will be thrown, so arguably, it's less safe.

public static void main(String args[]) {  
    String str = null;
    System.out.println(String.valueOf(str));  // This will print a String equal to "null"        
    System.out.println(str.toString()); // This will throw a NullPointerException
} 

1. It is a final class. We cannot extend it. 
2. Class objects are contructed automatically by JVM
3. No contructor. 
4. Static method to create object ```Class a = Class.forName(String className); ``` Class name for which object is determined at run time. 
5. ``` Class a = <classname>.class ``` The class name for which Class object is created is created at the compile time.    
6. ``` Class a = object.getClass() ``` Return runtime class of object.   

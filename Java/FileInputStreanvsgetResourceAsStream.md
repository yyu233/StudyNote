When reading a file from the filesystem use a FileInputStream(File()) using relative or absolute paths.

when your program is distributed as a jar and you need to load a file that is inside that jar, you need to use getResourceAsStream(), it will search the classpath for the file, and the path is relative to the classpath.

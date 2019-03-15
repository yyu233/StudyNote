Class loaders are responsible for loading Java classes during runtime dynamically to the JVM (Java Virtual Machine). Also, they are part of the JRE (Java Runtime Environment). Hence, the JVM doesn’t need to know about the underlying files or file systems in order to run Java programs thanks to class loaders.

Also, these Java classes aren’t loaded into memory all at once, but when required by an application. This is where class loaders come into the picture. They are responsible for loading classes into memory.

**The application class loader** loads the class where the example method is contained. An application or system class loader loads our own files in the classpath.

Next, **the extension one** loads the Logging class. Extension class loaders load classes that are an extension of the standard core Java classes.

Finally, **the bootstrap one** loads the ArrayList class. A bootstrap or primordial class loader is the parent of all the others.

[Good Read](https://www.javaworld.com/article/2077260/learn-java-the-basics-of-java-class-loaders.html)


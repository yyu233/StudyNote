The compiler will issue a warning about this method. It'll warn that we're using a raw-typed collection. If we don't want to fix the warning, then we can suppress it with the @SuppressWarnings annotation.

This annotation allows us to say which kinds of warnings to ignore. While warning types can vary by compiler vendor, the two most common are deprecation and unchecked.

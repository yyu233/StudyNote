How does one decide to not serialize a member by giving transient modifier?

1. When the field refers to a resource that doesn't make sense to be serialised. For example, a OutputStream or a Window handle.
2. When the field can be reconstructed from the other information that is serialised. This helps in reducing the amount of data that need to be written.

For example, why member field table is not part of serialization?

Because (2). Have a look at the readObject method in the HashMap class. The table field is reconstructed using the other information in the class.

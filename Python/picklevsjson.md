There are fundamental differences between the pickle protocols and JSON (JavaScript Object Notation):

JSON is a text serialization format (it outputs unicode text, although most of the time it is then encoded to utf-8), while pickle is a binary serialization format;

JSON is human-readable, while pickle is not;

JSON is interoperable and widely used outside of the Python ecosystem, while pickle is Python-specific;

JSON, by default, can only represent a subset of the Python built-in types, and no custom classes; pickle can represent an extremely large number of Python types (many of them automatically, by clever usage of Python’s introspection facilities; complex cases can be tackled by implementing specific object APIs);

Unlike pickle, deserializing untrusted JSON does not in itself create an arbitrary code execution vulnerability.

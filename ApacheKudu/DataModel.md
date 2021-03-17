A Kudu cluster stores tables that look just like tables you're used to from relational (SQL) databases. A table can be as simple as an binary key and value, or as complex as a few hundred different strongly-typed attributes.

Just like SQL, every table has a PRIMARY KEY made up of one or more columns. This might be a single column like a unique user identifier, or a compound key such as a (host, metric, timestamp) tuple for a machine time series database. Rows can be efficiently read, updated, or deleted by their primary key.

Kudu's simple data model makes it breeze to port legacy applications or build new ones: no need to worry about how to encode your data into binary blobs or make sense of a huge database full of hard-to-interpret JSON. Tables are self-describing, so you can use standard tools like SQL engines or Spark to analyze your data.

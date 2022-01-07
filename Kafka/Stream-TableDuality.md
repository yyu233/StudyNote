Kafka Streams support streams but also tables that can be bidirectionally transformed.  It is the so-called stream-table duality. Tables are a set of evolving facts. Each new event overwrites the old one, whereas streams are a collection of immutable facts.

Streams handle the complete flow of data from the topic. Tables store the state by aggregating information from the streams

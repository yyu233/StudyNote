Kudu was designed to fit in with the Hadoop ecosystem, and integrating it with other data processing frameworks is simple. You can stream data in from live real-time data sources using the Java client, and then process it immediately upon arrival using Spark, Impala, or MapReduce. You can even transparently join Kudu tables with data stored in other Hadoop storage such as HDFS or HBase.

Kudu is a good citizen on a Hadoop cluster: it can easily share data disks with HDFS DataNodes, and can operate in a RAM footprint as small as 1 GB for light workloads.

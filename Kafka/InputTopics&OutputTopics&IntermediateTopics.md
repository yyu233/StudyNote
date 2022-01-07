Input topics    
Topics that are specified via source processors in the application’s topology; e.g. via StreamsBuilder#stream(), StreamsBuilder#table() and Topology#addSource().     
Output topics       
Topics that are specified via sink processors in the application’s topology; e.g. via KStream#to(), KTable.to() and Topology#addSink().     
Intermediate topics     
Topics that are both input and output topics of the application’s topology; e.g. via KStream#through().       

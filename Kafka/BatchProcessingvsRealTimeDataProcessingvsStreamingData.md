Batch processing is when the processing and analysis happens on a set of data that have already been stored over a period of time. An example is payroll and billing systems that have to be processed weekly or monthly.     

Streaming data processing happens as the data flows through a system. This resultas in analysis and reporting of events as it happens. An example would be fraud detection or intrusion detection. Streaming data processing means that the data will be analyzed and that actions will be taken on the data within a short period of time or near real-time, as best as it can.   

Real-time data processing guarantees that the real-time data will be acted on within a period of time, like milliseconds. An example would be for-real time application that purchases a stock within 20ms of receiving a desired price.    

Here’s a breakdown of major differences between batch processing, real-time data processing, and streaming data:    

|Batch Data Processing|	Real-Time Data Processing|	Streaming Data|
|---|---|---|
|Hardware|	Most storage and processing resources requirement to process large batches of data.	|Less storage required to process the current or recent set of data packets. Less computational requirements.	|Less storage required to process current data packets. More processing resources required to “stay awake” in order to meet real-time processing guarantees|
|Performance|	Latency could be minutes, hours, or days	|Latency needs to be in seconds or milliseconds|	Latency must be guaranteed in milliseconds|
|Data set	|Large batches of data	|Current data packet or a few of them	|Continuous streams of data|
|Analysis	|Complex computation and analysis of a larger time frame|	Simple reporting or computation	|Simple reporting or computation|

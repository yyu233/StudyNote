## Type of Devices ## 

Devices are divided into 2 types: character devices and block devices. 

Block devices has a buffer for requests so that they can choose the best order in which to respond to the requests. This is important in the case of storage devices where it's faster to read or write sectors which are close to each other, rather than those which are further apart. 

Block devices can only accept input and return output in blocks, whereas character devices are allowed to use as many bytes as possible. 

## Type of Devices ## 

Devices are divided into 2 types: character devices and block devices. 

Block devices has a buffer for requests so that they can choose the best order in which to respond to the requests. This is important in the case of storage devices where it's faster to read or write sectors which are close to each other, rather than those which are further apart. 

Block devices can only accept input and return output in blocks, whereas character devices are allowed to use as many bytes as possible. 

## Registering A Device ##   
eg:   
``` brw-rw----  1 root  disk  3, 1 Jul  5  2000 /dev/hda1 ```    
   
The number 3 is a major number. The major number tells whcih driver handles which device file. The number 1 is a minor number. The minor number is uded only by the driver itself to differentiate which device it's operating on, just in case the driver handles more than one device.    

Registering a device means registering it with the kernel.    

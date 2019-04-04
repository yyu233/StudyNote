## Kickstart ##
Using kickstart, a system administrator can create a single file containing the answers to all the questions that would normally be asked during a typical installation.
Kickstart files can be kept on a single server system and read by individual computers during the installation. This installation method can support the use of a single kickstart file to install Red Hat Enterprise Linux on multiple machines, making it ideal for network and system administrators.

### Kickstart Section ### 

Sections must be in this order: 
1. Command Section 
2. ```%package``` Section
3. ```%pre``` ```%post``` pre and post installtion are optional, and can in any order.   

Example of ```%package``` section: 
```
    %packages 
    @ X Window System 
    @ GNOME Desktop Environment 
    @ Graphical Internet 
    @ Sound and Video dhcp
``` 

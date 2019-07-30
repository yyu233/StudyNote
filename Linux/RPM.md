Red Hat Package Manager 

RPM packages metadata along with the software. The metadata contains the version number, list of files, dependencies and scripts and etc.

**Yum** command would download the software along with other dependent software in the yum repo created by the developers. Use yum to download, remove or query packages.

### Why RPM ### 
1. RPM maintains a database of installed software packages. Easy to query and verify.    
2. Add package to yum. Centralized location for packages.  
3. Digitally sign the package with GPG key.    

### Diagnosis ##

1. Verify entire file system and see what might be deleted:  ``` rpm -Va ```
  
[Take RPM to the Limit](http://rpm5.org/docs/max-rpm.html#s1-rpm-inside-macros)       
[How to Build RPM](https://access.redhat.com/sites/default/files/attachments/rpm_building_howto.pdf)

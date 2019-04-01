``` yum remove ``` to remove RPM packages    

**/etc/yum.conf**   
The configuration file for yum and related utilities is located at /etc/yum.conf. This file contains one mandatory [main] section, which allows you to set Yum options that have global effect, and can also contain one or more [repository] sections, which allow you to set repository-specific options.

**/etc/yum.repos.d**
It is recommended to define individual repositories in new or existing .repo files in the /etc/yum.repos.d/ directory. The values you define in individual [repository] sections of the /etc/yum.conf file override values set in the [main] section

This kind of separation of configuration information is common in Linux.

Many programs use text-based configuration files (which can be extremely large and hard to read or are intended to provide only a basic set of data to operate). As such, it is often considered desirable to sort out things that are more likely to need to be changed (such as repository data) from information that is less likely to need to be changed (how yum works by default).

## yum cache ## 

Caches provide three advantages:
* The performance of yum increases
* You may carry out yum operations without a network connection, by using only the caches
* You may copy packages from the caches and reuse them elsewhere

By default, yum stores temporary files under the directory /var/cache/yum/, with one subdirectory for each configured repository

When distribution packaging became more and more common, it became clear that we needed better ways of forming such configuration files out of multiple fragments, often provided by multiple independent packages. Each package that needs to configure some shared service should be able to manage only its configuration without having to edit a shared configuration file used by other packages.

The most common convention adopted was to permit including a directory full of configuration files, where anything dropped into that directory would become active and part of that configuration. As that convention became more widespread, that directory was usually named after the configuration file that it was replacing or augmenting. But since one cannot have a directory and a file with the same name, some method was required to distinguish, so .d was appended to the end of the configuration file name. Hence, a configuration file /etc/Muttrc was augmented by fragments in /etc/Muttrc.d, /etc/bash_completion was augmented with /etc/bash_completion.d/*, and so forth. Sometimes slight variations on that convention are used, such as /etc/xinetd.d to supplement /etc/xinetd.conf, or /etc/apache2/conf.d to supplement /etc/apache2/apache2.conf. But it's the same basic idea.


*********    
[Reference](http://blog.siphos.be/2013/05/the-linux-d-approach/)   

Many services on a Linux system use a *.d directory approach to make their configuration easily configurable by other services. This is a remarkably simple yet efficient method for exposing services towards other applications. Let's look into how this .d approach works.

Take a look at the /etc/pam.d structure: services that are PAM-aware can place their PAM configuration files in this location, without needing any additional configuration steps or registration. Same with /etc/cron.d: applications that need specific cronjobs do not need to edit /etc/crontab directly (with the problem of concurrent access, overwriting changes, etc.) but instead can place their definitions in the cron.d directory.

This approach is getting more traction, as can be seen from the available "dot-d" directories on a system:

An application can place its configuration files in these directories, automatically "plugging" it in into the operating system and the services that it provides. And the more services adopt this approach, the easier it is for applications to be pluggable within the operating system. Even complex systems such as database systems can easily configure themselves this way. And for larger organizations, this is a very interesting approach.

Consider the need to deploy a database server on a Linux system in a larger organization. Each organization has its standards for file system locations, policies for log file management, etc. With the *.d approach, these organizations only need to put files on the file system (a rather primitive feature that every organization supports) and manage these files instead of using specific, proprietary interfaces to configure the environment. But to properly control this flexibility, a few attention points need to be taken into account.

The first is to use a proper naming convention. If the organization has a data management structure, it might have specific names for services. These names are then used throughout the organization to properly identify owners or responsibilities. When using the *.d directories, these naming conventions also allow administrators to easily know who to contact if a malfunctioning definition is placed. For instance, if a log rotation definition has a wrong entry, a file called mylogrotation does not reveal much information. However, CDBM-postgres-querylogs might reveal that the file is placed there by the customer database management team for a postgresql database. And it isn't only about knowing who to contact (because that could easily be done by comments as well), but also to ensure no conflicts occur. On a shared database system, it is much more likely that two different teams place a postgresql file (which would overwrite the file already there) unless they use a proper naming convention.

The second is to use something identifying where the file comes from. A best practice when using Puppet for instance is to add in a comment to the file such as the following:

This file is managed by Puppet through the org-pgsl-def module  
Please do not modify manually  
This informs the administrator how the file is put there; you might even want to include version information.  

A third one is when the order of configuration entries is important. Most *.d supporting tools do not really care about ordering, but some, like udev, do. When that is the case, the common consensus is to use numbers in the beginning of the file name. The numbers then provide a good ordering of the files.

Not all services already offer *.d functionality, although it isn't that difficult to provide it as well. Consider the Linux audit daemon, whose rules are managed in the /etc/audit/audit.rules file. Not that flexible, isn't it? But one can create a /etc/audit/audit.rules.d location and have the audit init script read these files (in alphanumeric order), creating the same functionality.

Given enough service adoption, software distribution can be sufficient to configure an application completely and integrate it with all services used by the operating system. And even services that do not support *.d directories can still be easily wrapped around so that their configuration file itself is generated based on the information in such directories. Consider a hypothetical AIDE configuration, where the aide.conf is generated based on the aide.conf.head, aide.d/* and aide.conf.tail files (similar to how resolv.conf is sometimes managed). The generation is triggered right before aide itself is called (perhaps all in a single script).

Such an approach allows full integration:

A PAM configuration file is placed, allowing the service authentication to be easily managed by administrators. Changes on the authentication (for instance, switch to an LDAP authentication or introduce some trust relation) is done by placing an updated file.
A log rotation configuration file is placed, making sure that the log files for the service do not eventually fill the partitions
A syslog configuration is provided, allowing for some events to be sent to a different server instead of keeping it local - or perhaps both
A cron configuration is stored so that statistics and other house-cleaning jobs for the service can run at night
An audit configuration snippet is added to ensure critical commands and configuration files are properly checked
Intrusion detection rules are added when needed
Monitoring information is placed on the file system, causing additional monitoring metrics to be automatically picked up
Firewall definitions are extended based on the snippets placed on the system
etc. And all this by only placing files on the file system. Keep It Simple, and efficient ;-)

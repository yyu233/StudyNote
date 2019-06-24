when make changes to a directorym, permission denied error.   
Use **ls -al** to show the owner of the directory.    
Use **sudo chown -R usernane:usernane directory** to change the owner 

Recursively find a file: **find . -name <filename>**   
  
Get a list of users:  **less /etc/passwd**

Get the user status logged into the computer: **w**

Get the process id: **ps -p $$**

Service command for controling the daemon process: **service script-name start**, **service script-name restart**, **service script-name stop**, **service script-name status**

List all processes: **ps -A**

Kill process: **ps -9 PID**

Download"  **wget link** or **curl -O link**

Secure copy: **scp user@host:filename user@host:filename**

Pipe output to file : [Reference](https://askubuntu.com/questions/420981/how-do-i-save-terminal-output-to-a-file)

Chang password for current user: **passwd**

Remount filesystem: **remount -rw -o remount /**

Home directory: **~**

Top root directory of filesystem **/**

awk:  **awk 'pattern {action}' input-file > output-file**    

Control systemd system and service manager: **systemctl COMMAND**

Switch user: **su user**  current working directory change, may require **cd** to go to user home directory     
             **su - user** land into user default home directory   
             
Change user setting: **usermod \<option> NAME** 

Add user: **useradd \<name>**   

Check disk usage: **df**

Check hostname: **cat /proc/sys/kernel/hostname**  

Communicate to other user: **wall \<message>**   **write \<user> \<message>**     

Watch file for changes:  **tail -f \<file>**   

Add user to supplementary group: **usermode -aG \<group> \<user>**    

Move to the begining of line: **Ctrl A**  

Move to the end of line: **Ctrl E**  

Move left one word: **Ctrl left arrow**   

Move right one word: **Ctrl right arrow**   

Delete from cursor to the begining of the line: **Ctrl U**       

Delete from cursor to the end of the line: **Ctrl K**         

Copy from clipboard: **Ctrl Shift C**        

Paste to command line: **Ctrl Shift V**    

Switch to previous folder: **cd -**   

Search word case insensitive: **grep -i \<pattern> \<file>**   

Ignore pattern: **grep -vi \<pattern> \<file>**  

Show lines with the regex: **grep -E \<pattern>**   

Print column of data: **awk '{print $\<num>}' \<filename>**    

Sort numerically: **sort -n \<filename>**   

Sort uniquely: **sort -u \<filename>** 

Switch string 1 with string 2: **sed "s/\<string 1>/\<string 2>" \<filename>**   

Append: **\>\>**  

Find location of command: **which \<cmd>**     

Identify tyoe of line breaks in text file: **find \<filename>**   

Find kernel information: **uname -a** 

Display human readable number of memory usages: **free -h**   

Check cpu information: **cat /proc/cpuinfo**    

View hardware information: **lshw**    

View network ip address informatio: **ip a**    

Display status of file: **stat \<filename>**  

Display ACL(Access Control List) of file for tabular format: **getfacl -t \<filename>**   

Create an empty file: **touch \<filename>**   

Match one character of numbers: **[:digit:]**   

Match one uppercase letter: **[:upper:]**  

Match one lowercase letter: **[:lower:]**  

Match one uppercase or lowercase letter: **[:alpha:]**  

Match one uppercase, lowercase or number: **[:alnum:]**   

Match one space, tab, linefeed, formfeed, or vertical tab: **[:space:]**   

Match one space, or tab **[:blank:]**    

Configure shell options: **set +o/-o**    

Configure bash options: **shopt -s/-u**   

Display directory tree: **tree -L \<levle>**   

Query sysfs or the udev database: **udevadm info --query=TYPE --path=SYSPATH** 

Create all directories in case that directory does not exist: **mkdir -p \<parent>/\<child>**   

Compare files line by line: **diff** 

Current running process id: **$$**     

Configure Network Interface: **dhclient**  

Grep command meta data empty string at the begining: **^**  

Grep command meta data empty string at the end: **$**   

Export variable to child process: **export \<var>**   

Display host name IP address: **hostname -I**   

Display host name IP address: **ip a s**   

Serve files from current directory: **python -m SimpleHttpServer: 8080**     

List PCI device in tree strucuture: **lspci -t**    

Cut and print by column (for fixed line length): **cut -c \<column> \<filename>**   

Cut and print by field (for flexible line length): **cut -d \<delimiter> -f \<field> \<filename>**    

Arithmetic operation: **expr \<arithmetic operation>**     

Using 'su' to simulate 'sudo': **su -c \<command>**  

Using 'sudo' to simulate 'su': **sudo -i**   

Enable a network interface: **ifconfig \<nic> up**   

Disable a network interface: **ifconfig \<nic> down**    

Set static IP address: **ifconfig \<nic> \<IP>**   

Covert RPM to CPIO: **rpm2cpio \<rpm>**    

Create temporary file with random name with no other user to access (permission 600, must contain at lease 3 consecutive X at the end): **mktemp \<template>.XXX**     

Display kernel modules that are loaded into kernel: **lsmod**    

Display kernel version: **uname -r**    

Remove password of a user: **passwd -d \<user>**   

List block devices: **lsblk**   

Partition a device: **parted \<dev>**   

Format a device: **/sbin/mkfs -t \<fs> \<dev>**    

Install RPM: **rpm -igh \<rpm>**   

Unintall RPM: **rpm -e \<rpm>**  

List installed RPMS: **rpm -qa**   

Show history commands: **history**   

Execute command from stdin: **xarg \<command>  -L \<maximum number of non-blank line passed from stdin per time>**    

Print process in tree strucute: **pstree -p**   

Redirect stdout and stderr: **&>** or **>&**    

Bring suspended or background job to foreground: **fg \<#job id>**     

Suspend a process: **Ctrl + Z**    

Resume suspened process in the background: **bg**    

Query information from YUM repo: **repoquery --disablerepo=\<repo> --enablerepo=\<repo> --repofrompath=\<repoid>, \<path/url> -f \<filename>**    

Find list of top processes ordered by RAM and CPU: **top -eo pid,ppid,cmd,%mem,%cpu --sort=%mem | head**    

Display all setting configurable in the ```/proc/sys/```: **sysctl -a**         

List all signals: **kill -l**     













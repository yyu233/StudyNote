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

Create a sharing mount point: **mount --make-shared \<mount_point> **, **mount --bind \<mount_pint> \<other_mount_point>** 

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

Check if rpm is installed: **rpm -qi**     

List uninstalled RPM contents: **rpm -qlp \<rpm_name>**   

Show history commands: **history**   

Execute command from stdin: **xarg \<command>  -L \<maximum number of non-blank line passed from stdin per time>** 

Execute command for filename containing spaces: **xarg -d '\n' \<file>**   

Print process in tree strucute: **pstree -p**   

Redirect stdout and stderr: **&>** or **>&**    

Bring suspended or background job to foreground: **fg \<#job id>**     

Suspend a process: **Ctrl + Z**    

Resume suspened process in the background: **bg**    

Query information from YUM repo: **repoquery --disablerepo=\<repo> --enablerepo=\<repo> --repofrompath=\<repoid>, \<path/url> -f \<filename>**    

Find list of top processes ordered by RAM and CPU: **top -eo pid,ppid,cmd,%mem,%cpu --sort=%mem | head**    

Display all setting configurable in the ```/proc/sys/```: **sysctl -a**         

List all signals: **kill -l**     

Count number of lines in file: **wc \<file>**   

View and configure Linux kernel parameters: **sysctl**   

Open files in tabs by Vim: **vim -p \<files>**    

Determine which process is using a file: **fuser**    

Display mounted file system: **df**   

Check ext2/ext3/ext4 file system: **e2fsck**    

Manage disk partition: **parted**   

Logical Volume Management: **lvm**     

Re-execute previous command: **!!**    

Execute command itself instead of alias: **\\ \<command>**    

Set ACL: **setfacl**    

Retrieve ACL: **getfacl**     

To view a list of configured devices and currently active network interfaces: **service net status**     

Configure symbolic link: **alternatives --config \<command>**    

Check all disk parition: **fdisk -l**   

Format disk: **mkfs**    

Display alias command: **alias**  

Temporarily disable alias command: **\\\<alias command>**  

Looks through the currently running bash processes on Linux and lists the process IDs (PID) on screen: **pgrep**     
 
List open files: **lsof**    

List logined user: **who**    (interesting note: If FILE is not specified, use /var/run/utmp. /var/log/wtmp as FILE is common. If ARG1 ARG2 given, -m presumed: 'am i' or 'mom likes' are usual.)      

Check if shell command is built in or not:**type \<command>**     

Re-excute command from history: **！ \<history number>**      

Merge files line by line (default delimeter is tab): **paste \<file1> \<file2>**     

Paginate or columnate files for printing: **pr**  

Change user password expiration information: **chage**    

Delete user group: **groupdel**    

Delete user: **userdel**    

Clone file permission: **chown --reference=ref_file file**   

Print message buffer of kernel: **dmesg**       

Start service: **systemctl start \<name>**    

Stop service: **systemctl stop \<name>**    

Restart a running service: **systemctl try-restart \<name>**    

Restart a service: **systemctl restart \<name>**   

Display all running service status: **systemctl**    

Display current running service status: **systemctl status \<name>**    

Enable running service at boot time: **systemctl enable \<name>**   

Disable runnig servie at boot time: **systemctl disable \<name>**    

Check if a service is enabled: **systemctl is-enabled \<name>**   

Adjust running priority of process: **renice**      

Find file name path: **${FILE%./*}**   

Flush memory to disk (useful if umount does not work): **sync**   

Create physical volume: **pvcreate \<partition>**   

Create volume group: **vgcreate \<name> \<partition>**   

Create logical volume: **lvcreate**   

Remove physical volume: **pvremove**  

Remove volume group: **vgremove**   

Remove logical volume: **lvremove**   

List configured repositories: **yum repolist \<filter>**      

Print resolved symbolic link: **readlink**    

Strip directory and suffix from filename: **basename**   

List file size under directory: **du**        

Print array element line by line: **printf '%s\n' "${my_array[@]}"**    

Print array element line by line: **( IFS=$'\n'; echo "${my_array[\*]}" )**   

List contents of archive: **cpio -it < \<archive>**    

Add and remove modules from the Linux kernel: **modprobe**    

View default Linux target: **systemctl get-default**   

View current Linux target : **systemctl list-units --type target**     

Switch terminal: **CTRL+ALT+F1~12**      

TTY setting: **stty -a**    

Bring interface up: **ip link set \<dev> up**    

Check port: **netstat -tupln | grep \<port>**    

Check services and listening port: **less /etc/services**         

Check which kernel to boot into: **cat /boot/grub2/grubenv |grep saved**    

Controlling NetworkManager: **nmcli**   

NetworkManager text user interface : **nmtui**    

View problem data: **abrt-cli**   











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

Print output in table: **column -t -s \<field separater>**      

Create a sharing mount point: **mount --make-shared \<mount_point> **, **mount --bind \<mount_pint> \<other_mount_point>** 

Home directory: **~**


Top root directory of filesystem **/**

awk:  **awk 'pattern {action}' input-file > output-file**    

awk deduplicate: **awk '!seen[$0]++' \<file>**

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

Move between start of command line to the current cursor: **Ctrl X**   

Retrieve last itme you deleted or cut: **Ctrl Y**   

Cut word after cursor: **Alt + d**   
Switch to previous folder: **cd -**   

Search word case insensitive: **grep -i \<pattern> \<file>**   

Ignore pattern: **grep -vi \<pattern> \<file>**  

Show lines with the regex: **grep -E \<pattern>**   

Print column of data: **awk '{print $\<num>}' \<filename>**    

Sort numerically: **sort -n \<filename>**   

Sort uniquely: **sort -u \<filename>** 

Switch string 1 with string 2: **sed "s/\<string 1>/\<string 2>" \<filename>**   

Print from line a to line b and quit scanning at line c: **sed -n 'a,bp;cq' \<filename> > \<newfile>**

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

List current settings of shell: **shopt**     

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

List scripts associated with the rpm: **rpm -ql \<rpm_name> --scripts** 

Show history commands: **history**   

Execute command from stdin: **xarg \<command>  -L \<maximum number of non-blank line passed from stdin per time>** 

Execute command for filename containing spaces: **xarg -d '\n' \<file>**     

Rename command argument to {} and use it as a placeholder: **xarg -I {} \<command> {}**    

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

Check if ISO is bootable: **isoinfo -d -i is_it_bootable.iso**     

Display files in hex, oct, decimal or ascii: **hexdump**   

Extract squashfs image: **unsquashfs**  

Bring virtual terminal to foreground: **chvt**      

List Firewall Zone Rules: **ls -l /usr/lib/firewalld/zones/**    

List groups: **groups**    

Print information about a user: **id**   

Show thread: **top -H -p \<PID>**     

Bind key stroke to function: **bind**    

Select nth argument of previous command: **ALT + number + .**    

List bash built-in commands: **help**     

Construct command by concatenating arguments: **eval**   

Check ssh ciphers: **ssh -Q ciphers**    

Keep running process after shell is closed: **nohup**      

Replace character with other character: **tr**    

Create compressed image of remote drive using SSH: **ssh username@54.98.132.10 "dd if=/dev/sda | gzip -1 -" | dd of=backup.gz**  

Check block device filesystem type：**lsblk -lno FSTYPE </dev/>**

Query Internet Servers: **nslookup**  

Get Content from Webpage: **wget -m -p -E -K -k \<link>**   

Specify file size limit of shell and its subprocess: **ulimit** 

Check space of Volume Group: **vgdisplay**   

Exporting content of rpmdb: **rpm -qa --xml** 

Check current SElinux Mode: **getenforce** 

Get verbose SElinux status: **sestatus** 

Create a new running session: **setsid** 

Make process ignore the hangup signal: **nohup** 

Check open ports: **lsof -i -P -n | grep LISTEN**   

Make btrfs storage pool: **mkfs.btrfs**  

Query loop device status: **losetup**   

Connect mysql remotely: **mysql**   

Local SSH port forwarding: **ssh -L \<port>:\<destination>:\<port> \<user>@\<server address>**  

Remote SSH port forwarding: **ssh -R \<port>:\<destination>:\<port> \<user>@\<visitor address>**  

Wipe signature from disk: **wipefs**  

Check space of Volume Group: **vgdisplay**   

Back up a partition: **dd if=/dev/sda of=~/partition.img**  

Back up a disk: **dd if=/dev/sda of=~/disk.img**  

Interact with systemd running on remote machine over ssh: **systemctl --host user_name@host_name command**  

View Control Group Hierarchy: **systemctl-cgls**  

Find the running process ID from the stdout criteria: **pgrep**  

Get process summary: **strace -c -p \<PID>**  

Get process instruction: **strace -i -p \<PID>**

Get process instruction time difference: **strace -T -p \<PID>**  

Trace process by only specific system call: **strace -e trace=\<value> -p \<PID>**  

Find the pid of running program: **ps -C \<program> -o pid h**    

Print all current settings in human readable form: **stty --all**   

Get all available encoding on the platform: **iconv --list**  

List the content of initramfs: **lsinitrd**   

Check RAID status: **/proc/mdstat**   

Searching a given binary image for embedded files and executable code: **binwalk**   

Print the stack trace of running process: **gstack**  

Restore volume group state: **vgcfgrestore**  

List all blocked state process: **echo w > /proc/sysrq-trigger** 

Print stack of each tread in the process: **eu-stack**  

Find out which entries manual contains for a command: **man -f \<command>**  

Search with keywords in manual: **man -k \<keyword>**  

Provides information for inter-process communication facilities: **ipcs**  

Merge snapshot into original logical volume: **lvmconvert --mergesnapshot \<snapshot volume>**  

Translate memory address into symbol: **klogd**   

Get attributes info starts with the device specified by the devpath and then chain of parent devices: **udevadm info -a -n**  

Monitor udev events: **udevadm monitor**  

Verfiy signature of rpm: **rpm -K**   

Only check kernel log: **journalctl -k**   

Check last boot log: **journalctl -b -1**  

Check PID log: **journalctl _PID=\<a\>**  

Check log for script: **journalctl \<script>**  

Check log for user ID: **journalctl _UID=\<a\>**  

Check log for systemd unit: **journalctl -u \<unit\>**  

Check log with level: **journalctl -p \<level> ** 

Set lifecycle for the log: **journalctl --vacuum-time=\<time>**  

Remove jobs from background and block HUP: **disown -h**  

Speed up SSH channel: **ssh -X -C -c**   

Change a process IO priority: **ionice**  

To create an MD5 file for a file: **md5sum \<file> > \<file>.md5** 

Kill group of process: **kill -TERM -\<PGID>**  

Set CPU affinity: **taskset** 

List all currently held locks: **lslocks**  

Adjust tunabled filesystem paramets on ext2/ext3/ext4 filesystem: **tune2fs**  

Control the default file permission for new files: **umask**  

Check current active IO scheduler: **cat /sys/block/sda/queue/scheduler**  

Check all cpu core usage: **mpstat -p ALL 1**  

Clear Page Cache: **sync;echo 1 > /proc/sys/vm/drop_caches**  

Clear Dentris and Inode: **sync;echo 2 > /proc/sys/vm/drop_caches** 

Clear Page Cache, Dentries and Inode:  **sync;echo 3 > /proc/sys/vm/drop_caches**  

Ensure drop cache for the whole file: **dd of=ofile oflag=nocache conv=notrunc,fdatasync count=0**  

List X Input Devices: **xinput --list** 

Return terminal tty to sanity: **stty sane**  

Query terminal info: **infocmp \<terminal type>**   

Change the NICE value of running process: **renice**  

Get a list of input devices: **cat /proc/bus/input/devices** 

Add Keyfile pem to ssh: **ssh-add keyfile.pem**   

Create NSS database: **certutil -d /etc/dirsrv/slapd-instance_name/ -N**  

Create Certificate Signing Request: **certutil -d instance_directory -R -g key_size -a -o output_file -8 FQDN -s \<subject>**  

Remove certificate: **certutil -d instance_directory -D -n "cert name"**    

Display keys in database: **certutil -d instance_directory -K**   

Remove the private key: **certutil -d instance_directory -F -n "cert name"**    

View the content of P12 file: **openssl pkcs12 -info -in filename.p12**   

Run localscript over SSH to remote machine: **ssh root@MachineB ARG1="arg1" ARG2="arg2" 'bash -s' < local_script.sh**   
                                                                                                                     
Start and configure a new PKI instance: **pkispawn**       

Remove PKI instance: **pkidestroy**   
                                                                                                                     
Create a new private key and CSR: **openssl req -out \<CSR.csr\> -new -newkey \<rsa:2048\> -nodes -keyout \<privateKey.key\>**       

Generate self-signed certificate: **openssl req -x509 -sha256 -nodes -days \<365\> -newkey \<rsa:2048\> -keyout \<privateKey.key\> -out \<certificate.crt\>** 

Verify certificate:**openssl verify -CAfile \<chain.pem\> \<mycert.pem\>**    

Generate a certificate signing request based on an existing certificate: **openssl x509 -x509toreq -in certificate.crt -out CSR.csr -signkey privateKey.key**   

Remove a passphrase from a private key: **openssl rsa -in privateKey.pem -out newPrivateKey.pem**   
  
Check a Certificate Signing Request (CSR): **openssl req -text -noout -verify -in CSR.csr**   
  
Check a private key: **openssl rsa -in privateKey.key -check**    
  
Check a PKCS#12 file (.pfx or .p12): **openssl pkcs12 -info -in keyStore.p12**    
  
Check an SSL connection. All the certificates (including Intermediates) should be displayed: **openssl s_client -connect \<website\>**   

Verify certificate with intermediate CA certificate:**openssl verify -CAfile ca.pem -untrusted intermediate.cert.pem cert.pem**   

Print all certificate content from a chained pem:**openssl crl2pkcs7 -nocrl -certfile \<CHAINED.pem\> | openssl pkcs7 -print_certs -text -noout**   
  
Modify the stdout buffering to line: **stdbuf -oL command > output**    
 
Disable all stdout buffering:**stdbuf -o0 command > output**   
  
Password history:**/etc/security/opasswd**  
  
Update man internal database: **mandb**   
  
Clear all command history: **history -c**
 
Clear specific line command history **history  -d \<line number>**    
  
Check previous and current run level: **runlevel**    
  
Enable extended shell pattern:  **shopt -s extglob**    
  
Split large file: **split -b**  
  
Join files: **cat**   
  
Get current ip rules: **iptable -S**    
  
Scan port table: **nmap**   
  
 
 
 
 


                                                                                                                     
                                                                                             
                                                                                                                     
                                                                                                                     


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

Communicate to other user **wall \<message>**   **write \<user> \<message>**   


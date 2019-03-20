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





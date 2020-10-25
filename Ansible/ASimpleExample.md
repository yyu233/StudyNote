```
block: 
   - name: Install Tomcat artifacts 
      action: > 
      yum name = "demo-tomcat-1" state = present 
      register: Output 
          
   always: 
      - debug: 
         msg: 
            - "Install Tomcat artifacts task ended with message: {{Output}}" 
            - "Installed Tomcat artifacts - {{Output.changed}}" 
Here, the output is the variable used.

Let us walk through all the keywords used in the above code −

block − Ansible syntax to execute a given block.

name − Relevant name of the block - this is used in logging and helps in debugging that which all blocks were successfully executed.

action − The code next to action tag is the task to be executed. The action again is a Ansible keyword used in yaml.

register − The output of the action is registered using the register keyword and Output is the variable name which holds the action output.

always − Again a Ansible keyword , it states that below will always be executed.

msg − Displays the message
```
